# 🗃️ Resources and links

{% hint style="warning" %}
Shoutout to [AlexaGawddess](https://twitter.com/AlexaGawddess) for providing inspiration on the structure of this page
{% endhint %}

## Become a Ninja and access Runes Camp <a href="#communities" id="communities"></a>

Pizza Ninja Collection: [https://magiceden.io/ordinals/marketplace/pizza-ninjas](https://magiceden.io/ordinals/marketplace/pizza-ninjas)

## bitcoin.conf file update <a href="#communities" id="communities"></a>

{% hint style="info" %}
If you did not follow this Ninja Mac Guide from the beginning, then you need to first check and make sure your directories and tooling are correctly setup. You need to check that your files are in your [SSD/Bitcoin folder as described here](faqs.md#update-bitcoin-directory-if-needed) (3 mins effort), and you need to make sure your SSD is named "Bitcoin", if not, then follow these steps to [Update your SSD name to Bitcoin](faqs.md#update-ssd-name-to-standardized-name-so-all-commands-work) (2 mins effort) so all standardized commands will work. Additionally, make sure you have installed all tools from [here](../fundamentals/install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md) (10 mins effort). Then you can proceed to the instructions below.
{% endhint %}

### bitcoin.conf File contents

```bash
# Pizza Ninjas Bitcoin Ord Runes Config File - FAST
txindex=1
assumevalid=000000000000000000025820df002cd81b8bd78e6c64c1791962c8a91b46f54e
server=1
```

1. Press `cmd+space` on your keyboard, this will open a search bar (spotlight search)
2.  Type `terminal` and open the terminal app as shown below\


    <figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>
3. Now copy and paste the following com

{% code overflow="wrap" %}
```bash
mkdir -p /Volumes/Bitcoin/Bitcoin
echo -e "# Pizza Ninjas Bitcoin Ord Runes Config File - FAST\ntxindex=1\nassumevalid=000000000000000000025820df002cd81b8bd78e6c64c1791962c8a91b46f54e\nserver=1" > /Volumes/Bitcoin/Bitcoin/bitcoin.conf
```
{% endcode %}

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

11. The above command will create a "Bitcoin" folder in your SSD which is also named "Bitcoin". It will also add the the Pizza Ninja super speed configuration file so your node can run at Ninja speed.
12. (Optional) You can check that this the folder and file mentioned in the previous step have been created properly by opening your SSD and checking to see that there is now a "Bitcoin" folder and within that folder is a "bitcoin.conf" file. \


    <figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>
13. (Optional) You can check that your bitcoin.conf file is created correctly by typing this command in terminal

```bash
cat /Volumes/Bitcoin/Bitcoin/bitcoin.conf
```

14. This should output a result as shown below\


    <figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
15. Woohoo! Time for Pizza! Your `bitcoin.conf` file is updated.

## Communities <a href="#communities" id="communities"></a>

The Ordicord: [https://discord.gg/ordinals](https://discord.gg/ordinals) - amazing group of helpful people who can help you troubleshoot.

NinjaAlerts Discord: [https://discord.gg/ninjalerts](https://discord.gg/ninjalerts) - Ninja Alerts holders have access to this guide and a chat where I am actively helping.

Based Discord: [https://discord.gg/bpUJvgpAhp](https://discord.gg/bpUJvgpAhp) Amazing group of artists, builders, and creators in the Ordinals space. This is my baby and wanted to share.

## Installation links <a href="#installation-links" id="installation-links"></a>

Bitcoin Core Download: [https://bitcoincore.org/en/download/](https://bitcoincore.org/en/download/)

Visual Studio: [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

Homebrew: [https://brew.sh/](https://brew.sh/)

## Ord clients <a href="#ord-clients" id="ord-clients"></a>

Casey's OG Ord Client: [https://github.com/ordinals/ord](https://github.com/ordinals/ord)

Greg's Forked Ord Client: [https://github.com/gmart7t2/ord](https://github.com/gmart7t2/ord)

## People to follow

In no particular order, here are some people you may want to follow on Twitter.

[Trevor](https://twitter.com/TO)

[Leonidas](https://twitter.com/LeonidasNFT)

[Alexa](https://twitter.com/AlexaGawddess)

[Taha Abbasi](https://twitter.com/tahaabbasi)

[Rare Satoshi Society](https://twitter.com/RareSatSociety)

[Nullish](https://twitter.com/null\_ish)

[Franken](https://twitter.com/ItsFranken)

[Udi Wertheimer](https://twitter.com/udiWertheimer)

[BitGod](https://twitter.com/BitGod21)

[zk-Shark](https://twitter.com/ZK\_shark)

[Dazza9x](https://twitter.com/dazza9x)

[H.O](https://twitter.com/Hosman\_NFT)

[Casey Rodarmor](https://twitter.com/rodarmor)

[Ordinally](https://twitter.com/veryordinally)

[Raph](https://twitter.com/raphjaph)

[Danny Huuep](https://twitter.com/huuep)

[TimechainOrd](https://twitter.com/timechainord)

[Erin](https://twitter.com/realizingerin)

[Psifour](https://twitter.com/psifour)

[CBSpears](https://twitter.com/cbspears)

[Rijndael](https://twitter.com/rot13maxi)

[Paz](https://twitter.com/pazNGMI)

