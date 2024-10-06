---
description: >-
  david@nodebridge-operator:~$ scp -r
  david@10.128.0.6:/home/david/staking-deposit-cli ~/ david@10.128.0.6:
  Permission denied (publickey). scp: Connection closed
  david@nodebridge-operator:~$
---

# SCP PERMISSION

The error message you're seeing indicates that there's a problem with the SSH authentication when trying to use `scp`. Here are some steps you can take to troubleshoot and resolve the issue:

#### 1. **Check SSH Key Configuration**

Make sure that your SSH key is properly set up for the user `david` on the VM. If you used a specific SSH key for accessing the VM, ensure you're using the same key with `scp`.

If you need to specify the SSH key, you can do so with the `-i` option:

```bash
scp -i /path/to/your/private_key -r david@10.128.0.6:/home/david/staking-deposit-cli ~/
```

#### 2. **Use the Correct IP Address**

Since `10.128.0.6` is an internal IP address, it might not be accessible from outside the Google Cloud network. If you're trying to access it from your local machine, you should use the external IP address of your VM. Check the Google Cloud Console for the external IP address.

#### 3. **Firewall Rules**

Ensure that the firewall rules for your Google Cloud project allow SSH (port 22) connections. You can check this in the Google Cloud Console under "VPC network" > "Firewall".

#### 4. **Check SSH Access**

Try connecting to your VM using SSH to ensure you can access it:

```bash
ssh -i /path/to/your/private_key david@<external_ip>
```

Replace `<external_ip>` with the actual external IP address of your VM. If you can connect, then `scp` should work as well.

#### 5. **Permissions on the VM**

Make sure that the user `david` has the necessary permissions to access the `staking-deposit-cli` folder.

#### Example Command with External IP

If you have the external IP, the command should look something like this:

```bash
scp -r david@<external_ip>:/home/david/staking-deposit-cli ~/
```

#### Summary

Make sure to use the external IP, check your SSH keys, and ensure your VM's firewall allows SSH connections. If you still face issues after these checks, let me know!



