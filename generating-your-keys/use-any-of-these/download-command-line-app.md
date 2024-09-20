# Download command line app



Step 1: Download the deposit command line interface app for your operating systemPlease make sure that you are downloading from the official Ethereum Foundation GitHub account by verifying the url: **https://github.com/ethereum/staking-deposit-cli/releases/**



<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

Step 2: Generate deposit keys using the Ethereum Foundation deposit toolFor security, we recommend you disconnect from the internet to complete this step.

* Decompress the file you just downloaded
* Use the terminal to move into the directory that contains the `deposit` executable
* Run the following command to launch the app
* ```
  ./deposit new-mnemonic --num_validators 1 --chain mainnet 
  ```
* Make sure you have set --chain mainnet for Mainnet, otherwise the deposit will be invalid.
* Now follow the instructions presented to you in the terminal window to generate your keys.
