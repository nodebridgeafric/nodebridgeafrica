# Setting Up Private Key

It looks like there are no SSH private key files in your `~/.ssh/` directory. The files you see (`authorized_keys` and `known_hosts`) serve different purposes:

* **`authorized_keys`**: This file contains public keys that are authorized to access the account. If you're connecting to a remote server, the server checks this file to see if the public key of your client is allowed.
* **`known_hosts`**: This file keeps track of the public keys of remote hosts you have connected to, helping to prevent man-in-the-middle attacks.

#### If You Don't Have a Private Key

Since there are no private keys in your `.ssh/` directory, you’ll need to create a new SSH key pair. Here’s how to do that:

#### 1. **Generate a New SSH Key Pair**

Run the following command:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Replace `"your_email@example.com"` with your actual email address.

#### 2. **Follow the Prompts**

* **File location**: When prompted for the file location, you can press Enter to accept the default location (`~/.ssh/id_rsa`).
* **Passphrase**: You can also choose to set a passphrase for added security or leave it empty.

#### 3. **Locate Your Keys**

After generating the keys, you will have:

* **Private Key**: `~/.ssh/id_rsa` (keep this secure)
* **Public Key**: `~/.ssh/id_rsa.pub` (this can be shared)

#### 4. **Copy the Public Key to the Remote Server**

You’ll need to copy the public key (`id_rsa.pub`) to the remote server’s `~/.ssh/authorized_keys` file to allow SSH access. You can do this manually or use the `ssh-copy-id` command:

```bash
ssh-copy-id -i ~/.ssh/id_rsa.pub -p 2222 david@<external_ip>
```

Replace `<external_ip>` with the actual external IP address of your VM and `-p 2222` if you're using a non-standard port.

#### 5. **Test SSH Connection**

After copying the public key, test the SSH connection:

```bash
ssh -i ~/.ssh/id_rsa -p 2222 david@<external_ip>
```

#### Summary

1. Generate a new SSH key pair.
2. Copy the public key to the remote server.
3. Test the connection.

Let me know if you need more assistance!
