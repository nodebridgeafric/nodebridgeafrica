# Practicing on Cloud VMs

Here are some logistics you will need to prepare before hand:

1. Laptop
2. Google Cloud account with free trial activated. Credit card details are needed but don’t have to charge it
   * https://cloud.google.com/free
3.  Go into your Google Cloud console

    ![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2F1628445806-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FoML8XLjdWBoYbtGBoQ9R%252Fuploads%252F5WuJW84kDgivWRe3Zo6X%252Fimage.png%3Falt%3Dmedia%26token%3D0bf04042-f7f0-4b80-99ea-555533b4f900\&width=768\&dpr=4\&quality=100\&sign=f20a7aaa\&sv=1)
4.  Go to **Create a VM**

    ![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2F1628445806-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FoML8XLjdWBoYbtGBoQ9R%252Fuploads%252Fnoiv6Ipf3ryJoyFoWUzw%252Fimage.png%3Falt%3Dmedia%26token%3D6141723c-a1b6-4ea7-b568-df5bbb7d48a0\&width=768\&dpr=4\&quality=100\&sign=2c4a2954\&sv=1)
5.  Enable the **Compute Engine API**

    ![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2F1628445806-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FoML8XLjdWBoYbtGBoQ9R%252Fuploads%252FchErCG1L9zrCJmXfc5PU%252Fimage.png%3Falt%3Dmedia%26token%3Dbf472506-d4a8-4a56-b702-dec17dab9d28\&width=768\&dpr=4\&quality=100\&sign=d0861de2\&sv=1)

### Create a new VM <a href="#create-a-new-vm" id="create-a-new-vm"></a>

Go to your google cloud console and create a new VM.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2Fzu3HmYBz4s8Gg3I5voie%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=3dced729\&sv=1)

Choose the following settings:

1. **Name:** Choose your own name or leave it as the default setting
2. **Region:** Choose your preferred region but it is recommended to diversify away from the popular regions (e.g. US, EU) for mainnet setups to minimise the risk of correlated downtime. I am going with Singapore in this example.
3. **Zone:** Choose any
4. **Machine configuration:** E2
5. **Machine type:** e2-standard-8, 16GB memory

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2F1628445806-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FoML8XLjdWBoYbtGBoQ9R%252Fuploads%252FlyzO2pF8EMSmKY6hhLdg%252Fimage.png%3Falt%3Dmedia%26token%3D2e0b34e4-2259-4051-ab64-6ac948bee307\&width=768\&dpr=4\&quality=100\&sign=61b9bbab\&sv=1)

Under **Boot disk**, click on the **"change"** button.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FShiBGOKzBy9JqqwQcBk6%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=d7c5c693\&sv=1)

Select `Ubuntu` for the operating system, `Ubuntu 24.04 LTS x86` for the version, `SSD persistent disk` for the boot disk type, and `300 GB` for the size of the storage.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2F1628445806-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FoML8XLjdWBoYbtGBoQ9R%252Fuploads%252FDm0VgKswM1Rz0ulwv99U%252FScreenshot%25202024-07-05%2520at%25205.41.32%25E2%2580%25AFPM.png%3Falt%3Dmedia%26token%3D952a3eb1-d657-4cd0-b4b1-15e8f9b9a1e3\&width=768\&dpr=4\&quality=100\&sign=33a1f28e\&sv=1)

Check the first 2 boxes under the **"Firewall"** section.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2F1628445806-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FoML8XLjdWBoYbtGBoQ9R%252Fuploads%252FauhtuR8RFFuvSNBIsHYH%252Fimage.png%3Falt%3Dmedia%26token%3Dfa1bc013-420f-441f-968d-92fe40e4b1f6\&width=768\&dpr=4\&quality=100\&sign=3f13012\&sv=1)

Once you are done, click on the **"Create"** button at the bottom of the screen.

**Expected output:** You should see your VM instance coming online after loading for a few seconds

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2Fd2RvuOp5KBWjY7ENwrzT%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=654773d9\&sv=1)

Click on the dropdown beside the **"SSH"** column and select **"Open in browser window".** Click on **"Authorize"** when prompted.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2F2Q2YLvmx1mbGgZ94FI8O%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=69649c14\&sv=1)

**Expected output:** Wait for the new window to load and your Ubuntu terminal will appear.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FffOailZ336whxXaTrYX7%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=1968ac6d\&sv=1)

Once you are logged into your VM via SSH, run a general update using the command below.

Copy

```
sudo apt update -y && sudo apt upgrade -y
```

Then, jump straight into the `Device level security setup` section next.
