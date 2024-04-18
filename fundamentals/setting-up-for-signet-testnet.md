# 🚧 Setting up for Signet (Testnet)

In order to setup for Signet, you will need to do the following steps for the first time.

1. Setup and sync Bitcoin Core (QT) to run on Signet
2. Setup and sync Ord on Signet

Completing the above steps is relatively simple, it requires an update of the bitcoin.conf file and a few commands. I have prepared a simply script that you can run which will make switching between mainnet and signet a breeze.&#x20;

## Setup your Bash File to toggle between mainnet and signet config

1. Open terminal and enter the following command

```bash
mkdir -p /Volumes/Bitcoin/resources
touch /Volumes/Bitcoin/resources/update_bitcoin_conf.sh
chmod +x /Volumes/Bitcoin/resources/update_bitcoin_conf.sh
open /Volumes/Bitcoin/resources/update_bitcoin_conf.sh
```

This will open the `update_bitcoin_conf.sh` file on your screen as shown below

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

2. Now you need to copy and paste the following code in this new `update_bitcoin_conf.sh` file as shown below

```bash
#!/bin/bash

# Define the path to the Bitcoin configuration file
CONFIG_FILE="/Volumes/Bitcoin/Bitcoin/bitcoin.conf"

# Check for the network type argument
if [[ $1 == "mainnet" ]]; then
  # Configuration for mainnet
  echo -e "# Pizza Ninjas Bitcoin Ord Runes Config File - FAST\ntxindex=1\nassumevalid=000000000000000000025820df002cd81b8bd78e6c64c1791962c8a91b46f54e\nserver=1" > $CONFIG_FILE
  echo "Updated configuration for mainnet."
elif [[ $1 == "testnet" ]]; then
  # Configuration for testnet (Signet)
  echo -e "# Pizza Ninjas Bitcoin Ord Runes Config File - FAST\ntxindex=1\nassumevalid=000000000000000000025820df002cd81b8bd78e6c64c1791962c8a91b46f54e\nserver=1\n\n[signet]\ntxindex=1\nserver=1" > $CONFIG_FILE
  echo "Updated configuration for testnet (Signet)."
else
  echo "Invalid argument. Please use 'mainnet' or 'testnet'."
fi

```

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Now you have the script ready to toggle between mainnet and signet configs. :pizza:

## Switch between mainnet and signet configs

### Command to set mainnet config

```bash
/Volumes/Bitcoin/resources/update_bitcoin_conf.sh mainnet
```

### Command to set Signet config

```
/Volumes/Bitcoin/resources/update_bitcoin_conf.sh testnet
```

## Set config to Signet and start Bitcoin Core Signet sync

Now we'll set the config to signet, if you haven't already done so, and start Bitcoin Core to sync with Signet. Here are the steps:

1. If you have Ord server running close that in terminal with `CTRL+C` only type `CTRL+C` once, do not press it twice, it will corrupt the index. Once Ord server is closed (if it was running) close Bitcoin Core safely if it is running by pressing `CMD+Q`. Wait for these to close then proceed.
2. Set config to Signet if you haven't already done so, if you can't remember just run the following command again in terminal

**Command to set signet config**

```
/Volumes/Bitcoin/resources/update_bitcoin_conf.sh testnet
```

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

3. Now you have the Signet config, to open the Bitcoin Core app using signet, we need to do it from terminal. So open terminal and paste in the following command, then hit enter. This will open Bitcoin Core with a green icon and start syncing Signet as shown below

### Command to start Bitcoin Core on signet

```bash
/Applications/Bitcoin-Qt.app/Contents/MacOS/Bitcoin-Qt -signet
```

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

4. Your Bitcoin Core will open on Signet and start syncing. A few things to note, syncing Signet will be quick relative to mainnet. The whole synce can be done in about 1-2 hours. The Bitcoin Core Icon will be green when connected to Signet vs Mainnet. When Bitcoin Core is connected to mainnet it will be Orange / Yellowish color\


<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## Start Ord Signet Sync

1. There should be a window already running the Signet Bitcoin core. We need to open another window to start the Ord Signet sync. To do this, head over to the terminal window currently open, click anywhere in the black area of the terminal window, then on your keyboard press `CMD+N`. This will open a new window as shown.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

2. Now you can start the indexing of Ord on Signet by copy and pasting the following command in terminal

{% code overflow="wrap" %}
```bash
ord --signet --cookie-file /Volumes/Bitcoin/Bitcoin/signet/.cookie --data-dir /Volumes/Bitcoin/Ord --index-runes index run
```
{% endcode %}

This will start the indexing Ord and Runes on Signet as shown below

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

3. If you see the following error, just type the command again and run it.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

4. This will go fast, once it's done, you will see a new line starting with `~`. This means Ord testnet is indexed. :pizza::ninja:
