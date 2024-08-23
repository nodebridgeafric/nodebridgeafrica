# Node Setup and Configuration Guide

## Node Setup and Configuration Guide

**1. Choose Your OS and Hardware**

* **OS:** Decide on the operating system for your computer. This system will generate your keys and does not need to be the OS used for your node.
* **Hardware:** Acquire hardware (laptop, desktop, server) or rent a VPS. As of May 2022, you need \~1TB for the Mainnet execution chain data (growing at >1GB/day). CPU and RAM requirements vary; research different clients if you have resource constraints.

**2. Internet Connection**

* Ensure a reliable, high-bandwidth connection (ideally 24/7) with no throttling or caps. As of May 2022, expect \~1.2-1.3 GB download and \~0.9-1 GB upload per hour. Being offline for brief periods incurs minor penalties but can be recovered. Complicated power backups can be costly, and redundant backups might lead to slashing penalties.

**3. Node Security**

* Secure your root account, set up a firewall, and configure port forwarding.

**4. Configure Time Sync**

* Sync server time with the wall clock. Use NTP or Chrony if necessary, especially in VMs which may disable NTP by default.

**5. Execution Client Layer**

* Choose and install an execution client (e.g., Nethermind, Reth, Besu, Erigon, Geth). Syncing may take a few days. Ensure you operate both an execution client and a consensus client.

**6. Consensus Client Layer**

* Choose and install a consensus client (e.g., Nimbus, Teku, Prysm, Lighthouse). Avoid running your validator in multiple locations to prevent slashing.

**7. Generate a Validator Key**

* Generate a validator key using a CLI app, GUI app, or build from source.

**8. JWT Authentication**

* Set up a JWT shared key for secure communication between the execution client and consensus client. Refer to the documentation for specific clients: Lighthouse | Nimbus | Prysm | Teku and Besu | Erigon | Geth | Nethermind | Reth.

**9. Set Withdrawal Address**

* Provide a withdrawal address with your deposit to enable reward payments and full fund withdrawal. This address is permanent and must be a regular Ethereum address. Funds will be locked until this address is set.

**10. Set Fee Recipient**

* Provide a fee recipient address to receive transaction fee rewards. This address must be configured in your consensus client. See specific documentation for setting this up: Lighthouse | Nimbus | Prysm | Teku.

**11. Consensus Layer Beacon Node (BN)**

*   Connect your consensus client to the execution client via HTTP API and sync your beacon node. Ensure it has more than 20 peers. Verify with:

    ```bash
    curl -H "Content-Type: application/json" -X POST --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":67}' http://<YourServerLocation>:8545
    ```

**12. Consensus Layer Validator Client (VC)**

* Import your keystore(s) into the validator client and ensure it’s stored on only one machine. Start your validator client.

**13. Wallet Setup and Deposit ETH**

* Set up a wallet, deposit ETH, and use monitoring software to protect your funds. Upload the deposit data file (`deposit_data-[timestamp].json`) to the Staking Launchpad website.

**14. Optional Recommendations**

* **Monitoring:** Use Prometheus and Grafana to visualize real-time metrics. Set up Prometheus, Grafana, and import dashboard configs. Monitoring docs: Lighthouse | Nimbus | Prysm | Teku
* **Testnet Simulations:** Practice scenarios like stopping/restarting the Beacon Node and Validator Client, handling power loss, and client migrations.
* **Advanced System Architecture:** Use a VPN to protect your IP address. Consider separating your Validator Client and Beacon Node on different machines and IPs.
* **Graffiti:** Add a personal touch to your blocks using the graffiti flag in your validator client. Check it using Beaconcha.in or BeaconScan.
