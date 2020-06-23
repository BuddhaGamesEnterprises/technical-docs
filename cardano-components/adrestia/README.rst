========
Adrestia
========

Adrestia is a collection of products which makes it easier to integrate with Cardano. It comes in different flavours: SDK or high-level APIs. Depending on the use-cases you have and the control that you seek, you may use any of the components below.

APIs
----

+--------------------+------------------------------------------------+----------------------------------+--------------------------------------+----------------------------+
|    Name / Link     |                  Description                   |              Byron               |                 Jörm                 |           Shell            |
+====================+================================================+==================================+======================================+============================+
| `cardano-wallet`_  | JSON/REST API for managing UTxOs in HD wallets | .. image:: icon/check-circle.svg | .. image:: icon/check-circle.svg     | .. image:: icon/hammer.svg |
+--------------------+------------------------------------------------+----------------------------------+--------------------------------------+----------------------------+
| `cardano-rest`_    | JSON/HTTP API for browsing on-chain data       | .. image:: icon/check-circle.svg | .. image:: icon/dash-circle-fill.svg | .. image:: icon/hammer.svg |
+--------------------+------------------------------------------------+----------------------------------+--------------------------------------+----------------------------+
| `cardano-graphql`_ | GraphQL/HTTP API for browsing on-chain data    | .. image:: icon/check-circle.svg | .. image:: icon/dash-circle-fill.svg | .. image:: icon/hammer.svg |
+--------------------+------------------------------------------------+----------------------------------+--------------------------------------+----------------------------+


SDKs
----

+------------------------------+--------------------------------------------------------------------------+--------------------------------------+--------------------------------------+
|         Name / Link          |                               Description                                |               Haskell                |              Javascript              |
+==============================+==========================================================================+======================================+======================================+
| `beck32`_                    | Human-friendly Bech32 address encoding                                   | .. image:: icon/check-circle.svg     | `bitcoinjs/bech32`_                  |
+------------------------------+--------------------------------------------------------------------------+--------------------------------------+--------------------------------------+
| `cardano-addresses`_         | Addresses and mnemonic manipulation & derivations                        | .. image:: icon/check-circle.svg     | .. image:: icon/hammer.svg           |
+------------------------------+--------------------------------------------------------------------------+--------------------------------------+--------------------------------------+
| `cardano-coin-selection`_    | Coin selection and fee balancing algorithms                              | .. image:: icon/check-circle.svg     | .. image:: icon/hammer.svg           |
+------------------------------+--------------------------------------------------------------------------+--------------------------------------+--------------------------------------+
| `cardano-launcher`_          | Shelley cardano-node and cardano-wallet launcher for NodeJS applications | .. image:: icon/dash-circle-fill.svg | .. image:: icon/dash-circle-fill.svg |
+------------------------------+--------------------------------------------------------------------------+--------------------------------------+--------------------------------------+
| `cardano-serialization-lib`_ | Binary serialization of on-chain data types                              | .. image:: icon/hammer.svg           | .. image:: icon/hammer.svg           |
+------------------------------+--------------------------------------------------------------------------+--------------------------------------+--------------------------------------+
| `cardano-transactions`_      | Transaction construction and signing                                     | .. image:: icon/check-circle.svg     | .. image:: icon/hammer.svg           |
+------------------------------+--------------------------------------------------------------------------+--------------------------------------+--------------------------------------+

Formal Specifications
---------------------

+------------------------------+----------------------------------------+
|         name / link          |              description               |
+==============================+========================================+
| `utxo-wallet-specification`_ | Formal specification for a UTxO wallet |
+------------------------------+----------------------------------------+


Internal
--------

:warning: Here be dragons. These tools are used internally by other tools and does not benefit from the same care in documentation than other tools above.

+-------------------+----------------------------------------------------------------------+
|    name / link    |                             description                              |
+===================+======================================================================+
| `cardano-js`_     | (experimental) Cardano primitives for ECMAScript applications        |
+-------------------+----------------------------------------------------------------------+
| `cardano-js-sdk`_ | (experimental) Cardano SDK for ECMAScript applications               |
+-------------------+----------------------------------------------------------------------+
| `persistent`_     | Fork of the persistent Haskell library maintained for cardano-wallet |
+-------------------+----------------------------------------------------------------------+

.. _Adrestia user-guide: https://input-output-hk.github.io/adrestia/
.. _cardano-wallet: https://github.com/input-output-hk/cardano-wallet
.. _cardano-rest: https://github.com/input-output-hk/cardano-addresses
.. _cardano-graphql: https://github.com/input-output-hk/cardano-addresses

.. _beck32: https://input-output-hk.github.io/adrestia/
.. _bitcoinjs/bech32: https://github.com/input-output-hk/cardano-wallet
.. _cardano-addresses: https://github.com/input-output-hk/cardano-addresses
.. _cardano-coin-selection: https://github.com/input-output-hk/cardano-coin-selection
.. _cardano-launcher: https://github.com/input-output-hk/cardano-launcher
.. _cardano-serialization-lib: https://github.com/input-output-hk/cardano-serialization-lib
.. _cardano-transactions: https://github.com/input-output-hk/cardano-transactions

.. _utxo-wallet-specification: https://github.com/input-output-hk/utxo-wallet-specification

.. _cardano-js: https://github.com/input-output-hk/cardano-js
.. _cardano-js-sdk: https://github.com/input-output-hk/cardano-js-sdk
.. _persistent: https://github.com/input-output-hk/persistent