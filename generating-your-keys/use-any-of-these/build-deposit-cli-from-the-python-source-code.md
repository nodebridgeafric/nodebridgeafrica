# Build deposit-cli from the Python source code

### Build deposit-cli from the Python source code

**Install python3.7+**

The python3 install process may differ depending on your linux build.If you need help, check out the Python documentation.

[Python installation instructions](https://python.org/about/gettingstarted)

You can check your Python version by typing python3 -V in your terminal.

**Install pip3**

You can install pip using a Linux Package Manager like apt or yum.

[More on installing pip](https://packaging.python.org/guides/installing-using-linux-tools/#installing-pip-setuptools-wheel-with-linux-package-managers)

**Install virtualenv**

virtualenv would help you to create an isolated Python environment for deposit-cli tool.[More on virtualenv](https://virtualenv.pypa.io/en/latest/installation.html)

**Install deposit-cli tool**

Download and uncompress the master branch source code from [GitHub.](https://github.com/ethereum/staking-deposit-cli/archive/master.zip)

If you’re a git user, you can run git clone -b master --single-branch https://github.com/ethereum/staking-deposit-cli.git to download the master branch. First, create a venv virtualenv under repository directory:

```
virtualenv venv
```

```
source venv/bin/activate
```

Second, install the dependency packages:

```
python3 setup.py install
```

```
pip3 install -r requirements.txt
```

**Generate deposit keys using the Ethereum Foundation deposit tool**

For security, we recommend you disconnect from the internet to complete this step.Type the following lines into the terminal window:

```
python3 ./staking_deposit/deposit.py new-mnemonic --num_validators 1 --chain mainnet  
```

Make sure you have set --chain mainnet for Mainnet, otherwise the deposit will be invalid.If you have questions about deposit-cli, please visit the GitHub repository.[https://github.com/ethereum/staking-deposit-cli](https://github.com/ethereum/staking-deposit-cli)
