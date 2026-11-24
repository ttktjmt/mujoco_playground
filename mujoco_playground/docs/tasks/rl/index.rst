Reinforcement Learning
======================

MuJoCo Playground provides reinforcement learning environments for manipulation, control, and humanoid motion tracking.
Policies train in parallel GPU simulation and can then be deployed onto physical hardware using the
:doc:`Robots <../../robots/index>`, :doc:`Teleoperation <../teleop>`, :doc:`System Identification <../sysid>`, and
:doc:`Sim-to-Real <../sim2real>` workflows.

Environments
------------

Every environment registered in `mujoco_playground/_src/rl/env_registry.py
<https://github.com/google-deepmind/mujoco_playground/blob/main/mujoco_playground/_src/rl/env_registry.py>`_:

.. list-table::
    :header-rows: 1
    :widths: 30 25 25 20

    * - Environment ID
      - Robot
      - Observations
      - Category
    * - ``SO101PickCube``
      - SO-101
      - State
      - :doc:`manipulation`
    * - ``SO101PickCubeVision``
      - SO-101
      - Vision + State
      - :doc:`manipulation`
    * - ``TrossenPickCube``
      - Trossen WXAI
      - State
      - :doc:`manipulation`
    * - ``TrossenPickCubeVision``
      - Trossen WXAI
      - Vision + State
      - :doc:`manipulation`
    * - ``CartpoleBalance``
      - Cartpole
      - State
      - :doc:`dm_control_suite`
    * - ``CartpoleSwingUp``
      - Cartpole
      - State
      - :doc:`dm_control_suite`
    * - ``CartpoleBalanceVision``
      - Cartpole
      - Vision
      - :doc:`dm_control_suite`
    * - ``G1WholeBodyTracking``
      - Unitree G1
      - State
      - :doc:`whole_body`

Training and Evaluation
-----------------------

Train a PPO policy across batched GPU worlds with ``playground train rsl_rl`` and evaluate checkpoints in the
interactive viewer with ``playground play rsl_rl`` (while your policy trains, you can proceed to
:doc:`Robots <../../robots/index>` to connect and calibrate your hardware):

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=SO101PickCube \
      --logdir=/tmp/rslrl_logs/so101_pick_cube
      # --overrides='{"nworld": 64}'  # For CPU

    uv run --extra rl playground play rsl_rl \
      --env=SO101PickCube \
      --resume_path=/tmp/rslrl_logs/so101_pick_cube

Pass JSON dicts to ``--overrides`` (runner settings) or ``--env_overrides`` (environment config kwargs), or use
``torchrun`` for multi-GPU training:

.. code-block:: bash

    # Customize runner settings
    uv run --extra rl playground train rsl_rl \
      --env=SO101PickCube \
      --overrides='{"max_iterations": 2000, "nworld": 2048}'

    # Multi-GPU training
    uv run --extra rl torchrun --standalone --nnodes=1 --nproc_per_node=2 \
      -m mujoco_playground.rl.rsl_rl.train --env=G1WholeBodyTracking --logdir=/tmp/g1_tracking

Monitoring with TensorBoard
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Training writes TensorBoard event files to ``--logdir``. Launch TensorBoard and open ``http://localhost:6006`` in your
browser to monitor training rewards, episode length, policy entropy, and losses:

.. code-block:: bash

    uv run --extra rl tensorboard --logdir=/tmp/rslrl_logs/so101_pick_cube

.. toctree::
    :hidden:

    Manipulation <manipulation>
    DM Control Suite <dm_control_suite>
    Whole Body <whole_body>
