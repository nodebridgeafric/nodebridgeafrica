# Page 2

To obtain the necessary connection details for your node, follow these steps:

#### 1. Find Your Node’s IP Address or Hostname

* **Public IP**: If your node is hosted in the cloud (like AWS, DigitalOcean, etc.), you can find the public IP address in the cloud provider's management console.
*   **Local Network**: If the node is on your local network, you can find the IP address by running:

    ```bash
    hostname -I
    ```

    in the terminal of the node itself.

#### 2. Determine Your SSH Username

* The SSH username is typically the user account you created when setting up your node. Common usernames include:
  * `ubuntu` (for Ubuntu servers on cloud providers)
  * `centos` (for CentOS servers)
  * `ec2-user` (for Amazon EC2 instances)
* If you’re unsure, check the documentation of your cloud provider or the server setup.

#### 3. Get Your SSH Password

* If you set up your node with a password, use that password.
* If you used an SSH key for authentication, you won’t need a password. Ensure you have the private key file (.pem or .key) that corresponds to the public key placed on your node.

#### 4. Port Number

* The default port for SFTP (SSH File Transfer Protocol) is **22**. Unless you configured your node to use a different port, you should use 22.

#### Example

Here’s how it might look:

* **Host**: `192.168.1.10` (replace with your node’s IP)
* **Username**: `ubuntu`
* **Password**: (leave blank if using SSH key)
* **Port**: `22`

#### Troubleshooting

* If you cannot connect, check your firewall settings and ensure that SSH is enabled on your node.
* If you are using a cloud provider, ensure your security group settings allow inbound SSH connections on port 22.

If you have more questions or need further assistance, let me know!
