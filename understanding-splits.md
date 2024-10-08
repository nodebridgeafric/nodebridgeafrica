---
hidden: true
---

# Understanding Splits

In the ever-evolving world of blockchain technology, managing on-chain revenue can be both complex and cumbersome. Enter **Splits**—a revolutionary tool designed to simplify this process. In this blog post, we’ll break down what Splits is, how it works, and why it’s an essential tool for anyone looking to manage decentralized finances (DeFi).

### What is Splits?

Splits is a set of composable, open-source, and audited smart contracts that allows users to manage and distribute on-chain revenue with ease. Think of it as a financial tool that helps you share your earnings fairly among multiple recipients, whether they are team members, collaborators, or stakeholders.

<figure><img src=".gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

#### Key Features of Splits

1. **Autonomous Hyperstructure**: Splits operates as a hyperstructure, meaning it runs perpetually without the need for ongoing maintenance or trusted third parties. It charges no protocol fees and operates solely on gas costs.
2. **Equity Instrument**: With Splits, you can define what percentage of future revenue each recipient will earn, providing a clear and transparent distribution mechanism.
3. **Composability**: Each Split contract can interact with other on-chain contracts, making it a versatile component in the DeFi ecosystem.

### How Does Splits Work?

#### The Structure of a Split

A Split is essentially a smart contract that holds funds (in ETH or ERC20 tokens) and distributes them to defined recipients. Here’s how it operates:

1. **Creating a Split**:
   * When creating a Split, you specify multiple recipients and their corresponding ownership percentages. For instance, if you have three collaborators, you might allocate 50% to one, 30% to another, and 20% to the last.
2. **Receiving Funds**:
   * Any ETH or ERC20 tokens sent to the Split contract are held in its balance. These funds can only be distributed once a distribution function is called.
3. **Distribution**:
   * When you call `distributeETH` or `distributeERC20`, the contract automatically calculates the shares for each recipient based on their pre-set ownership percentages and transfers the appropriate amounts.

#### Smart Contract Mechanics

* **On-Chain Storage**: Recipient details, ownership percentages, and any associated fees are stored on-chain, ensuring transparency and reliability.
* **Proxy and Minimal Contracts**: Each Split has a unique address and uses a proxy pattern to enhance composability. This setup minimizes gas costs during fund transfers, making it efficient and cost-effective.
* **Central Fund Pooling**: All incoming funds are accumulated in a central contract (referred to as SplitMain) until a recipient withdraws their share, simplifying the management of multiple revenue streams.

### Why Use Splits?

#### Benefits for Creators and Teams

1. **Simplicity**: Managing revenue distribution manually can be tedious. Splits automates the entire process, allowing you to focus on your work rather than financial logistics.
2. **Transparency**: All transactions and distribution mechanisms are recorded on-chain, providing a transparent audit trail for all parties involved.
3. **Flexibility**: Whether you’re a freelancer, a startup, or part of a larger organization, Splits can be tailored to suit various revenue-sharing arrangements.
4. **Cost-Effective**: With no protocol fees and a focus on gas efficiency, Splits is an economical choice for revenue management in the DeFi landscape.

### Getting Started with Splits

To start using Splits, you’ll need a basic understanding of Ethereum and how to interact with smart contracts. Here’s a simple step-by-step guide:

1. **Set Up a Wallet**: First, ensure you have a crypto wallet (like MetaMask) that supports ETH and ERC20 tokens.
2. **Create a Split**: Use an interface or platform that integrates with Splits to create a new Split contract. Input the recipient addresses and their ownership percentages.
3. **Send Funds**: Transfer ETH or ERC20 tokens to your Split contract.
4. **Distribute Funds**: When you’re ready, call the distribution function to allocate funds to the recipients based on their shares.
5. **Monitor Transactions**: Keep track of your Split’s activity on a blockchain explorer to ensure everything is operating smoothly.

### Conclusion

Splits offers a powerful and efficient way to manage on-chain revenue distribution. Its combination of transparency, flexibility, and cost-effectiveness makes it an invaluable tool for anyone operating within the decentralized finance space. Whether you’re a creator, a business owner, or part of a collaborative project, understanding and utilizing Splits can streamline your financial processes and foster fair revenue sharing.
