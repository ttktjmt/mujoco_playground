Whole Body
==========

``tasks/whole_body/tracking``: the :doc:`Unitree G1 <../../robots/g1>` tracks a reference motion clip with its whole
body (BeyondMimic-style).

G1WholeBodyTracking
-------------------

.. image:: https://www.gstatic.com/reaf-sim/demos/g1_lafan_dance/0/g1_lafan_dance.webp
    :align: center
    :alt: Unitree G1 Whole-Body Motion Tracking
    :width: 80%

|

.. Placeholder until the mjswan Cloud demo is published: then an iframe on
   https://embed.mjswan.com/<id>, and an "Open in a new tab" link to https://mjswan.com/s/<id>.

.. raw:: html

   <div role="img" aria-label="Interactive demo of G1WholeBodyTracking, coming soon"
     style="width: 100%; aspect-ratio: 16 / 9; border-radius: 6px; background: #1f2633;
       color: #c9d1dc; display: flex; flex-direction: column; align-items: center;
       justify-content: center; gap: 0.5rem; text-align: center; font-size: 0.95rem;
       box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.08); margin-bottom: 1.15rem;">
     <svg width="48" height="48" viewBox="0 0 48 48" aria-hidden="true">
       <circle cx="24" cy="24" r="22" fill="none" stroke="currentColor" stroke-width="2"/>
       <path d="M19 15 L34 24 L19 33 Z" fill="currentColor"/>
     </svg>
     <span>Interactive demo: G1WholeBodyTracking</span>
     <span style="opacity: 0.65; font-size: 0.85rem;">Coming soon on mjswan Cloud</span>
   </div>

Convert a retargeted CSV clip (e.g. from the `LAFAN1 Retargeting Dataset for G1
<https://huggingface.co/datasets/lvhaidong/LAFAN1_Retargeting_Dataset/tree/main/g1>`_) to ``.npz``, verify it in the
viewer, and train a tracking policy:

.. code-block:: bash

    # 1. Convert CSV trajectory to .npz and preview in viewer
    uv run python -m mujoco_playground.tasks.whole_body.tracking.csv_to_npz \
      --input_csv=/path/to/input.csv --output_npz=/path/to/output.npz
    uv run python -m mujoco_playground.tasks.whole_body.tracking.replay_npz \
      --trajectory_path=/path/to/output.npz

    # 2. Train tracking policy
    uv run --extra rl playground train rsl_rl \
      --env=G1WholeBodyTracking \
      --env_overrides='{"trajectory_path": "/path/to/output.npz"}' \
      --logdir=/tmp/g1_tracking

    # 3. Play checkpoint with reference ghost enabled
    uv run --extra rl playground play rsl_rl \
      --env=G1WholeBodyTracking \
      --env_overrides='{"trajectory_path": "/path/to/output.npz", "play": true, "enable_ghost": true}' \
      --resume_path=/tmp/g1_tracking \
      --nworld=1
