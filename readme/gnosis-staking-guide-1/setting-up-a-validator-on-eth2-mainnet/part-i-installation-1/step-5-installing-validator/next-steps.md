# Next Steps

{% hint style="success" %}
:tada: Congrats! You've finished the primary steps of setting up your validator. You're now an Ethereum staker!
{% endhint %}

## :track\_next: FAQ

<details>

<summary>When is staking rewards?</summary>

**Activation Queue**: Once your EL+CL is synced, validator up and running, you just wait for activation. This process can take 24+ hours. Only 900 new validators can join per day. Check the queue length: [https://wenmerge.com](https://wenmerge.com)

**Activated**: When you're activated, your validator will begin creating and voting on blocks while earning staking rewards.

**Quick monitoring**: Use [https://beaconcha.in/](https://beaconcha.in) to create alerts and track your validator's performance.

</details>

<details>

<summary>Sync Timeline</summary>

Syncing the consensus client is instantaneous with checkpoint sync but the execution client can take up to a day. On nodes with fast NVME drives and gigabit internet, expect your node to be fully synced in a few hours.

**How do I know I'm fully synced?**

* Check your execution client's logs and compare the block number against the most recent block on [https://etherscan.io](https://etherscan.io/)
  * Check EL logs: `journalctl -fu execution`
* Thanks to checkpoint sync, your consensus client's is instantly synched. You can compare the slot number against the most recent slot on [https://beaconcha.in](https://beaconcha.in/)
  * Check CL logs: `journalctl -fu consensus`

</details>

### :thumbsup: Recommended Next Steps

* :fingers\_crossed:**Finished with staking?** Before decommissioning your validator, it's good practice to properly [exit your validator](../../../../ethereum-staking-guide/ethereum-staking-guide/setting-up-a-validator-on-eth2-mainnet/part-iii-tips-1/voluntary-exiting-a-validator.md) and re-claim your ETH deposit.

### :checkered\_flag: Optional Steps

* :robot:**MEV-boost**: Setup [MEV-boost](../../../../ethereum-staking-guide/ethereum-staking-guide/mev-boost/) for extra staking rewards!
* :bar\_chart:**Monitoring**: Setup [Monitoring with Grafana and Prometheus](../../../../ethereum-staking-guide/ethereum-staking-guide/setting-up-a-validator-on-eth2-mainnet/part-i-installation-1/monitoring-your-validator-with-grafana-and-prometheus.md)
* :chains:**RPC**: Setup using your own [Node as a RPC endpoint](../../../../ethereum-staking-guide/ethereum-staking-guide/setting-up-a-validator-on-eth2-mainnet/part-iii-tips-1/using-staking-node-as-rpc-url-endpoint.md).
* :mobile\_phone:**Notifications**: Setup [Mobile App Notifications and Monitoring by beaconcha.in](../../../../ethereum-staking-guide/ethereum-staking-guide/setting-up-a-validator-on-eth2-mainnet/part-i-installation-1/mobile-app-node-monitoring-by-beaconchain.md)
* :up:**External Monitoring**: Setup [External Monitoring with Uptime Check by Google Cloud](../../../../../nodes/ethereum-node/archived-guides/guide-or-how-to-setup-a-validator-on-eth2-mainnet/part-i-installation/monitoring-with-uptime-check-by-google-cloud.md)
* :books:**Knowledge**: Familiarize yourself with [Part III - Tips](../../../../ethereum-staking-guide/ethereum-staking-guide/setting-up-a-validator-on-eth2-mainnet/part-iii-tips-1/) section, as you dive deeper into staking.

### :telephone: **Need extra live support?**

* Find likeminds [NodeBridge Africa](https://t.me/+tvDqZMWfz580NTI0) Telegram and [NodeBridge Africa](https://x.com/Nodebridgeafric) Twitter.

<figure><img src="../../../../ethereum-staking-guide/.gitbook/assets/leslie-solo.png" alt=""><figcaption><p>This is Leslie, the official mascot of Eth Staking</p></figcaption></figure>
