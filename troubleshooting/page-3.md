# Page 3

To ensure that SSH is enabled on your node, you can follow these steps:

1.  **Check SSH Service Status:** Run the following command in your terminal:

    ```bash
    sudo systemctl status ssh
    ```

    This will show you if the SSH service is active and running. If it's not active, you can start it with:

    ```bash
    sudo systemctl start ssh
    ```
2.  **Enable SSH to Start on Boot:** If you want to ensure SSH starts automatically on boot, use:

    ```bash
    sudo systemctl enable ssh
    ```
3.  **Check Firewall Settings:** Make sure your firewall allows SSH connections. If you're using `ufw`, you can check with:

    ```bash
    sudo ufw status
    ```

    If SSH is not allowed, you can enable it with:

    ```bash
    sudo ufw allow ssh
    ```
4.  **Verify SSH Configuration:** You can check the SSH configuration file (`/etc/ssh/sshd_config`) to ensure it's set up correctly. Common settings to verify include:

    * `PermitRootLogin` (often set to `no` for security)
    * `PasswordAuthentication` (set to `yes` or `no` depending on your needs)

    After making changes, restart the SSH service:

    ```bash
    sudo systemctl restart ssh
    ```
5.  **Testing SSH Connection:** From another machine, try connecting to your node using:

    ```bash
    ssh username@your_node_ip
    ```

    Replace `username` with your actual username and `your_node_ip` with the IP address of your node.

By following these steps, you can ensure that SSH is enabled and configured properly on your node.
