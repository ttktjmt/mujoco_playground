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

.. Placeholder until the mjswan Cloud demo is published: then an iframe on
   https://embed.mjswan.com/<id>, and an "Open in a new tab" link to https://mjswan.com/s/<id>.

.. raw:: html

   <div role="img" aria-label="Interactive demo of CartpoleBalance, coming soon"
     style="width: 100%; aspect-ratio: 16 / 9; border-radius: 6px; background: #1f2633;
       color: #c9d1dc; display: flex; flex-direction: column; align-items: center;
       justify-content: center; gap: 0.5rem; text-align: center; font-size: 0.95rem;
       box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.08); margin-bottom: 1.15rem;">
     <svg width="48" height="48" viewBox="0 0 48 48" aria-hidden="true">
       <circle cx="24" cy="24" r="22" fill="none" stroke="currentColor" stroke-width="2"/>
       <path d="M19 15 L34 24 L19 33 Z" fill="currentColor"/>
     </svg>
     <span>Interactive demo: CartpoleBalance</span>
     <span style="opacity: 0.65; font-size: 0.85rem;">Coming soon on mjswan Cloud</span>
   </div>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleBalance \
      --logdir=/tmp/rslrl_logs/cartpole_balance

CartpoleSwingUp
---------------

Starts with the pole hanging down, so the policy has to swing it up first.

.. Placeholder until the mjswan Cloud demo is published: then an iframe on
   https://embed.mjswan.com/<id>, and an "Open in a new tab" link to https://mjswan.com/s/<id>.

.. raw:: html

   <div role="img" aria-label="Interactive demo of CartpoleSwingUp, coming soon"
     style="width: 100%; aspect-ratio: 16 / 9; border-radius: 6px; background: #1f2633;
       color: #c9d1dc; display: flex; flex-direction: column; align-items: center;
       justify-content: center; gap: 0.5rem; text-align: center; font-size: 0.95rem;
       box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.08); margin-bottom: 1.15rem;">
     <svg width="48" height="48" viewBox="0 0 48 48" aria-hidden="true">
       <circle cx="24" cy="24" r="22" fill="none" stroke="currentColor" stroke-width="2"/>
       <path d="M19 15 L34 24 L19 33 Z" fill="currentColor"/>
     </svg>
     <span>Interactive demo: CartpoleSwingUp</span>
     <span style="opacity: 0.65; font-size: 0.85rem;">Coming soon on mjswan Cloud</span>
   </div>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleSwingUp \
      --logdir=/tmp/rslrl_logs/cartpole_swingup

CartpoleBalanceVision
---------------------

Balances from pixels alone.

.. Placeholder until the mjswan Cloud demo is published: then an iframe on
   https://embed.mjswan.com/<id>, and an "Open in a new tab" link to https://mjswan.com/s/<id>.

.. raw:: html

   <div role="img" aria-label="Interactive demo of CartpoleBalanceVision, coming soon"
     style="width: 100%; aspect-ratio: 16 / 9; border-radius: 6px; background: #1f2633;
       color: #c9d1dc; display: flex; flex-direction: column; align-items: center;
       justify-content: center; gap: 0.5rem; text-align: center; font-size: 0.95rem;
       box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.08); margin-bottom: 1.15rem;">
     <svg width="48" height="48" viewBox="0 0 48 48" aria-hidden="true">
       <circle cx="24" cy="24" r="22" fill="none" stroke="currentColor" stroke-width="2"/>
       <path d="M19 15 L34 24 L19 33 Z" fill="currentColor"/>
     </svg>
     <span>Interactive demo: CartpoleBalanceVision</span>
     <span style="opacity: 0.65; font-size: 0.85rem;">Coming soon on mjswan Cloud</span>
   </div>

.. code-block:: bash

    uv run --extra rl playground train rsl_rl \
      --env=CartpoleBalanceVision \
      --logdir=/tmp/rslrl_logs/cartpole_balance_vision
