# Permission denied (publickey)

```
// Some code

david@nodebridge-operator:~$ ssh-copy-id -i ~/.ssh/id_rsa.pub -p 22 david@104.154.35.215
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/david/.ssh/id_rsa.pub"
The authenticity of host '104.154.35.215 (104.154.35.215)' can't be established.
ED25519 key fingerprint is SHA256:YYp1waK2AsJoZxBVANjfhUhIUISeV+XxGjXGRV/ze0I.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:1: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
david@104.154.35.215: Permission denied (publickey).
david@nodebridge-operator:~$ 
```





The "Permission denied (publickey)" error indicates that the SSH server is rejecting your attempt to log in, likely due to the public key not being recognized or not being installed correctly. Here’s how to troubleshoot this:

#### 1. **Check the Public Key on the Server**

If you have access to the VM through the Google Cloud Console, log in directly using the built-in SSH feature. Once logged in, check if your public key is in the `~/.ssh/authorized_keys` file:

```bash
cat ~/.ssh/authorized_keys
```

#### 2. **Manually Add the Public Key**

If your public key is not in the `authorized_keys` file, you can manually add it. First, display your public key on your local machine:

```bash
cat ~/.ssh/id_rsa.pub
```

Copy the output (your public key) and then on the VM, use a text editor to add it to the `authorized_keys` file:

```bash
echo "your_public_key_here" >> ~/.ssh/authorized_keys
```

Make sure to replace `"your_public_key_here"` with the actual public key you copied.

#### 3. **Check Permissions**

Ensure the permissions for the `.ssh` directory and the `authorized_keys` file are set correctly on the VM. The permissions should be:

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

#### 4. **Check the SSH Service Configuration**

Since you've already verified the SSH configuration file, ensure it allows public key authentication. Make sure the following line is not commented out in `/etc/ssh/sshd_config`:

```plaintext
PubkeyAuthentication yes
```

If you made changes, restart the SSH service:

```bash
sudo systemctl restart sshd
```

#### 5. **Verify the Correct Key is Used**

If you have multiple keys, ensure that the correct private key is specified when connecting. You can explicitly specify it in the `ssh` command:

```bash
ssh -i ~/.ssh/id_rsa -p 22 david@104.154.35.215
```

#### 6. **Testing the SSH Connection**

After you’ve added the public key and confirmed permissions, try connecting again:

```bash
ssh -i ~/.ssh/id_rsa -p 22 david@104.154.35.215
```

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-06 at 19.33.54.png" alt=""><figcaption></figcaption></figure>

####

#### Summary

1. Check if your public key is in the `authorized_keys` file.
2. Manually add the public key if it's missing.
3. Ensure correct permissions for the `.ssh` directory and files.
4. Verify SSH service configuration allows public key authentication.
5. Explicitly specify the private key when connecting.

Let me know if you need further help!
