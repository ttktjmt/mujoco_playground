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

.. mjswan demo goes here once published (https://embed.mjswan.com/<id>).

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
