# Save the key files and get the validator file ready

You should now have your mnemonic written down in a safe place and a keystore saved for each of your 1 validators. Please make sure you keep these safe, preferably offline. Your validator keystores should be available in the newly created validator\_keys directory.You should see that you have one keystore per validator. This keystore contains your signing key, encrypted with your password.



<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

The other file you just generated is deposit\_data.json. This file contains the public key(s) associated with your validator(s); You will need to upload this in the next step.

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>



Warning: Do not store keys on multiple (backup) validator clients at once

[More on slashing prevention](https://medium.com/prysmatic-labs/eth2-slashing-prevention-tips-f6faa5025f50)
