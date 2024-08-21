# Install and prepare the OS

### Flash Ubuntu OS on USB Drive <a href="#flash-ubuntu-os-on-usb-drive" id="flash-ubuntu-os-on-usb-drive"></a>

#### Download the latest version of Ubuntu <a href="#download-the-latest-version-of-ubuntu" id="download-the-latest-version-of-ubuntu"></a>

Now that you have assembled your hardware, you will need to install the Ubuntu OS onto your device. To do that, we will need to **create a bootable USB drive flashed with the latest Ubuntu OS.** Follow the steps below:

1. Prepare a new USB drive of at least 8GB
2.  On your working laptop, download the latest version of Ubuntu here (this might take around 30 minutes**)** - [https://ubuntu.com/download/desktop](https://ubuntu.com/download/desktop) -

    ![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2F0eGjJ7pX72f35iH9fQPG%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=68669e0\&sv=1)
3. Once the download is complete, you will need to verify the checksum of the downloaded file to ensure it has not been tampered with during the download

#### Verify the checksum of download <a href="#verify-the-checksum-of-download" id="verify-the-checksum-of-download"></a>

Click on "verify your download" and you should see a window appearing.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FAYbIhGU19H1TEJlIvlIE%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=f4bf8b3e\&sv=1)

Open up your terminal (Mac) or Windows Power Shell (Windows) and run the following commands.

Copy

```
cd Downloads
echo "a435f6f393dda581172490eda9f683c32e495158a780b5a1de422ee77d98e909 *ubuntu-22.04.3-desktop-amd64.iso" | shasum -a 256 --check
```

You are good to go if you see an "OK" in the output.

Copy

```
ubuntu-22.04.3-desktop-amd64.iso: OK
```

#### Download an ISO writer <a href="#download-an-iso-writer" id="download-an-iso-writer"></a>

After we download the ISO file of the latest Ubuntu version, we will need a tool to write this ISO file into the USB drive so that it is bootable when plugged into your NUC.

1. Download and install BalenaEtcher - [https://etcher.balena.io/](https://etcher.balena.io/)
2.  Open up BalenaEtcher and choose select flash from file

    ![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2Fg29KYamHDEt77TIf6YA5%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=f6cdfcb3\&sv=1)
3.  Select your new USB drive under the "Select target" option

    ![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FHMH2948EA8su5TecGNsH%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=9fb09161\&sv=1)
4.  Hit the "Flash!" button and wait for the process to complete

    ![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FKdj4PSzOrLZ9EYh5dDLx%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=7f69cd4d\&sv=1)

### Install Ubuntu on your NUC <a href="#install-ubuntu-on-your-nuc" id="install-ubuntu-on-your-nuc"></a>

You will need to connect your NUC device to a keyboard and monitor for the installation process

Plug your bootable USB drive into your NUC device and turn it on. Select `Try or Install Ubuntu` from the boot menu.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FbYXA0nF83TTtfm7Kza2U%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=12d3cb6c\&sv=1)

Choose the following options when prompted:

1. Install Ubuntu (not Try)
2. _**Connect to the WIFI network of your Node Router**_
3. Minimal installation + Download updates while installing Ubuntu
4. Erase disk and install Ubuntu
5. Set your username and password + "Require my password to login"
6. Restart your device
7. Skip connecting to your online accounts
8. Skip setting up Livepatch
9. Select "No, don't send system info"
10. Disable location services

Your NUC device is now installed with the Ubuntu OS.

#### Install the SSH Server <a href="#install-the-ssh-server" id="install-the-ssh-server"></a>

Open up the Ubuntu terminal on your NUC by pressing `CTRL + ALT + T` and perform the following:

1\) General updates

Copy

```
sudo apt update -y && sudo apt upgrade -y
```

2\) Install the ssh server

Copy

```
sudo apt install openssh-server
```

3\) Get the IP address of your NUC device within your Node Router subnet.

Copy

```
ip a
```

**Expected output:**

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FxY9t0TWnLkkyvCGPqUSn%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=7bf744a9\&sv=1)

Your NUC's IP address will be located under the `wl01` interface - e.g. 192.168.xx.xx.

Write this down as you will need to use this IP address to access your NUC remotely and we will call this the `node_IP_address` moving forward.

You can now access your NUC (`Node`) remotely by running the following command while you are in the Node Router subnet and entering the password of the Node when prompted.

Copy

```
ssh <username>@<node_IP_address> -v
```

**Note:** This command will change slightly once you properly secure your Node device in the next section.

### Prepare your OS <a href="#prepare-your-os" id="prepare-your-os"></a>

#### Install useful packages <a href="#install-useful-packages" id="install-useful-packages"></a>

Copy

```
sudo apt install curl jq htop
```

* `curl` allows you to query IP addresses, URLs, and the endpoints of internal services directly to test for connectivity and downloading files from the internet
* `jq` is a formatting package
* `htop` is a system monitoring tool

#### Configure timekeeping <a href="#configure-timekeeping" id="configure-timekeeping"></a>

We need to make sure the time on our device is the same with all other nodes so that we are able to sync with everyone else. If our timekeeping is off, we will start missing attestations (and rewards!). Verify this by running:

Copy

```
timedatectl
```

And check that NTP service is “active”. See screenshot below.

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FLrcreSakAXMiuG8jSrQ6%2FUntitled%2520%286%29.png\&width=768\&dpr=4\&quality=100\&sign=60927f98\&sv=1)

If not, turn it on by running:

Copy

```
sudo timedatectl set-ntp on
```

#### **Create a Swap Space** <a href="#create-a-swap-space" id="create-a-swap-space"></a>

A swap space _(”back-up” memory space carved out from disk space)_ is used to prevent out-of-memory errors.

Recommended swap space:

Copy

```
RAM     Swap Size
  8GB           3GB
 12GB           3GB
 16GB           4GB
 24GB           5GB
 32GB           6GB
 64GB           8GB
128GB          11GB
```

Disable existing swap:

Copy

```
sudo swapoff /swapfile
```

Create swap file:

Copy

```
sudo fallocate -l 6G /swapfile 
sudo chmod 600 /swapfile 
sudo mkswap /swapfile 
sudo swapon /swapfile
```

Make your OS remember the swap space settings even after rebooting:

Copy

```
sudo cp /etc/fstab /etc/fstab.bak
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
sudo sysctl vm.swappiness=10
sudo sysctl vm.vfs_cache_pressure=50
sudo nano /etc/sysctl.conf
```

Add the following to the end of the `sysctl.conf` configuration file:

Copy

```
vm.swappiness=10
vm.vfs_cache_pressure=50
```

Save and exit the file with `CTRL + O, enter, CTRL + X`

Check your new swap space with the following commands.

Copy

```
htop
free -h
```

_**Expected output:**_

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FtwS5ZYurAAETnNsBV1tH%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=fc964a42\&sv=1)

`htop`

![](https://dvt-homestaker.stakesaurus.com/\~gitbook/image?url=https%3A%2F%2Fcontent.gitbook.com%2Fcontent%2FoML8XLjdWBoYbtGBoQ9R%2Fblobs%2FhO52uxCQW7iTd2UaBqIF%2Fimage.png\&width=768\&dpr=4\&quality=100\&sign=eb3042bc\&sv=1)

`free -h`
