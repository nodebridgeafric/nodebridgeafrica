# Page 6

david@nodebridge-operator:\~$ scp -r david@10.128.0.6:/home/david/staking-deposit-cli / david@10.128.0.6: Permission denied (publickey). scp: Connection closed david@nodebridge-operator:$

ssh -i /path/to/your/private\_key david@104.154.35.215

scp -P 2222 -r david@104.154.35.215:/home/david/staking-deposit-cli \~/

scp -r david@\<external\_ip>:/home/david/staking-deposit-cli \~/



It looks like you are trying to use `scp` to download the `staking-deposit-cli` folder, but you're running into permission issues and connection errors. Here’s how to proceed step by step:

#### 1. **Use the Correct External IP Address**

Make sure you're using the correct external IP address (e.g., `104.154.35.215` in your case) instead of an internal IP. Internal IPs like `10.128.0.6` are not accessible from outside Google Cloud.

#### 2. **SSH into the VM**

Before using `scp`, make sure you can SSH into your VM successfully using the private key. The command should look like this:

```bash
ssh -i /path/to/your/private_key david@104.154.35.215
```

#### 3. **Use `scp` with the Correct Command**

Once you’ve confirmed that you can SSH into the VM, use the `scp` command to download the folder. If you are using a custom port (like 2222), the command will look like this:

```bash
scp -P 2222 -r -i /path/to/your/private_key david@104.154.35.215:/home/david/staking-deposit-cli ~/
```

#### Breakdown of the Command:

* `-P 2222`: Specifies the port number if it’s not the default (22).
* `-r`: Recursively copy the entire directory.
* `-i /path/to/your/private_key`: Use your specific private key for authentication.

#### 4. **Ensure the Correct Key Permissions**

Make sure that your private key has the correct permissions. You can set the permissions using:

```bash
chmod 600 /path/to/your/private_key
```

#### 5. **Check User Permissions**

Ensure that the user `david` has the necessary permissions to access the `staking-deposit-cli` directory on the VM. You can check the permissions by SSHing into the VM and running:

```bash
ls -ld /home/david/staking-deposit-cli
```

#### 6. **Firewall Rules**

If you still encounter connection issues, double-check the firewall settings in the Google Cloud Console to ensure that SSH traffic is allowed on the specified port.

#### Summary

1. Use the correct external IP address.
2. SSH into the VM to confirm access.
3. Use the correct `scp` command with the right key and port.
4. Check user permissions and firewall rules if needed.

Let me know if you encounter any further issues!



