# Page 10

#### Obol Splits Overview

Obol creates smart contracts for Distributed Validators. These include:

1. **Withdrawal Recipients**: Contracts for a validator’s withdrawal address.
2. **Split Contracts**: Contracts to share ether among different parties, created by Splits.org.
3. **Split Controllers**: Contracts that change how a splitter works.

#### Key Goals for Validator Rewards

1. **Separate Rewards from Principal**: Node operators should be paid from the rewards, not the total of principal plus rewards.
2. **Ongoing Withdrawals**: Rewards should be withdrawable without exiting the validator.

However, due to the way ether is handled and limited access to validator status, achieving these goals is challenging.

#### Withdrawal Recipients

Validators earn two types of rewards: from the consensus layer and the execution layer. Withdrawal Recipients focus on the consensus layer, allowing for ongoing reward collection while keeping the principal safe until the validator is exited.

**Optimistic Withdrawal Recipient**

This is the main type used by Obol. It separates rewards from the principal and allows ongoing reward withdrawals.

When set up, it requires:

* A principal address (where the main ether goes after exit).
* A reward address (for accumulating rewards).
* The amount of ether that is the principal.

The contract assumes that any ether received since the last accounting is a reward unless it's over 16 ether, in which case it is considered part of the principal.

**Risk**: If there are large slashing events (losses), some principal may be misclassified as a reward, leading to incorrect distributions. Users should be aware of this risk.

The alternative is using a Splits.org contract, which only allows rewards to be claimed after returning all principal, meaning validators must exit first.

This contract works well for many validators, but it’s important to process rewards before exiting a validator to avoid misclassification.

#### OWR Factory Deployment

The Optimistic Withdrawal Recipient is deployed via a factory contract at specific addresses across different chains.

#### Exitable Withdrawal Recipient

This feature will allow exiting a validator using just the withdrawal address, reducing the risk of funds being stuck or validators going offline.

#### Split Contracts

A split contract divides ether or ERC20 tokens among various addresses. They often work with withdrawal recipients. Execution layer rewards are sent to a split address via a fee recipient address.

#### Split Controllers

Split contracts can be changed using a controller address, which can allow for different levels of control:

* **Gnosis SAFE Wallet**: A flexible method for managing splits that can update to any valid set of addresses and percentages.
* **Immutable Split Controller**: This allows one-time updates to a split configuration, which can only be triggered by a permitted address.

#### Deployment Addresses for Split Controllers

The addresses for these contracts on different chains are provided for reference.
