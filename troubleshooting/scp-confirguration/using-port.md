# Using Port



To specify a port when using `scp`, you can use the `-P` option (note the uppercase "P"). Here's how you can structure your command:

#### Command Syntax

```bash
scp -P port_number -r username@host:remote_directory local_directory
```

#### Example Command

If you're connecting to your VM on a specific port (for example, port 2222), the command to download the `staking-deposit-cli` folder would look like this:

```bash
scp -P 2222 -r david@<external_ip>:/home/david/staking-deposit-cli ~/
```

Replace `<external_ip>` with the actual external IP address of your VM.

#### Steps to Follow

1. **Determine the Port**: Make sure you know which port your SSH service is using. The default is 22, but it can be changed for security purposes.
2. **Run the Command**: Open your terminal on your local machine and run the command with the correct external IP and port.

#### Example with Default Port

If you’re using the default SSH port (22), you don’t need to specify the `-P` option:

```bash
scp -r david@<external_ip>:/home/david/staking-deposit-cli ~/
```

#### Troubleshooting

If you run into any permission issues or connection errors, make sure:

* The SSH service is running on the VM.
* You can SSH into the VM with the specified port.
* Your firewall rules allow connections on that port.

Let me know if you need further assistance!

