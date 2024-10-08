# Obol Split: Validator Reward Management

Welcome to the world of Ethereum staking! If you're diving into this space, you may have heard about validator rewards and how they can be managed. One of the most exciting developments in this area is **Obol Splits**. This blog post will break down what Obol Splits are, how they work, and why they matter—all in a beginner-friendly way!

### What Are Obol Splits?

At its core, **Obol Splits** refer to a set of smart contracts that help validators distribute rewards efficiently. But what does that really mean?

#### Why Do We Need Obol Splits?

When you stake ETH as a validator, you earn rewards from two main sources:

1. **Consensus Layer Rewards**: These are the rewards you earn for validating blocks and keeping the network secure.
2. **Execution Layer Rewards**: These come from transaction fees and other activities on the Ethereum network.

Managing these rewards can be complex, especially when multiple parties are involved. Obol Splits make this easier by allowing you to divide ether (ETH) or ERC20 tokens among different addresses, ensuring everyone involved gets their fair share.

### Key Features of Obol Splits

1. **Separation of Funds**: Obol Splits distinguish between the original amount you staked (the principal) and the rewards you earn. This separation simplifies accounting and distribution.
2. **Flexible Distribution**: Depending on your needs, you can configure how rewards are shared among stakeholders—like operators, partners, or other contributors.
3. **Cross-Network Compatibility**: Obol’s contracts are available across multiple Ethereum-compatible networks, making them accessible to a broad audience.

### The Heart of Obol Splits: Key Contract Types

Let’s dive into the main contract types that make Obol Splits work. Think of these contracts as the building blocks of your reward management strategy.

#### 1. Optimistic Withdrawal Recipient (OWR)

The **Optimistic Withdrawal Recipient (OWR)** is a critical component of Obol Splits.

**What Does It Do?**

* **Distributes Rewards**: The OWR directs the rewards you earn from validating transactions to a specified address.
* **Returns Principal**: It ensures that when you want to withdraw, your original stake (the principal) goes back to your designated address.
* **Tracks Ether Distributions**: It monitors the ETH coming into your contract and decides how to allocate it based on simple rules.

**How It Works:**

The OWR uses a straightforward distribution logic:

* **If Balance > 16 ETH**: The contract sends the excess balance to your principal address.
* **If Balance < 16 ETH**: The contract assumes this balance is part of the rewards and sends it to the rewards address.

**Setting Up the OWR**

When you set up an OWR, you'll need to provide:

* A **rewards address** (where your rewards go).
* A **principal address** (where your original stake will be returned).
* The **principal amount** (the amount you initially staked).

#### 2. Split Contracts

**Split contracts** are designed to help you divide your ether or tokens across multiple addresses. This is essential for managing rewards among various stakeholders.

**Types of Split Contracts:**

* **Immutable Splits**: Once deployed, these splits cannot be changed, providing security and predictability.
* **Mutable Splits**: These can be modified later, allowing for flexibility in how rewards are distributed as circumstances change.

#### 3. Split Controllers

**Split controllers** manage how and when you can change your split configurations.

**Types of Controllers:**

* **Permissive Controller**: This allows significant changes to the split configuration, perfect for teams needing flexibility.
* **Immutable Controller**: This permits only a one-time change, which enhances security and stability.

### Contract Addresses Across Different Networks

If you want to get started with Obol Splits, you’ll need to know where to find the relevant contracts on various networks. Here’s a handy list of contract addresses to help you out:

#### Goerli Network Contracts

| Contract Type                        | Address                                      |
| ------------------------------------ | -------------------------------------------- |
| OptimisticWithdrawalRecipientFactory | `0xe9557FCC055c89515AE9F3A4B1238575Fcd80c26` |
| OptimisticWithdrawalRecipient        | `0x898516b26D99d0F389598acFcd9F115Ab8184Fe3` |
| ImmutableSplitControllerFactory      | `0x64a2c4A50B1f46c3e2bF753CFe270ceB18b5e18f` |
| ImmutableSplitController             | `0x009894cdA6cB6d99866ca8E04e8EDeabd625712F` |
| ObolLidoSplitFactory                 | `0x40435F54cc57943C727d8f856A52d4E55501cA8C` |
| ObolLidoSplit                        | `0xdF46B2f36ffb67492A73263Ae3C3849B99DA9967` |

#### Sepolia Network Contracts

| Contract Type                        | Address                                      |
| ------------------------------------ | -------------------------------------------- |
| OptimisticWithdrawalRecipientFactory | `0xca78f8fda7ec13ae246e4d4cd38b9ce25a12e64a` |
| OptimisticWithdrawalRecipient        | `0x99585e71ab1118682d51efefca0a170c70eef0d6` |

#### Holesky Network Contracts

| Contract Type                             | Address                                      |
| ----------------------------------------- | -------------------------------------------- |
| ObolLidoSplitFactory                      | `0x934ec6B68cE7cC3b3E6106C686B5ad808ED26449` |
| ObolLidoSplit                             | `0x22bdC6609de39E569546184Bff4ba4716d34fEBd` |
| OptimisticWithdrawalRecipientFactory      | `0xc0961353fcc43a99e3041db07ac646720e116256` |
| OptimisticWithdrawalRecipient             | `0xa70eb35c1ee7f96688ea5e530ddf1ebedd0c8259` |
| OptimisticTokenWithdrawalRecipientFactory | `0xD6c9f28062834185FF65D61388D9E2d9D804Fc03` |
| OptimisticTokenWithdrawalRecipient        | `0xb927bf07d1686A7Ad06Fae18e632232a8498F0f6` |

#### Mainnet Contracts

| Contract Type                        | Address                                      |
| ------------------------------------ | -------------------------------------------- |
| OptimisticWithdrawalRecipientFactory | `0x119acd7844cbdd5fc09b1c6a4408f490c8f7f522` |
| OptimisticWithdrawalRecipient        | `0xe11eabf19a49c389d3e8735c35f8f34f28bdcb22` |
| ObolLidoSplitFactory                 | `0xA9d94139A310150Ca1163b5E23f3E1dbb7D9E2A6` |
| ObolLidoSplit                        | `0x2fB59065F049e0D0E3180C6312FA0FeB5Bbf0FE3` |
| ImmutableSplitControllerFactory      | `0x49e7cA187F1E94d9A0d1DFBd6CCCd69Ca17F56a4` |
| ImmutableSplitController             | `0xaF129979b773374dD3025d3F97353e73B0A6Cc8d` |

#### Gnosis Chain Mainnet Contracts

| Contract Type                             | Address                                      |
| ----------------------------------------- | -------------------------------------------- |
| OptimisticTokenWithdrawalRecipientFactory | `0x417C41a1A49316dFdC317C1459d04C9959a67972` |
| OptimisticTokenWithdrawalRecipient        | `0xdd94984658d4B9C45dDF1652287c15A672021894` |

#### Gnosis Chain Chiado Contracts

| Contract Type                             | Address                                      |
| ----------------------------------------- | -------------------------------------------- |
| OptimisticTokenWithdrawalRecipientFactory | `0x417C41a1A49316dFdC317C1459d04C9959a67972` |
| OptimisticTokenWithdrawalRecipient        | `0xdd94984658d4B9c45ddf1652287c15a672021894` |

### Conclusion

Obol Splits represent a powerful tool for anyone involved in Ethereum staking. They simplify the process of managing validator rewards, ensuring that funds are distributed fairly and transparently. By separating principal from rewards and allowing flexible configurations, Obol Splits make it easier for validators to operate efficiently.

If you're new to the Ethereum staking ecosystem, understanding these tools is an excellent step toward effectively managing your rewards. Feel free to reach out if you have any questions or need further clarification—happy staking!
