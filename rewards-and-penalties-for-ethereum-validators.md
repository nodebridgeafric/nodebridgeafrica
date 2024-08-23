# Rewards and Penalties for Ethereum Validators

## **Rewards**

Validators on the Ethereum network earn rewards for processing transactions and ensuring network security. These rewards come from three main sources:

1. **Issuance**:
   * **Consensus Layer Rewards**: Validators receive issuance rewards for participating in block attestation and performing sync committee duties. This contributes approximately 2.85% of the total annual percentage rate (APR).
2.  **Block Rewards**:

    * **Execution Layer Rewards**: Validators earn rewards from block proposals, which include transaction fees (tips) and MEV (Maximal Extractable Value) bribes. This contributes approximately 0.58% of the APR.
    * **Average APR**: The combined average APR from issuance and block rewards is around 3.42%. This is based on data from Rated.Network as of June 2, 2024. Note that due to variability in block rewards, the median APR for most validators is closer to 3.5%.



    <figure><img src=".gitbook/assets/image (25).png" alt=""><figcaption><p>Last 30 days data from Rated.Network. 2nd June 2024.</p></figcaption></figure>



    * **Block Attestation Rewards**: These rewards are relatively stable and adjust based on the number of active validators. More validators generally mean lower rewards per validator, and fewer validators mean higher rewards.
    * **Sync Committee Rewards**: Every 24 hours, 512 validators are selected to perform sync committee duties. These validators handle increased computational load and receive additional rewards. However, they also face higher penalties if they go offline.
3. **Block Rewards**:
   * **Proposal Rewards**: Each epoch (approximately 6.4 minutes), 32 validators are randomly selected to propose blocks. These block proposers receive all transaction tips and MEV fees associated with their blocks.
   * **Distribution**: Block rewards are given approximately every 6.4 minutes, with the accumulated balance automatically withdrawn to the validator’s wallet every 6 days.

**Penalties**

Validators can face penalties for various issues, which impact their rewards and overall participation in the network.

1. **Uncorrelated Downtime**:
   * **Individual Penalties**: If a validator goes offline independently (uncorrelated downtime), they incur inactivity penalties similar to their rewards rate. Missing block proposals during downtime can exacerbate these penalties.
2. **Correlated Downtime**:
   * **Network-Wide Penalties**: If a large portion of the network goes offline simultaneously, the "inactivity leak" mechanism is triggered. This is an emergency measure to encourage inactive validators to return or remove them from the network until more than 2/3 of validators are active again.
   * **Inactivity Leak**: This results in:
     * Stopping normal attestation rewards for all validators.
     * A quadratic leak, where penalties for inactive validators increase over time until the network stabilizes.
3. **Double Signing**:
   * **Slashing Offenses**: Double signing involves:
     * Signing two different beacon blocks for the same slot.
     * Signing an attestation that surrounds another attestation.
     * Signing two different attestations for the same target.
   * **Consequences**: These actions are considered malicious and can result in slashing, which involves removing a portion of the validator's stake and forcing their exit from the network.
4. **Aftermath of Slashing**:
   * **Exit Process**: A slashed validator is scheduled to exit the network within 36 days. They face an initial penalty of 1/32 of their effective balance, with additional penalties accruing until their exit.
   * **Correlated Slashing Penalties**: If other validators are also slashed during the same period, additional penalties apply, potentially affecting the entire effective balance.
5. **Slashing Prevention**:
   * **Keystore Management**: Avoid importing the same validator signing keystore onto multiple devices and ensure that keystores are not exposed or stored on multiple running nodes. Always delete old keystores when migrating.
   * **Slashing Protection**: Import the slashing protection database to new clients and use the doppelganger protection feature.
   * **Migration Practices**: Wait for at least 15 minutes and confirm that your validator has missed 2 epochs before starting a new validator client. Test migration procedures on a testnet before applying them on the mainnet.
