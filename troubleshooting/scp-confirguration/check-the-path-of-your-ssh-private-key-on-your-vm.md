# check the path of your SSH private key on your VM

To check the path of your SSH private key on your VM or see its contents, you can follow these steps:

#### 1. **Common Locations for SSH Keys**

By default, SSH keys are typically stored in the `~/.ssh/` directory. You can check for existing keys there:

```bash
ls -l ~/.ssh/
```

Look for files named something like:

* `id_rsa` (the private key)
* `id_rsa.pub` (the public key)

#### 2. **View the Private Key**

If you find your private key (e.g., `id_rsa`), you can view its contents with:

```bash
cat ~/.ssh/id_rsa
```

#### 3. **Check for Other Keys**

If you don't see the default key files, there might be other keys. You can list all files in the `.ssh` directory:

```bash
ls -l ~/.ssh/*
```

#### 4. **Identifying Your Key**

If you have multiple keys and you’re unsure which one is being used, you can check the `~/.ssh/config` file if it exists:

```bash
cat ~/.ssh/config
```

This file may specify which private key to use for different hosts.

#### 5. **Creating a New SSH Key**

If you do not have a private key and need to create a new one, you can generate a new key pair using:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Follow the prompts to specify the file location (default is `~/.ssh/id_rsa`), and a passphrase is optional but recommended.

#### Important Note on Security

* **Do not share your private key**: It should remain confidential and should never be shared with anyone.
*   **Check Permissions**: Ensure that your private key file has the correct permissions:

    ```bash
    chmod 600 ~/.ssh/id_rsa
    ```

#### Summary

1. Check for existing keys in `~/.ssh/`.
2. Use `cat` to view the private key.
3. Review `~/.ssh/config` for configurations.
4. Create a new key if necessary.







david@nodebridge-operator:\~$ ls -l /.ssh/&#x20;

total 8 -rw------- 1 david david 750 Oct 6 17:58 authorized\_keys&#x20;

\-rw-r--r-- 1 david david 142 Oct 6 03:51 known\_hosts&#x20;

david@nodebridge-operator:$
