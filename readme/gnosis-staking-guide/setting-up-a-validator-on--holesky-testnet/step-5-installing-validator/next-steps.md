# Next Steps

{% hint style="success" %}
:tada: Congrats! You've finished the primary steps of setting up your validator. You're now an Ethereum staker!
{% endhint %}

## :track\_next: FAQ

<details>

<summary>Wen staking rewards?</summary>

**Activation Queue**: Once your EL+CL is synced, validator up and running, you just wait for activation. This process can take 24+ hours. Only 900 new validators can join per day. Check the queue length: [https://wenmerge.com](https://wenmerge.com)

**Activated**: When you're activated, your validator will begin creating and voting on blocks while earning staking rewards.

**Quick monitoring**: Use [https://holesky.beaconcha.in](https://holesky.beaconcha.in/) to create alerts and track your validator's performance.

</details>

<details>

<summary>Sync Timeline</summary>

Syncing the consensus client is instantaneous with checkpoint sync but the execution client can take up to a day. On nodes with fast NVME drives and gigabit internet, expect your node to be fully synced in a few hours.

**How do I know I'm fully synced?**

* Check your execution client's logs and compare the block number against the most recent block on [https://holesky.etherscan.io](https://holesky.etherscan.io/)
  * Check EL logs: `journalctl -fu execution`
* Thanks to checkpoint sync, your consensus client's is instantly synched. You can compare the slot number against the most recent slot on [https://holesky.beaconcha.in](https://holesky.beaconcha.in/)
  * Check CL logs: `journalctl -fu consensus`

</details>

### :thumbsup: Recommended Steps

* :fingers\_crossed:**Finished testing?** Before decommissioning your validator, it's good practice to properly exit your validator as this improves staking network health.

### :checkered\_flag: Optional Steps

* :robot:**MEV-boost**: Setup [MEV-boost](../../../ethereum-staking-guide/mev-boost/) for extra staking rewards!
* :bar\_chart:**Monitoring**: Setup Monitoring with Grafana and Prometheus
* :chains:**RPC**: Setup using your own Node as a RPC endpoint
* :mobile\_phone:**Notifications**: Setup Mobile App Notifications and Monitoring by beaconcha.in
* :up:**External Monitoring**: Setup External Monitoring with Uptime Check by Google Cloud

### :telephone: **Need extra live support?**

{% hint style="success" %}
**Ready for mainnet staking? Check Out the Mainnet guide.**
{% endhint %}
