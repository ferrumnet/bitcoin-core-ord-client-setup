# ⁉️ FAQs - Common Issues and Resolutions

## Ord Index Error | Code -5 message No such mempool transaction

### The error

{% code overflow="wrap" %}
```bash
███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████░ 838792/839401[2024-04-15T23:57:47Z ERROR ord::index::updater] Couldn't receive txs failed to fetch raw transaction: code -5 message No such mempool transaction. Blockchain transactions are still in the process of being indexed. Use gettransaction for wallet transactions.
```
{% endcode %}

### The solution

Thanks to [Post Capone](https://twitter.com/p0stc4p0n3) for sharing the solution.&#x20;

To fix this, you need to take the following steps

1. Add `reindex=1` to your `bitcoin.conf` file.&#x20;
2. Open Bitcoin Core and let bitcoin finish the reindex (usually takes an hour or two)
3. After the reindex is completed you need to remove `reindex=1` from your `bitcoin.conf` file
4. Now you can proceed with the [ord index](../fundamentals/setup-ord-client-on-mac.md#start-indexing-ord)

## Ord Client cookie file not found or related error

### The error

If you are facing an error similar to the one shown below:

```bash
error: cookie file /Volumes/Bitcoin/Bitcoin/.cookie does not exist
```

When you typed the command (see below) in step 6 under the [Build the Ord Index](https://mattonchain.github.io/notes-on-a-chain/ord-setup.html#build-the-ord-index)  section of the ord setup guide by mattonchain

```bash
ord --index /Volumes/Bitcoin/Ord/index.redb --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie index
```

### The solution

Then you may have two issues to resolve.&#x20;

1. [Update Bitcoin Directory (If Needed)](faqs-common-issues-and-resolutions.md#update-bitcoin-directory-if-needed)
2. [Update SSD name to standardized name so all commands work](faqs-common-issues-and-resolutions.md#update-ssd-name-to-standardized-name-so-all-commands-work)

To check if your Bitcoin Directory is correct or if you need to update it, see the [Update Bitcoin Directory (If Needed) first](faqs-common-issues-and-resolutions.md#update-bitcoin-directory-if-needed), then proceed to [Update SSD name to standardized name so all commands work](faqs-common-issues-and-resolutions.md#update-ssd-name-to-standardized-name-so-all-commands-work). After doing these steps, run the command again and you should be golden. :pizza::ninja:

## Update Bitcoin Directory (If Needed)

1. First we'll check if you need to update the Bitcoin directory. To check, open your SSD, and check if your files are in a "Bitcoin" folder in the SSD, or directly in the SSD with no Bitcoin Folder.
2.  If your files are in a "Bitcoin" folder in the SSD, then you don't need to update the directory. You can proceed to the "Update Path of command to build ord index" section below.\


    <figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption><p>Files are in SSD - Bitcoin Folder - No Directory Update needed</p></figcaption></figure>


3.  If your files are NOT in the Bitcoin folder in the SSD (As shown below), then you need to update your directory using the steps listed below. (Follow them exactly)\


    <figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption><p>Files are not in a Bitcoin Folder in SSD, instead are sitting in the SSD directly without Bitcoin Folder</p></figcaption></figure>


4. Quit Bitcoin Core (QT) app by pressing `CMD+Q`
5. Open your SSD in Finder
6.  Create a new folder named Bitcoin\


    <figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
7. Move all your files in this folder
8.  Eject your drive safely as shown in the screen shot\


    <figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>
9. Open Bitcoin Core (QT) - While your SSD is disconnected
10. It will open the directory selection, type Bitcoin to the end of the directory path as shown .- Do not Click OK yet\


    <figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>
11. Now connect your SSD and wait about 30 seconds to a minute
12. After 30 seconds to a minute, click ok
13. Bitcoin Core (QT) will now sync with the new directory

## Update SSD name to standardized name so all commands work

1. Update SSD name to "Bitcoin" if it is not already named Bitcoin.&#x20;
2. [Safely quit Bitcoin Core and Ord Server (if running)](../fundamentals/setup-ord-client-on-mac.md#safely-close-ord-client)
3. Connect the SSD External Drive to your Mac
4. Open `Disk Utility` by searching in spotlight search
5.  If needed, update view to show all devices as shown in the screenshot below\


    <figure><img src="../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>
6.  Right click on your SSD and click Rename\


    <figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>
7.  After you click rename, the name field will become editable as shown below. Rename this SSD to `Bitcoin` and then hit enter\


    <figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>
8. Go to Finder and there, you need to Eject the newly named "Bitcoin" drive safely
9.  Eject your drive safely as shown in the screen shot (NOTE: your drive will say "Bitcoin" as the name now)\


    <figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>
10. Open Bitcoin Core (QT) - While your SSD is disconnected
11. You will see a pop-up as shown below, here select `Use a custom data directory`, then navigate to and select your External SSD named "Bitcoin" drive as shown in the image below\


    <figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>
12. After 30 seconds to a minute, click `OK` your node should start to sync.&#x20;
13. Bitcoin Core (QT) will now sync with the new directory
14. Now you can run the command to index the node

{% code overflow="wrap" %}
```bash
ord --index /Volumes/Bitcoin/Ord/index.redb --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie index update
```
{% endcode %}
