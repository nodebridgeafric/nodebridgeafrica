# Bonded Validators

### What are bonded validators? <a href="#what-are-bonded-validators" id="what-are-bonded-validators"></a>

Conventionally, running an Ethereum validator node as a solo staker required you to deposit 32 ETH into the [beacon deposit contract](https://etherscan.io/address/0x00000000219ab540356cBB839Cbe05303d7705Fa).

However, there are options available today to significantly reduce this capital requirement in the form of bonded validators. The basic mechanism works as follows:

1. **Liquid stakers** stakes native ETH into smart contracts of liquid staking protocols
2. **Node operators** provide some amount of ETH as collateral or bond (e.g., 1/2/4/8 ETH) to serve as the first line of defence against slashing events, poor performance, & MEV theft.
3. **Liquid staking protocols** assign some amount of staked ETH of liquid stakers to node operators to fulfil the 32 ETH minimum requirement per active validator key
4. **Fee distribution:** Liquid staker pay some fees (e.g., 10% or 14%) to the liquid staking protocol and a majority portion (or all) of this flows to node operators

Hence, bonded validators enable node operators to lower their capital requirements and boost their rewards rate as compared to native solo staking.

### Examples of bonded validators <a href="#examples-of-bonded-validators" id="examples-of-bonded-validators"></a>

| Option         | ETH bond | ETH matched | Non-ETH bond         | Fee %                | Note                                              |
| -------------- | -------- | ----------- | -------------------- | -------------------- | ------------------------------------------------- |
| Rocketpool     | 8        | 24          | 2.4 ETH worth of RPL | 14% out of 14% total | 8% APR on RPL staked                              |
| Stader         | 4        | 28          | 0.4 ETH worth of SD  | 6% out of 10% total  | 7.97% APR on SD staked                            |
| Lido           | 2        | 32          | None                 | 8% out of 10% total  | Bond provided in stETH which also accrues rewards |
| Ether.fi (WIP) |          |             |                      |                      |                                                   |
| Puffer (WIP)   |          |             |                      |                      |                                                   |

### How do I run bonded validators as a solo staker? <a href="#how-do-i-run-bonded-validators-as-a-solo-staker" id="how-do-i-run-bonded-validators-as-a-solo-staker"></a>

_**There are 2 methods of setting up bonded validators today.**_



{% tabs %}
{% tab title="Lido CSM" %}
<figure><img src=".gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

For the Lido CSM, you will essentially be running just a native validator node with no additional services required on your hardware. Bond deposit is managed on the CSM Webapp.

#### Jump to Lido CSM setup here <a href="#jump-to-lido-csm-setup-here" id="jump-to-lido-csm-setup-here"></a>


{% endtab %}

{% tab title="Rocketpool, Stader" %}
<figure><img src=".gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

For the Rocketpool and Stader, you will need to run an additional and separate service that handles the ETH bond + alternative tokens deposit on your hardware on top of your native validator node.

You then expose the endpoints of your execution and consensus, and connect them to your bonded validator client. This way, your bonded validator client can now "talk" to your existing execution + consensus clients and perform its duties.
{% endtab %}

{% tab title="Native Solo Staking" %}
<figure><img src=".gitbook/assets/image (21).png" alt=""><figcaption><p>Simplified illustration of a solo staker setup</p></figcaption></figure>

#### Jump to native Solo Staking setup below <a href="#jump-to-native-solo-staking-setup-below" id="jump-to-native-solo-staking-setup-below"></a>
{% endtab %}
{% endtabs %}

You can also run multiple bonded validator clients on the same hardware, provided that you have sufficient resources (e.g., CPU, RAM, Disk) on your hardware to meet the minimum requirements of each additional service.

<figure><img src=".gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
You can also run DVT clients alongside bonded validator clients.
{% endhint %}
