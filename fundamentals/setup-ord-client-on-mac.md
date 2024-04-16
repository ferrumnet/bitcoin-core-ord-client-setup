# ⚙️ Setup Ord Client on Mac

{% hint style="danger" %}
Updating Do not follow yet. Will be updated in the next hour
{% endhint %}

## Prerequisite

Make sure you setup your Bitcoin Node and it has finished syncing before you setup the Ord Client

If you haven't completed the prerequisite, use the following link to complete those steps first.&#x20;

{% content-ref url="run-a-bitcoin-node-in-three-easy-steps.md" %}
[run-a-bitcoin-node-in-three-easy-steps.md](run-a-bitcoin-node-in-three-easy-steps.md)
{% endcontent-ref %}

## Ord Setup (Mac)

{% hint style="info" %}
Shoutout to [Matt](https://twitter.com/MattLxNFT) for putting this together :clap:. Give hiim a follow [@MattLxNFT](https://twitter.com/MattLxNFT)

Additional shoutouts to Casey for the [OG Ord Client](https://github.com/ordinals/ord), Greg for the contributions and update to [Ord Client](https://github.com/gmart7t2/ord). [AlexaGawddess](https://twitter.com/AlexaGawddess) for the Windows version of this guide [here](https://guide.ordinalshelp.com/bitcoin-core-ord-client-setup-on-windows/installing-ord-client).  [Trevor](https://twitter.com/tahaabbasi), for organizing the largest node running initiative in Bitcoin's history!
{% endhint %}

Here are the highlevel steps we are going to take to setup our Ord client

1. Download and install Ord with Homebrew
2. Download pre-built Ord Index (Without Runes) from [https://ordstuff.info/indexes/](https://ordstuff.info/indexes/) using Transmission
   1. Rename the file to `index.redb`
3. Setup our Ord directory and move `index.redb`
4. Start indexing Ord

## Download and install Ord with Homebrew

1. If you don't have terminal open already the, press `cmd+space` on your keyboard, this will open a search bar (spotlight search)
2.  Type `terminal` and open the terminal app as shown below\


    <figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>
3. With brew, installing ord is as easy as this command

{% hint style="info" %}
Copy and paste the following command in terminal then press enter
{% endhint %}

```bash
brew install ord
```



## Setup our Ord directory

1. Connect the SSD External Drive to your Mac
2. Press `cmd+space` on your keyboard, this will open a search bar (spotlight search)
3.  Type `terminal` and open the terminal app as shown below\


    <figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>
4. Now copy and paste the following command, then press enter

{% code overflow="wrap" %}
```bash
mkdir -p /Volumes/Bitcoin/Ord
```
{% endcode %}

5. The above command will create a "Bitcoin" folder in your SSD which is also named "Bitcoin". It will also add the the Pizza Ninja super speed configuration file so your node can run at Ninja speed.

