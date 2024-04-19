# 📝 Quick Commands for Runes by Taha Abbasi

{% hint style="info" %}
You need to run Bitcoin node, and Order Server to run most of these commands.&#x20;
{% endhint %}

1. [Start Ord Server](quick-commands-for-runes-by-taha-abbasi.md#start-ord-server)
2. [Safely stop Ord Server](quick-commands-for-runes-by-taha-abbasi.md#safely-stop-ord-server)
3. [Create Wallet](quick-commands-for-runes-by-taha-abbasi.md#create-wallet)
   1. Default
   2. Named
4. [Receive Wallet](quick-commands-for-runes-by-taha-abbasi.md#receive-wallet)
   1. Default
   2. Named
5. [Mint](quick-commands-for-runes-by-taha-abbasi.md#mint-a-rune)
   1. Default postage
   2. Custom postage

## Start Ord Index (or Update Ord Index)

{% hint style="warning" %}
Before you start the order server, you need make sure that you have Bitcoin Core running and it has finished syncing. Once the Ord sync starts, do not close it, even if it seems to be stuck. Some blocks can take a long time, closing Ord sync in the middle has caused issues before.
{% endhint %}

{% code overflow="wrap" %}
```bash
ord --index /Volumes/Bitcoin/Ord/index.redb --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie index update
```
{% endcode %}

## Start Ord server

{% hint style="warning" %}
Before you start the order server, you need make sure that you have Bitcoin Core running and it has finished syncing
{% endhint %}

{% code overflow="wrap" %}
```bash
ord --index /Volumes/Bitcoin/Ord/index.redb --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie server
```
{% endcode %}

## Safely stop Ord Server

{% hint style="warning" %}
When you run the command to close the Ord Server, it presents you with an option to type the same command again and force close the server. DO NOT PRESS the command twice. It is highly likely you will corrupt your Ord Index and will need to restart your sync.&#x20;
{% endhint %}

```bash
CTRL+C
```

{% hint style="info" %}
Generally speaking the order to close systems should be.&#x20;

1. Close Sparrow (if open)
2. Safely close Ord Server
3. Close Bitcoin Core
{% endhint %}

## Create Wallet

### Default Wallet

You can only run the `wallet create` command once without a `--name` flag. The first time you run this command Ord creates a default wallet for you. Every other wallet must be created with a `--name` flag.

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet create
```
{% endcode %}

### Named Wallet

To create additional wallets after the first one, you need to use the named wallet command. Use the naming convention ninj-demo i.e. small caps, no spaces, use hyphen `-` instead of spaces.

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet --name enter-wallet-name-here create
```
{% endcode %}

Example: If I wanted to name a wallet Pizza Ninja, I would name it as follows:

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet --name pizza-ninja create
```
{% endcode %}

## Receive Wallet

### Default Wallet

The first time you ran wallet create (without a `--name` flag) command Ord created a default wallet for you. To receive an address from this wallet, you can type the following command

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet receive
```
{% endcode %}

{% hint style="info" %}
Everytime you run a receive command, Ord will provide the next deterministic address in your wallet. Each of these addresses belong to the same wallet, you can see them easily in Sparrow wallet if you load your wallet in there.
{% endhint %}

### Named Wallet

To receive addresses for additional wallets created with a `--name` flag, you need to use the named wallet command.&#x20;

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet --name enter-wallet-name-here receive
```
{% endcode %}

Example: If I wanted to name a wallet Pizza Ninja, I would name it as follows:

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet --name pizza-ninja receive
```
{% endcode %}

## Mint a Rune

By default, if you don't pass a postage flag, the amount of postage is set to 10,000 sats. Postage are the number of sats used in the UTXO where the Runes are isncribed and sent to you.

### Default Postage with default ord wallet

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet mint --fee-rate enterFeeRateHere --rune enter-rune-name-here --destination enterDestinationXverseOrUniSatOrdinalsAddressHere
```
{% endcode %}

#### Example

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet mint --fee-rate 200 --rune PIZZA•NINJA --destination enterDestinationXverseOrUniSatOrdinalsAddressHere
```
{% endcode %}

### Default Postage with named ord wallet

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet --name enterWalletNameHere mint --fee-rate enterFeeRateHere --rune enter-rune-name-here --destination enterDestinationXverseOrUniSatOrdinalsAddressHere
```
{% endcode %}

#### Example

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet --name ninja-demo mint --fee-rate 100 --rune PIZZA•NINJA --destination enterDestinationXverseOrUniSatOrdinalsAddressHere
```
{% endcode %}

### Custome Postage with default ord wallet

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet mint --fee-rate enterFeeRateHere --rune enter-rune-name-here --destination enterDestinationXverseOrUniSatOrdinalsAddressHere --postage enterPostageAmountThensats
```
{% endcode %}

#### Example

{% code overflow="wrap" %}
```bash
ord --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie --data-dir /Volumes/Bitcoin/Ord wallet mint --fee-rate 200 --rune PIZZA•NINJA --destination enterDestinationXverseOrUniSatOrdinalsAddressHere --postage 600sats
```
{% endcode %}
