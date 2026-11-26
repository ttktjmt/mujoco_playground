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

.. raw:: html

   <iframe
     src="https://embed.mjswan.com/lDIKRyb"
     title="TrossenPickCube, interactive demo (mjswan)"
     style="display: block; width: 100%; aspect-ratio: 16 / 9; border: 0; border-radius: 6px;"
     allow="xr-spatial-tracking"
     allowfullscreen
   ></iframe>
   <p><a href="https://mjswan.com/s/lDIKRyb" target="_blank" rel="noopener">Open in a new tab ↗</a></p>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=TrossenPickCube \
      --logdir=/tmp/rslrl_logs/trossen_pick_cube

TrossenPickCubeVision
---------------------

.. raw:: html

   <iframe
     src="https://embed.mjswan.com/rlpfagJ"
     title="TrossenPickCubeVision, interactive demo (mjswan)"
     style="display: block; width: 100%; aspect-ratio: 16 / 9; border: 0; border-radius: 6px;"
     allow="xr-spatial-tracking"
     allowfullscreen
   ></iframe>
   <p><a href="https://mjswan.com/s/rlpfagJ" target="_blank" rel="noopener">Open in a new tab ↗</a></p>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=TrossenPickCubeVision \
      --logdir=/tmp/rslrl_logs/trossen_pick_cube_vision
