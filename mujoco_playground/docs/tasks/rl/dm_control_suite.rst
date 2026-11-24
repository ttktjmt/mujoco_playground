DM Control Suite
================

``tasks/dm_control_suite``: the cart-pole of the `DeepMind Control Suite <https://github.com/google-deepmind/dm_control>`_,
a cart on a rail that keeps a hinged pole upright.

.. list-table::
    :header-rows: 1
    :widths: 30 45 25

    * - Environment ID
      - Observations
      - Control
    * - ``CartpoleBalance``
      - State
      - 100 Hz
    * - ``CartpoleSwingUp``
      - State
      - 100 Hz
    * - ``CartpoleBalanceVision``
      - Grayscale image from a fixed camera (64×64)
      - 50 Hz

CartpoleBalance
---------------

Starts with the pole close to upright.

.. mjswan demo goes here once published (https://embed.mjswan.com/<id>).

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleBalance \
      --logdir=/tmp/rslrl_logs/cartpole_balance

CartpoleSwingUp
---------------

Starts with the pole hanging down, so the policy has to swing it up first.

.. mjswan demo goes here once published (https://embed.mjswan.com/<id>).

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleSwingUp \
      --logdir=/tmp/rslrl_logs/cartpole_swingup

CartpoleBalanceVision
---------------------

Balances from pixels alone.

.. mjswan demo goes here once published (https://embed.mjswan.com/<id>).

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleBalanceVision \
      --logdir=/tmp/rslrl_logs/cartpole_balance_vision
