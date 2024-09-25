# Page 1

To transfer your validator keys to your node on Ubuntu using FileZilla, follow these steps:

#### Step 1: Prepare Your Validator Keys

1. **Ensure your validator keys** (e.g., `keystore-m_xxxxxxxx.json` files) are ready on your local machine.

#### Step 2: Install FileZilla (if not already installed)

1. Open the Terminal.
2.  Update your package list:

    ```bash
    sudo apt update
    ```
3.  Install FileZilla:

    ```bash
    sudo apt install filezilla
    ```

#### Step 3: Launch FileZilla

* Start FileZilla from the applications menu or by typing `filezilla` in the Terminal.

#### Step 4: Connect to Your Node

1. In FileZilla, enter the following:
   * **Host**: Your node’s IP address or hostname.
   * **Username**: Your SSH username for the node.
   * **Password**: Your SSH password (if applicable).
   * **Port**: Typically, this is `22` for SFTP.
2. Click **Quickconnect**.

#### Step 5: Navigate to the Destination Directory

1.  In the right pane (remote), navigate to:

    ```bash
    $HOME/staking-deposit-cli/validator_keys
    ```

    This might be displayed as `/home/your-username/staking-deposit-cli/validator_keys`.

#### Step 6: Transfer Validator Keys

1. In the left pane (local), locate your `keystore-m_xxxxxxxx.json` files.
2. Drag and drop the files from the left pane to the right pane to transfer them.

#### Step 7: Verify the Transfer

1. After the transfer, check the right pane to confirm that your files are now in the `$HOME/staking-deposit-cli/validator_keys` directory.

#### Step 8: Disconnect

* To disconnect, click on the **Server** menu and select **Disconnect**, or just close the FileZilla window.

#### Tips

* Ensure that your node is accessible over SSH and that the firewall allows SFTP connections.
* If you prefer using the command line, you can also use `scp` or `rsync` for transferring files, especially if you have SSH access set up.

If you have any further questions or encounter issues, feel free to ask!
