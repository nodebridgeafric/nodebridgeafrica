# Introduction to SSV.Network

### What is SSV.Network?

SSV.Network is a decentralized, open-source platform designed for Ethereum staking that utilizes Secret Shared Validator (SSV) technology, also known as Distributed Validator Technology (DVT). This innovative framework splits a validator key into multiple KeyShares, enabling Ethereum validators to operate securely across several independent nodes. By doing so, SSV.Network enhances security and redundancy while fostering a healthier Ethereum ecosystem.

#### Key Benefits

* **Active-Active Redundancy and fault tolerance**: Ensures that validators can continue to operate even if some nodes experience downtime, improving reliability.
* **Enhanced Security**: By splitting validator keys, the risk of a single point of failure is significantly reduced.
* **Support for Diverse Users**: Accommodates staking pools, services, and solo stakers, enhancing overall participation in the Ethereum network.

### Key Components of SSV Configuration

#### 1. Distributed Key Generation

This process involves multiple operators running SSV instances to create a shared public and private key set. Each operator retains a segment of the private key, ensuring that no single entity has full control over the validator key.

#### 2. Shamir Secret Sharing

A cryptographic technique that allows the reconstruction of a validator key using a specified number of KeyShares. This method tolerates failures, ensuring that the protocol can still function even if some KeyShares are unavailable.

#### 3. BLS Signatures

Boneh-Lynn-Shacham (BLS) signatures allow for the aggregation of multiple signatures into a single validator key signature. By combining Shamir and BLS - the keys are 'broken down' to share and regrouped whenever a duty is assigned. This enhances both security and flexibility in how duties are assigned among operators.

#### 4. Multi-Party Computation (MPC)

MPC allows for the secure distribution of KeyShares among multiple operators, enabling them to compute validator duties collectively without needing to reconstruct the validator key on a single device.

#### 5. Istanbul Byzantine Fault Tolerance (IBFT) Consensus

IBFT is a consensus mechanism that randomly selects a validator node to propose blocks, ensuring that consensus can still be reached even if some operators are faulty or offline.

### Network Overview

The SSV.Network ecosystem is composed of three main participants:

* **Stakers**: Individuals or services that utilize SSV/DVT technology to enhance the security and decentralization of their validators. Stakers pay fees in SSV tokens to operators for their services.
* **Operators**: These participants provide the necessary hardware, run the SSV protocol, and maintain the validators. Operators set their own fees in SSV tokens for managing validators.
* **DAO Members**: Members of the decentralized autonomous organization (DAO) that governs the SSV.Network protocol and treasury. DAO members make decisions and allocate funds based on proposals made by $SSV token holders.

### SSV Token

The native token of SSV.Network, $SSV, serves two primary purposes:

* **Payments**: Stakers use $SSV to compensate operators for managing their validators.
* **Governance**: Token holders participate in governance, making decisions and allocating treasury funds.

### Tokenomics

* **Facilitates Transactions**: The $SSV token acts as the medium of exchange between stakers and operators.
* **Revenue Generation**: As more ETH is staked, both operators and the DAO treasury benefit from increased revenues, promoting network growth.

<figure><img src=".gitbook/assets/image (27).png" alt=""><figcaption><p>Operators earn SSV payments and generate ETH rewards for stakers. Stakers pay SSV and receive the generated ETH rewards in return.</p></figcaption></figure>

### Governance

The SSV.Network DAO decentralizes ownership and governance of the protocol. Holding $SSV tokens allows participants to engage in votes and proposals. The DAO implements its governance functions through a multi-signature setup and decisions made by token holders.

### Operator Onboarding

#### Steps to Become an Operator:

1. **Run an SSV Node**: Install the required software to run the SSV protocol on your hardware.
2. **Register**: Complete registration through the network’s smart contracts or via the web interface.

### Fee Configuration

* **Setting Fees**: Operators can determine their fees based on the number of validators they manage. Fees are presented as annual payments but are paid continuously as validators produce blocks.
* **Fee Adjustment**: Operators can modify their fees anytime through a two-step process:
  1. **Declare New Fee**: Broadcast to the network about the proposed fee increase.
  2. **Execute Fee Change**: After a specified period, finalize the fee change. Increases are capped at 10% per cycle to protect stakers.

### Verified Operators

Verified Operators (VOs) are a curated group recognized for their reliability and performance. This list typically includes reputable companies with experience in proof-of-stake (PoS) staking and blockchain infrastructure.

#### Selection Criteria:

* Operate a minimum of 10 active validators.
* Maintain performance above 98%.
* Use the latest version of node software.

### Permissioned Operators

Permissioned Operators restrict validator registrations to a specific list of wallet addresses, enhancing privacy and compliance.

#### Benefits:

* **Exclusive Infrastructure**: Ideal for private staking services or specialized fee structures.
* **Controlled Access**: Improves operational efficiency by limiting public engagement.

### Validator Onboarding Guide

Validators are managed within Clusters, which are groups of selected operators. To run a validator via the SSV network, users must distribute their validator key to their chosen cluster and register it with the network’s smart contract.

#### Supported Cluster Sizes

The cluster size affects fault tolerance. The following configurations are supported:

* **4 Operators**: Tolerates 1 faulty operator.
* **7 Operators**: Tolerates 2 faulty operators.
* **10 Operators**: Tolerates 3 faulty operators.
* **13 Operators**: Tolerates 4 faulty operators.

#### Factors to Consider When Choosing Operators:

* **Reputation**: Prefer verified operators with a proven track record.
* **Performance**: Regularly monitor performance metrics to ensure reliability.
* **Diversification**: Use a mix of technology stacks, cloud providers, and geographic locations for increased resilience.

### Validator Rewards

The SSV.Network is non-custodial, meaning stakers retain full custody of their rewards.

#### Types of Rewards:

* **Consensus Layer Rewards**: Earned for participating in Ethereum’s consensus mechanism.
* **Execution Layer Rewards**: Include priority fees and MEV (Maximum Extractable Value) rewards, which are accessible immediately.

#### Fee Recipient Address

Stakers can designate a specific address to receive execution layer rewards, ensuring rewards are directed appropriately regardless of operator actions.

### Clusters Overview

Clusters are vital for managing distributed validators. They facilitate coordination among operators, handle fee payments, and support overall management.

#### Example of Clusters:

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* **Cluster #1**: Manages 3 validators with Operators 1, 2, 3, 4, 5, 6, 7.
* **Cluster #2**: Manages 1 validator with Operators 1, 2, 3, 4.

#### Cluster Balance

Maintaining a healthy balance is crucial to ensure continuous operation. The cluster balance includes:

* **Liquidation Threshold**: A required collateral balance to cover operational costs.
* **Operational Runway**: Additional funds to extend operational capacity.

#### Liquidation Threshold Calculation:

<figure><img src=".gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

#### Operational Runway Calculation:

The operational runway is any additional funds added to the cluster balance that prolongs the operation of its validators. This means that all extra funds added to the cluster balance on top of the required collateral will increase its operational runway.

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Since operator and network fees are dynamic, the required liquidation collateral and operational runway could vary between different clusters.

The cluster balance needs to be kept in check to ensure the continued operation of its validator(s). To manage cluster balances, users can deposit or withdraw funds at will.

### Managing Cluster Balances

#### Deposits

Increasing the cluster balance helps avoid liquidation and ensures a longer operational runway.

#### Withdrawals

Withdrawals can enhance capital efficiency but cannot include liquidation collateral. Only excess funds can be withdrawn to maintain validator operations.

#### Reactivating Liquidated Clusters

To reactivate a liquidated cluster, users must provide the required liquidation collateral and ideally add more to ensure an operational runway.

#### Conclusion

Clusters are essential for the efficient management of distributed validators. Monitoring balances, maintaining sufficient collateral, and managing deposits and withdrawals are critical for avoiding liquidation and ensuring continuous validator functionality. By leveraging SSV.Network, participants can enhance the security and efficiency of their Ethereum staking operations while contributing positively to the Ethereum ecosystem.
