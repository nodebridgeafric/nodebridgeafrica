# Node Operator and Validator

What do validator nodes actually do?

In short, validator nodes on the Ethereum network _**process transactions and secure the network.**_ This is done via the [proof-of-stake ](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/)consensus mechanism where each validator puts 32 ETH at stake to vouch for the validity of new blocks _- with a bundle of transactions in them -_ that either others or themselves have created.

In exchange for doing the work above, validators receive rewards from both users and the Ethereum protocol directly. However, if validators are **caught acting dishonestly** by other nodes in the network, **their stake is slashed** - forcibly burning their 32 ETH based on the severity of their actions. This mechanism is further explained in the [Rewards and penalties section](broken-reference).

<figure><img src="../.gitbook/assets/image (14) (1).png" alt=""><figcaption><p>Source: <a href="https://github.com/flashbots/mev-boost">https://github.com/flashbots/mev-boost</a></p></figcaption></figure>

