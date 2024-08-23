# Understanding the Ethereum Validator Process

To grasp how transactions are processed and validated on the Ethereum network, let's break down the value chain of the Ethereum validator network.

1. **Transaction Submission and Mempool**:
   * When users interact with decentralized applications (Dapps) or send Ethereum assets, their transactions first enter a holding area known as the **Mempool**. This is where transactions wait before being included in a block.
2. **Role of Block Builders**:
   * **Block Builders** are responsible for assembling transactions into blocks. They retrieve transactions through three main channels:
     * **Observing the Mempool**: Block builders monitor the Mempool directly to gather transactions.
     * **Working with MEV Searchers**: These users look for arbitrage opportunities in the Mempool. They submit their own transactions to capitalize on these opportunities and provide their transaction sets to block builders.
     * **Direct Submissions**: Users can also send their transactions directly to block builders.
3. **Transaction Routing via Relays**:
   * **Relays** connect block builders with the validator network. They use the mev-boost public auction service to allow validators to choose the most profitable transactions based on bids, known as MEV (Maximal Extractable Value) fees.
4. **Transaction Handling by Validators**:
   * Validators receive transactions in two ways:
     * **Directly from the Mempool**: Through their Execution Clients, validators pick up transactions and build blocks locally.
     * **From Relays**: Transactions can also be pre-built into blocks by block builders and sent to validators via Relays.
5. **Block Proposing and Validation**:
   * Every epoch (approximately 6.4 minutes), **32 validators** are randomly selected to propose blocks. Each validator has a roughly 12-second window to propose a block.
   * The proposing validator has around 4 seconds to receive, execute, and broadcast the block.
   * A random committee of validators, known as the **Beacon Committee**, then has about 8 seconds to review and confirm the block's validity.
6. **Finalization**:
   * Once a block is proposed and validated, it is added to the blockchain. At the end of every 2 epochs, all transactions included in the finalized blocks are permanently recorded and cannot be reversed without significant penalties, including the potential burning of staked ETH across the network.
