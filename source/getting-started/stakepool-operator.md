Getting Started with Stakepool Operations
=========================================

Getting started as stake pool operator

## Creating a stake pool

Stake pools use the Cardano node to validate how the pool interacts with the network, sends transactions, creates blocks, and so on.

## Operating a stake pool

Stake pools are a key part of a decentralized Cardano, supporting the mechanisms that ensure the long-term health and liveness of the network. By running a stake pool, stake pool operators enable other users to participate in the protocol and gain rewards without needing to continuously run an online node.

## Prerequisites for stake pool operators

As a stake pool operator for Cardano, you will typically have the following abilities:

* operational knowledge of how to set up, run and maintain a Cardano node continuously
* a commitment to maintain your node 24/7/365
* system operation skills
* server administration skills (operational and maintenance).
* experience of development and operations (DevOps) would be very useful

## The role of a stake pool operator

When you set up a stake pool or choose to run a node on your own, you are helping to improve the Cardano network’s strength and security. The more independent nodes in the ecosystem, the more copies of the blockchain that exist, therefore the more resilient the Cardano network becomes.

Meanwhile, stake pool owners sign the original registration transaction when creating a stake pool.

## Who can operate a stake pool?

Anyone can register a stake pool, although it requires an individual or team with system administration skills to be able to operate and maintain a pool. The only costs associated with creating a pool is the stake pool registration deposit and the stake key deposit, both of which are eligible for a partial refund. These are configurable values defined in the genesis configuration file and they vary depending on the associated network. For a pool to be competitive, it needs to have a significant amount of stake delegated to it, otherwise the node will run idle and never, or very seldom, create blocks.

## Minimum requirements for running a stake pool

In terms of hardware, you should have the following available:

4 GB of RAM
24 GB of hard disk space
a good network connection and about 1 GB of bandwidth per hour
a public IP4 address
Note that processor speed is not a significant factor for running a stake pool.

## Minimal installation

In order to set up a minimal stake pool, you need a small server that fulfils the hardware requirements and a Shelley node. Although this will work, a stake pool should have close to 100% availability. That means that the node must be online with good internet connection 24/7.

## Recommended setup

We recommend that you have one or more relay nodes, in addition to your Shelley block-producing node. You can check here for network configuration details, as well as genesis and topology files.

## About the stake pool operator keys

It is the responsibility of the operator to manage both the hot (online), and cold (offline) keys for the pool. Cold keys must be secure and should not reside on a device that has internet connectivity. It is recommended that you have multiple backups of your cold keys.

The keys that you need as a stake pool operator are:

* stake pool cold key
* stake pool hot key (KES key)
* stake pool VRF key

The KES key, or hot key as mentioned above, is a node operational key that authenticates who you are. You specify the validity of the KES key using the start time and key period parameters and this KES key needs to be updated every 90 days. The VRF key is a signing verification key and is stored within the operational certificate. You can read more information on these crypto scheme keys in the Shelley ledger specification

## Operational certificates

Stake pool operators must provide an operational certificate to verify that the pool has the authority to run. The certificate includes the operator's signature, and includes key information about the pool (addresses, keys, etc.)

Operational certificates represent the link between the operator's offline key and their operational key. A certificate's job is to check whether or not an operational key is valid, to prevent malicious interference. The certificate identifies the current operational key, and is signed by the offline key.

Certificates are generated with an issue counter number and included in the header of each block the node generates. This mechanism enables nodes to verify whether a certificate is current, or has already been superseded by a newer one. Certificates include a kes-period (start date), which indicates the time span within which the certificate is valid, before you need to create another one. See an example of an operational certificate generation here.

The counter becomes significant when an attacker has compromised the KES key, in which case the owner of the cold keys can create a new KES key and a new certificate with a higher issue number. If a node sees two blocks claiming to originate from the same cold key, but using different KES keys, the higher issue counter trumps the lower one.

Certificates are generated on the offline machine using the offline/cold keys, before being copied over to the node to validate the KES keys used to sign the blocks. You can see an example of a transaction containing certificates here.

## Stake pool metadata

In addition to posting a registration certificate to the blockchain, setting up a stake pool for delegation also involves the provision of metadata, (additional information about the pool).

The registration certificate contains all the necessary information for the execution of the protocol (public key hashes, cost, margin, relays, and pledge), and also contains a hash of the metadata.

If metadata is provided, the end users' wallet will display the stake pool. If metadata is not supplied, the stake pool is considered private, and will not be displayed in a user's wallet.

## Public stake pools

If the registration certificate that is sent by a stake pool operator contains metadata, the stake pool is considered to be public.

Referring to, or pointing to metadata, in the stake pool certificate is optional. The certificate might contain a URL of up to 64 bytes in length that points to a JSON object with the following content:

* a ticker of 3-5 characters, for a compact display of stake pools in a wallet.
* title/name of up to 50 characters.
* short textual description
* URL to a homepage with additional information about the pool (optional).

These are important considerations to note about the metadata:

* metadata information is encoded in UTF-8, and will never exceed 512 bytes
* the content hash of the JSON object referenced in the URL (if present), should match the content hash in the registration certificate. If there is a mismatch, the pool will not be displayed in a wallet.
* for the wallet to display the pool, the following conditions must be met - the registration certificate must refer to the metadata, the metadata must be valid and have the correct content hash, and be available at the URL. It must be possible to get the metadata and validate it. If this process fails, the wallet will not display the pool.
* if a stake pool operator changes the metadata, they must post a new stake pool registration certificate with the new content hash.

## [Metadata proxy servers](source/getting-started/metadata-proxy-servers.md)


### How to create a stake pool

To learn how to setup your own stake pool, please follow the [Tutorials](../cardano-tutorials/readme)

```eval_rst
.. toctree::
   :maxdepth: 3
   :titlesonly:

   metadata-proxy-servers

``
