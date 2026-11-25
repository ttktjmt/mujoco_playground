Manipulation
============

``tasks/manipulation/pick_cube``: an arm picks up a cube and lifts it to a target. Each robot has a state variant,
which observes the cube's position, and a vision variant, which finds the cube through its wrist camera.

.. list-table::
    :header-rows: 1
    :widths: 30 25 30 15

    * - Environment ID
      - Robot
      - Observations
      - Control
    * - ``SO101PickCube``
      - :doc:`SO-101 <../../robots/so101>`
      - State
      - 50 Hz
    * - ``SO101PickCubeVision``
      - :doc:`SO-101 <../../robots/so101>`
      - State + wrist camera (64×64)
      - 10 Hz
    * - ``TrossenPickCube``
      - :doc:`Trossen WXAI <../../robots/trossen_wxai>`, right arm
      - State
      - 50 Hz
    * - ``TrossenPickCubeVision``
      - :doc:`Trossen WXAI <../../robots/trossen_wxai>`, right arm
      - State + wrist camera (32×32)
      - 50 Hz

SO101PickCube
-------------

.. raw:: html

   <iframe
     src="https://embed.mjswan.com/YuXtzQL"
     title="SO101PickCube, interactive demo (mjswan)"
     style="display: block; width: 100%; aspect-ratio: 16 / 9; border: 0; border-radius: 6px;"
     allow="xr-spatial-tracking"
     allowfullscreen
   ></iframe>
   <p><a href="https://mjswan.com/s/YuXtzQL" target="_blank" rel="noopener">Open in a new tab ↗</a></p>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=SO101PickCube \
      --logdir=/tmp/rslrl_logs/so101_pick_cube

SO101PickCubeVision
-------------------

This is the policy that :doc:`Sim-to-Real <../sim2real>` deploys on the physical SO-101.

.. raw:: html

   <iframe
     src="https://embed.mjswan.com/3-dJZNH"
     title="SO101PickCubeVision, interactive demo (mjswan)"
     style="display: block; width: 100%; aspect-ratio: 16 / 9; border: 0; border-radius: 6px;"
     allow="xr-spatial-tracking"
     allowfullscreen
   ></iframe>
   <p><a href="https://mjswan.com/s/3-dJZNH" target="_blank" rel="noopener">Open in a new tab ↗</a></p>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=SO101PickCubeVision \
      --logdir=/tmp/rslrl_logs/so101_pick_cube_vision

TrossenPickCube
---------------

.. Placeholder until the mjswan Cloud demo is published: then an iframe on
   https://embed.mjswan.com/<id>, and an "Open in a new tab" link to https://mjswan.com/s/<id>.

.. raw:: html

   <div role="img" aria-label="Interactive demo of TrossenPickCube, coming soon"
     style="width: 100%; aspect-ratio: 16 / 9; border-radius: 6px; background: #1f2633;
       color: #c9d1dc; display: flex; flex-direction: column; align-items: center;
       justify-content: center; gap: 0.5rem; text-align: center; font-size: 0.95rem;
       box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.08); margin-bottom: 1.15rem;">
     <svg width="48" height="48" viewBox="0 0 48 48" aria-hidden="true">
       <circle cx="24" cy="24" r="22" fill="none" stroke="currentColor" stroke-width="2"/>
       <path d="M19 15 L34 24 L19 33 Z" fill="currentColor"/>
     </svg>
     <span>Interactive demo: TrossenPickCube</span>
     <span style="opacity: 0.65; font-size: 0.85rem;">Coming soon on mjswan Cloud</span>
   </div>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=TrossenPickCube \
      --logdir=/tmp/rslrl_logs/trossen_pick_cube

TrossenPickCubeVision
---------------------

.. Placeholder until the mjswan Cloud demo is published: then an iframe on
   https://embed.mjswan.com/<id>, and an "Open in a new tab" link to https://mjswan.com/s/<id>.

.. raw:: html

   <div role="img" aria-label="Interactive demo of TrossenPickCubeVision, coming soon"
     style="width: 100%; aspect-ratio: 16 / 9; border-radius: 6px; background: #1f2633;
       color: #c9d1dc; display: flex; flex-direction: column; align-items: center;
       justify-content: center; gap: 0.5rem; text-align: center; font-size: 0.95rem;
       box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.08); margin-bottom: 1.15rem;">
     <svg width="48" height="48" viewBox="0 0 48 48" aria-hidden="true">
       <circle cx="24" cy="24" r="22" fill="none" stroke="currentColor" stroke-width="2"/>
       <path d="M19 15 L34 24 L19 33 Z" fill="currentColor"/>
     </svg>
     <span>Interactive demo: TrossenPickCubeVision</span>
     <span style="opacity: 0.65; font-size: 0.85rem;">Coming soon on mjswan Cloud</span>
   </div>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=TrossenPickCubeVision \
      --logdir=/tmp/rslrl_logs/trossen_pick_cube_vision
