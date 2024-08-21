# Downloading files from your node

### Using the secure file transfer protocol (SFTP) <a href="#using-the-secure-file-transfer-protocol-sftp" id="using-the-secure-file-transfer-protocol-sftp"></a>

An easy way to extract (i.e. download) files from your validator node onto your working laptop is to make use of SFTP - an extension of the SSH protocol.

To connect your working laptop to your validator node via SFTP, run:

```
sftp -P <port> -i <ssh_key_filepath> <user>@<IP_address>
```

Note the difference in order and capitalisation of the port (-P) and identity (-i) flags from the SSH syntax.

Once you are connected, you will now be in the home folder of your validator node and you can then download your desired file by running:

**If file is in home folder:**

```
get <file_name>
```

**If file is in other folders:**

```
get <full_file_path>
```
