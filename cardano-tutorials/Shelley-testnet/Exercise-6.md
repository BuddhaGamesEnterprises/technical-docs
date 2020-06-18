# Shelley Stakepool Exercise Sheet 6

LATEST TAG: 1.13.0

## Stake Pool Parameters and Protocol Parameters

In the [fifth exercise](Exercise-5.md),
we registered a stake pool, pledged to it, started it and produced blocks.

In this exercise, we will investigate some additional pool parameters.

You may have already done some of these exercises as optional exercises on
[Exercise Sheet 5](Exercise-5.md). Feel free to skip these if so.

### Prerequisites

1. 	Complete [Exercise Sheet 5](Exercise-5.md).
2. 	Read the
    [Cardano Tutorial Documentation](https://github.com/input-output-hk/cardano-tutorials)
    and [General Documentation on Stake Pool Parameters, Pool De-Registration and Protocol Parameters](https://testnets.cardano.org).
4. 	Update your instances of *cardano-node* and *cardano-cli* if you need to.
5. 	Start a relay node and your stake pool from [Exercise Sheet 5](Exercise-5.md).

### Objectives

In the sixth exercise, we will make sure that you can:

1. 	Run multiple stake pools;
2. 	Vary the stake pool parameters;
3. 	Retire Stake Pools.

As before, if you have any questions or encounter any problems, please feel free to use the dedicated Cardano Forum channel.  IOHK staff will be monitoring the channel, and other pool operators may also be able to help you.


### Exercises

1. 	Create a new set of hot keys for your stake pool and restart it with those keys.

2. 	Register and start a second stake pool, as you did in [Exercise 5](Exercise-5.md).
    You can connect the pool to the same relay node as your first stake pool if you like,
    but you should give it different port connections (e.g. 127.0.0.1:4244)
    and may need to update your local topology.
    You will need new cold and hot keys for this pool, plus a new operational certificate.
    Do not attempt to replicate the keys and certificates from your original pool.
    This will make you an adversarial pool.

    As before, you will need to decide on the three key settings: *cost*, *margin* and *pledge*.
    Set these to different values from your main pool.

    Pledge the required ada to your pool if you didn’t do that when you registered it
    (you did remember not to pledge all your ada to your first pool, didn’t you?).

3. 	Advertise the new pool cost and margin settings,
    as well as those for your original pool.

    __Note:__ At the time of writing, proper pool id's have not been implemented yet.
    Please use the CBOR-hex from the cold key verification file instead.

4. 	Change the parameters for your original pool.
    Increase the cost by 10,000 ada and set the margin to 20%.
    Choose a suitable pledge value.
    Advertise these new settings.

5. 	We will change the following general protocol parameter settings over the course of a few epochs:

    1.  Saturation threshold (`k`);
    2.  Influence factor (`a0`);
    3.  Decentralisation parameter (`d`);
    4.  Protocol version.

    Determine how these general settings affect your pool operation and rewards.
    Has your pool become saturated at any point?
    Did you need to change your pledge?

6.  _Optional Exercise (Easy)._

    Persuade 5 or more additional Testnet users to delegate to your pools.
    Check your rewards.
    Compete with other Testnet Stakepool operators to offer the most attractive pool.

7. 	_Optional Exercise (Medium)._

    De-register the stake key that you used for the pledge on one of your pools.
    What effect does this have, and how do you recover your pool to a normal operating state?

8. 	_Optional Exercise (Easy to Medium)._

    Work with other Testnet stakepool operators to explore the network topology
    by testing connections between relays within and across different countries and continents.
    What is the longest connection you can make and still have a good chance of producing blocks?
    What is the optimal node setup? Is network bandwidth more important than latency?
    Does CPU speed and/or memory make a difference?
    Is SSD or a hard disk faster?
    Are there other important factors that affect the stake pool operation?

9. 	_Optional Exercise (Medium)._

    Explore the use of GHC’s parallelism and memory management runtime parameters
    to tune the performance of your node. For example,

    -   run on two cores, send statistics to the standard error output

            cardano-node ... +RTS -N2 -Sstderr

    -   use 3 generations for garbage collection

            cardano-node ... +RTS -G3

    -   use the parallel garbage collector

            cardano-node … +RTS -qg

    Share your findings with the other Stakepool operators.
    Note that you may need to add the `-rtsopts` flag to the `cabal install`
    to be able to use some of the tuning options.

    __Warning:__ If you choose the wrong settings,
    the node may have insufficient memory and may fail to run, or may run extremely slowly.
    Feel free to experiment, but be careful with the settings for your live pool and relay!
    The default ones will generally give reasonable performance.

10. _Optional Exercise (Medium to Hard)._

    Run a stake pool on a different OS (e.g. MacOS, FreeBSD or a different flavour of Linux),
    perhaps under a Virtual Machine.
    Integrate this stake pool into the Shelley Testnet.
    NB: do not try to run a stake pool on Windows unless you are very experienced –
    there are many networking issues you could encounter, for example –
    you will probably find it easiest to use the Windows Subsystem for Linux (WSL) if you do this.


You have now learnt the rudiments of how to operate a stake pool,
and can consider yourself to be a Graduate Stakepool Operator.
Congratulations!


### Feedback

Please provide any feedback or suggested changes to the tutorials or exercises by either raising an issue on the [cardano-tutorials repository](https://github.com/input-output-hk/cardano-tutorials) or by forking the repository and submitting a PR.

Please provide any feedback or suggested changes on the node itself by raising an issue at the [cardano-node repository](https://github.com/input-output-hk/cardano-node).
