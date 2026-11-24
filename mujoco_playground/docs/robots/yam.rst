I2RT YAM Pro
============

6-DoF + gripper arm with a wrist camera, in simulation (``robots/yam/sim``) and on hardware (``robots/yam/real``).
Used by :doc:`System Identification <../tasks/sysid>` and :doc:`Agentic <../tasks/agentic>`.

Setup
-----

Linux:

.. code-block:: bash

    uv sync --extra yam
    sudo ip link set can0 up type can bitrate 1000000
    uv run --extra yam python -m mujoco_playground.robots.yam.real.get_cameras --identify

macOS (uses ``libusb`` in user space; no ``ip link`` setup needed):

.. code-block:: bash

    brew install libusb
    uv sync --extra yam
    uv run --extra yam python -m mujoco_playground.robots.yam.real.get_cameras --identify

.. note::

    The RealSense D405 exposes multiple color UVC streams on both Linux and macOS. Select the **ISP RGB stream**
    (bright, ``640x480`` ``4:3``, no corner vignetting—``...-video-index4`` on Linux) rather than the raw stereo sensor
    (dark, ``424x240`` ``16:9``, heavy corner vignetting—``...-video-index2`` on Linux).
