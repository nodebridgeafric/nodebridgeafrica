# Installing Validator

A _validator_ is a virtual entity that lives on the Beacon Chain, represented by a balance, public key, and other properties, and participates in consensus of the Ethereum network.

A _validator client_ is the software that acts on behalf of the validator by holding and using its private key to make attestations about the state of the chain. A single validator client can hold many key pairs, controlling many validators.

The validator client is essential for participating in Ethereum's proof-of-stake system. Its main roles include verifying new blocks by checking the transactions and their validity, re-executing them to confirm changes to the blockchain state, and broadcasting votes called attestations to signal agreement with valid blocks. The client also helps maintain network security by producing blocks when selected and monitoring the network for updates.
