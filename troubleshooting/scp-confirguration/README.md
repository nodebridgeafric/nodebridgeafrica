---
description: >-
  how can i download the staking deposit cli folder from google vm to my local
  computer using the sc command david@nodebridge-operator:~/staking-deposit-cli$
  ls deposit validator_keys verify_seed david@
---

# SCP confirguration





To download the `staking-deposit-cli` folder from your Google VM to your local computer using the `scp` command, you can follow these steps:

1. **Open your terminal on your local machine.**
2.  **Use the `scp` command** to securely copy the folder. The basic syntax for the `scp` command is:

    ```bash
    scp -r username@remote_host:remote_directory local_directory
    ```

    Here's how you can structure the command for your situation:

    ```bash
    scp -r david@<your_vm_external_ip>:~/staking-deposit-cli ~/local_destination_directory
    ```

    Replace `<your_vm_external_ip>` with the external IP address of your Google VM and `~/local_destination_directory` with the path where you want to save the folder on your local machine.
3.  **Example command:**

    If your VM's external IP is `34.123.45.67` and you want to save the folder to your home directory on your local machine, the command would look like this:

    ```bash
    scp -r david@34.123.45.67:~/staking-deposit-cli ~/
    ```
4. **Enter your password** when prompted, and the transfer should start.

#### Notes:

* Make sure that the SSH service is running on your VM.
* Ensure you have permissions to read the folder on the VM and write to the destination on your local machine.
*   If you're using a specific SSH key for authentication, you can specify it with the `-i` option:

    ```bash
    scp -i /path/to/your/private_key -r david@34.123.45.67:~/staking-deposit-cli ~/
    ```

This should successfully transfer the `staking-deposit-cli` folder to your local computer! Let me know if you run into any issues.
