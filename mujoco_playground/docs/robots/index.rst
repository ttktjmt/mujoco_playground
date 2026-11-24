Robots
======

Each robot in ``mujoco_playground/robots/<robot>/`` includes a simulation model (``sim/``) and, for supported hardware,
drivers and setup utilities (``real/``) that share the same joint ordering and control interface.

.. list-table::
    :header-rows: 1
    :widths: 20 15 20 45

    * - Robot
      - Modes
      - Hardware Extra
      - Description
    * - :doc:`SO-101 <so101>` (``robots/so101``)
      - ``sim``, ``real``
      - ``--extra so101``
      - 5-DoF + gripper follower and leader arms with wrist camera.
    * - :doc:`I2RT YAM Pro <yam>` (``robots/yam``)
      - ``sim``, ``real``
      - ``--extra yam``
      - 6-DoF + gripper arm with wrist camera.
    * - :doc:`Trossen WXAI <trossen_wxai>` (``robots/trossen_wxai``)
      - ``sim``
      - —
      - 6-DoF + gripper tabletop manipulation arm.
    * - :doc:`Unitree G1 <g1>` (``robots/g1``)
      - ``sim``
      - —
      - 29-DoF humanoid robot for whole-body motion tracking.

.. toctree::
    :hidden:

    SO-101 <so101>
    I2RT YAM Pro <yam>
    Trossen WXAI <trossen_wxai>
    Unitree G1 <g1>
