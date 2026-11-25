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

.. raw:: html

   <iframe
     src="https://embed.mjswan.com/uL7vOT4"
     title="CartpoleBalance, interactive demo (mjswan)"
     style="display: block; width: 100%; aspect-ratio: 16 / 9; border: 0; border-radius: 6px;"
     allow="xr-spatial-tracking"
     allowfullscreen
   ></iframe>
   <p><a href="https://mjswan.com/s/uL7vOT4" target="_blank" rel="noopener">Open in a new tab ↗</a></p>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleBalance \
      --logdir=/tmp/rslrl_logs/cartpole_balance

CartpoleSwingUp
---------------

Starts with the pole hanging down, so the policy has to swing it up first.

.. raw:: html

   <iframe
     src="https://embed.mjswan.com/1LfFYbe"
     title="CartpoleSwingUp, interactive demo (mjswan)"
     style="display: block; width: 100%; aspect-ratio: 16 / 9; border: 0; border-radius: 6px;"
     allow="xr-spatial-tracking"
     allowfullscreen
   ></iframe>
   <p><a href="https://mjswan.com/s/1LfFYbe" target="_blank" rel="noopener">Open in a new tab ↗</a></p>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleSwingUp \
      --logdir=/tmp/rslrl_logs/cartpole_swingup

CartpoleBalanceVision
---------------------

Balances from pixels alone.

.. raw:: html

   <iframe
     src="https://embed.mjswan.com/kiCPtat"
     title="CartpoleBalanceVision, interactive demo (mjswan)"
     style="display: block; width: 100%; aspect-ratio: 16 / 9; border: 0; border-radius: 6px;"
     allow="xr-spatial-tracking"
     allowfullscreen
   ></iframe>
   <p><a href="https://mjswan.com/s/kiCPtat" target="_blank" rel="noopener">Open in a new tab ↗</a></p>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleBalanceVision \
      --logdir=/tmp/rslrl_logs/cartpole_balance_vision
