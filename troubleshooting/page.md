# Page

To use FileZilla on Ubuntu, follow these steps:

#### 1. Install FileZilla

* Open the Terminal (you can find it in the applications menu or press `Ctrl + Alt + T`).
*   Update your package list:

    ```bash
    sudo apt update
    ```
*   Install FileZilla:

    ```bash
    sudo apt install filezilla
    ```

#### 2. Launch FileZilla

* You can start FileZilla from the applications menu or by typing `filezilla` in the Terminal.

#### 3. Connect to the Server

* In FileZilla, fill in the following fields at the top:
  * **Host**: Your FTP server address (e.g., `ftp.example.com`).
  * **Username**: Your FTP username.
  * **Password**: Your FTP password.
  * **Port**: Typically, 21 for FTP and 22 for SFTP.
* Click **Quickconnect**.

#### 4. Navigate Directories

* The left pane shows your local files.
* The right pane shows the remote server files.
* Browse to the desired folders in both panes.

#### 5. Transfer Files

* **To Upload**: Drag and drop files from the left pane (local) to the right pane (remote).
* **To Download**: Drag and drop files from the right pane (remote) to the left pane (local).

#### 6. Monitor Transfers

* Check the progress of your file transfers in the lower panel. Completed transfers will appear in the designated folders.

#### 7. Disconnect

* To disconnect, click on the **Server** menu and select **Disconnect**, or simply close the FileZilla window.

#### Tips

* If you encounter any issues with permissions, ensure your FTP user has the appropriate rights on the server.
* For better performance, consider adjusting transfer settings under **Edit** > **Settings**.

If you have any more questions or run into any issues, feel free to ask!
