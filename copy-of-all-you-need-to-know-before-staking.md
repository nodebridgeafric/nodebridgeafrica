---
hidden: true
---

# Copy of All you need to know before staking

1. Decide and Choose the OS of the computer you'll be using. This will be the computer you use to generate your keys. It doesn't need to be the OS you want to use for your node.Acquire some hardware (laptop, desktop, server) that meets this specification or rent a VPS (cloud server). As of May 2022, you'll need \~1TB for the Mainnet execution chain data alone (growing at >1GB/day). CPU and RAM resource usage can vary significantly between clients. Research the different clients if you're working with resource constraints.
2. Internet: Ideally your internet connection should be reliable and as close to 24/7 as possible without interruption. Ensure your bandwidth can't be throttled and isn't capped so your node stays in sync and will be ready to validate when called. You need enough upload bandwidth too. As of May 2022 this is \~1.2-1.3 GB download and \~0.9-1 GB upload per hour, and is likely to increase. Being offline for brief periods of time will result in small inactivity penalities, but will be recouped easily after being online again for about the same amount of time. Complicated power backups can add to the expense of your setup, and redundant backup validators can lead to a more serious penalty known as slashing.
3. Node security: secure root account, setup firewall, and forward network request to designated port (port forwarding)
4. Configure time sync: ensure your server time is in sync with the wall clock. The RTC (Real-Time Clock) time may be set to your local timezone instead of UTC, especially in a VM which has its clock configured on Windows. you may need to install chrony or ntp package. by default, VMs may disable NTP so you may need to find a work-around for your environment.
5.  Choose and Configure your execution client layer.  Choose your execution client and set up a node

    To process incoming validator deposits from the execution layer (formerly 'Eth1' chain), you'll need to run an execution client as well as your consensus client (formerly 'Eth2'). Install and Sync your preferred execution layer client. Syncing your execution client may take a few days in the worst-case scenario. All stakers must operate an execution client with their consensus client. Examples include Nethermind, Reth, Besu, Erigon, and Geth.
6. Configure your consensus client layer. Install and Sync a consensus layer client. It is high risk to run your validator in multiple places. It will lead to a slashable event and ejection from the network. Examples include Nimbus, Teku, Prysm, and Lighthouse,&#x20;
7. Generate a validator key: you can either [download CLI app](https://github.com/ethereum/staking-deposit-cli/releases/), Download [Key Gen GUI app](https://github.com/stake-house/wagyu-key-gen/releases), or Build from source
8. JWT Authentication: Your task here is to setup a JWT shared key and make it available to both your consensus client and execution client (beacon node). Communication between the execution layer and consensus layer occurs using the [Engine API](https://github.com/ethereum/execution-apis/blob/main/src/engine/specification.md). This is a set of JSON RPC methods that can be used to communicate between the two client layers.This communication is secured using a [JWT](https://en.wikipedia.org/wiki/JSON\_Web\_Token) secret, which is a secret key that is shared only between the two clients to authenticate one another. This shared JWT secret must be made available to each client (both execution and consensus clients) to allow them to communicate with one another properly. Consensus JWT docs: [Lighthouse](https://lighthouse-book.sigmaprime.io/merge-migration.html#connecting-to-an-execution-engine) | [Nimbus](https://nimbus.guide/eth1.html#3-pass-the-url-and-jwt-secret-to-nimbus) | [Prysm](https://docs.prylabs.network/docs/execution-node/authentication) | [Teku](https://docs.teku.consensys.net/get-started/connect/mainnet#1-generate-the-shared-secret). Execution JWT docs: [Besu](https://besu.hyperledger.org/en/stable/public-networks/reference/cli/options/#engine-jwt-secret) | [Erigon](https://github.com/ledgerwatch/erigon#beacon-chain-consensus-layer) | [Geth](https://geth.ethereum.org/docs/interface/consensus-clients) | [Nethermind](https://docs.nethermind.io/nethermind/first-steps-with-nethermind/running-nethermind-post-merge#jwt-secrets) | [Reth](https://reth.rs/run/mainnet.html#running-the-reth-node).
9. Set withdrawal address: You may choose to provide a withdrawal address with your initial deposit to automatically enable reward payments and also the ability to fully exit your funds at anytime (recommended). This address should be to a regular Ethereum address and will be the only address funds can be sent to from your new validator accounts, and cannot be changed once chosen. If this is not provided now, your deposited funds will remain locked on the Beacon Chain until an address is provided. Unlocking will require signing a message with your withdrawal keys, generated from your mnemonic seed phrase (so keep it safe). Stakers must set a withdrawal address to unlock reward payments from the consensus layer. This is set when generating your validator keys.If you do not provide a withdrawal address prior to depositing, you will have to perform an additional step to update your keys and enable withdrawals. Funds will be locked in the meantime.
10. Set fee recipient: Stakers must provide a fee recipient address to their consensus client in order to receive transaction fee rewards. This is a normal Ethereum address that you're used to.If you do not provide an address to your client, you will not receive transaction fees when your validator proposes blocks.See your consensus client documentation for client-specific instructions on how to set this.Fee recipient docs: [Lighthouse](https://lighthouse-book.sigmaprime.io/suggested-fee-recipient.html) | [Nimbus](https://nimbus.guide/suggested-fee-recipient.html) | [Prysm](https://docs.prylabs.network/docs/execution-node/fee-recipient) | [Teku](https://docs.teku.consensys.net/reference/cli#validators-proposer-default-fee-recipient)
11. Consensus Layer Beacon Node (BN): You will be required to connect your consensus client to your execution client via a HTTP API(s) and sync your beacon node (consensus client) on Testnet or Mainnet. Make sure that your node has more than 20 peers. Verify it with the following command to check if it returns the client version correctly:

`curl -H "Content-Type: application/json" -X POST --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":67}' http://<YourServerLocation>:8545`

12. Consensus Layer Validator Client (VC): import your keystore(s) into your validator client,, ensure it/they're only stored on one validator machine, and start running validator client.
13. Setup a wallet and deposit ETH.
14. After depositing, protect your funds using monitoring software, and learn how to handle different real world scenarios. Then, upload the deposit data file you just generated on the [Staking Launchpad website](https://launchpad.ethereum.org/en/checklist#section-one).&#x20;

<figure><img src=".gitbook/assets/Screenshot from 2024-08-23 09-39-26 (1).png" alt=""><figcaption></figcaption></figure>



15. The deposit\_data-\[timestamp].json is located in your /staking-deposit-cli/validator\_keys directory.
16. Connect your wallet.
17. These steps are optional but are recommended to optimize your node.

i. Monitoring: Prometheus and Grafana monitor. The clients support Prometheus and Grafana to help you visualize important real-time metrics about your validator. setup [Prometheus service](https://prometheus.io/), [Grafana service](https://grafana.com/) and import the dashboard config to your Grafana server and double check that your node is alive. Monitoring docs: [Lighthouse](https://github.com/sigp/lighthouse-metrics) | [Nimbus](https://nimbus.guide/metrics-pretty-pictures.html) | [Prysm](https://docs.prylabs.network/docs/prysm-usage/monitoring/grafana-dashboard/) | [Teku](https://docs.teku.consensys.net/how-to/monitor/use-metrics)

ii Testnet simulations

While validating on the testnet, perform these simulations to learn more about your node, and better prepare yourself for Mainnet: simulate how to manually stop and restart the Beacon Node (BN) and Validator Client (VC) gracefully, simulated power loss (server and internet) and automatic resumption, simulated how to safely migrate from one consensus client to another, simulated how to safely migrate from one execution client to another.

iii. Advanced system architecture

* To avoid exposing your validator identity to the network, you can use a trustworthy VPN to help reduce the risk of revealing your IP address.
* Moreover, you can set your Validator Client (VC) and Beacon Node (BN) on separate machines and IPs so that even if your beacon node is vulnerable, your keystore is stored on a different machine.

iv. Graffiti: You can use your validator client's graffiti flag to add a personal touch to your proposed blocks (some text of your choice). You will be able to see it using [Beaconcha.in](https://mainnet.beaconcha.in) or [BeaconScan](https://beaconscan.com/) blockchain explorers.



