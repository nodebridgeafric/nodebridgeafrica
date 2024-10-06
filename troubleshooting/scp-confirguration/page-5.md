# Page 5

david@nodebridge-operator:\~$ scp -P 2222 -r david@10.128.0.6:/home/david/staking-deposit-cli / ssh: connect to host 10.128.0.6 port 2222: Connection refused scp: Connection closed david@nodebridge-operator:$



The "Connection refused" error usually indicates that the SSH service on the target host isn't listening on the specified port or that you're trying to connect to an internal IP address that's not accessible from your local machine. Here’s how to troubleshoot and resolve this:

#### Steps to Troubleshoot

1. **Use External IP Address**: Make sure you are using the external IP address of your Google VM instead of the internal IP address. The internal IP (`10.128.0.6`) is only accessible from within the Google Cloud network. Find the external IP in the Google Cloud Console.
2.  **Check SSH Configuration**: Ensure that the SSH service on your VM is configured to listen on the specified port (2222 in your case). You can check this by connecting to your VM directly (if you have access) and inspecting the SSH configuration file:

    ```bash
    sudo nano /etc/ssh/sshd_config
    ```

    Look for a line like this:

    ```
    Port 2222
    ```

    If it's set to a different port or if it's commented out, you'll need to adjust accordingly.
3.  **Restart SSH Service**: If you change the SSH port in the configuration, restart the SSH service:

    ```bash
    sudo systemctl restart sshd
    ```
4. **Firewall Rules**: Ensure that your firewall rules allow incoming connections on the specified port (2222). You can check and modify the firewall rules in the Google Cloud Console under "VPC network" > "Firewall."
5.  **Test SSH Connection**: Before using `scp`, test the SSH connection using the external IP and port:

    ```bash
    ssh -p 2222 david@<external_ip>
    ```

    Replace `<external_ip>` with the actual external IP address.

#### Example Command to Download

Once you’ve confirmed that SSH is set up correctly and the firewall allows the connection, the command to download the folder would look like this:

```bash
scp -P 2222 -r david@<external_ip>:/home/david/staking-deposit-cli ~/
```

#### Summary

1. Use the external IP address.
2. Verify the SSH port in the VM configuration.
3. Ensure firewall rules allow traffic on that port.
4. Test the SSH connection before attempting `scp`.

Let me know if you need further assistance!

