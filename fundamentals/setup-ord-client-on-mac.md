# ⚙️ Setup Ord Client on Mac

## Prerequisite

Make sure you setup your Bitcoin Node and it has finished syncing before you setup the Ord Client

If you haven't completed the prerequisite, use the following link to complete those steps first.&#x20;

{% content-ref url="run-a-bitcoin-node-in-three-easy-steps.md" %}
[run-a-bitcoin-node-in-three-easy-steps.md](run-a-bitcoin-node-in-three-easy-steps.md)
{% endcontent-ref %}

{% hint style="info" %}
If you did not follow this Ninja Mac Guide from the beginning, then you need to first check and make sure your directories and tooling are correctly setup. You need to check that your files are in your [SSD/Bitcoin folder as described here](../resources/faqs-common-issues-and-resolutions.md#update-bitcoin-directory-if-needed) (3 mins effort), and you need to make sure your SSD is named "Bitcoin", if not, then follow these steps to [Update your SSD name to Bitcoin](../resources/faqs-common-issues-and-resolutions.md#update-ssd-name-to-standardized-name-so-all-commands-work) (2 mins effort) so all standardized commands will work. Additionally, make sure you have installed all tools from [here](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md) (10 mins effort). Then you can proceed to the instructions below.
{% endhint %}

## Ord Setup (Mac)

{% hint style="info" %}
Shoutout to [Matt](https://twitter.com/MattLxNFT) for putting this together :clap:. Give hiim a follow [@MattLxNFT](https://twitter.com/MattLxNFT)

Additional shoutouts to Casey for the [OG Ord Client](https://github.com/ordinals/ord), Greg for the contributions and update to [Ord Client](https://github.com/gmart7t2/ord). [AlexaGawddess](https://twitter.com/AlexaGawddess) for the Windows version of this guide [here](https://guide.ordinalshelp.com/bitcoin-core-ord-client-setup-on-windows/installing-ord-client).  [Trevor](https://twitter.com/tahaabbasi), for organizing the largest node running initiative in Bitcoin's history!
{% endhint %}

Here are the highlevel steps we are going to take to setup our Ord client

1. [Download and install Ord with Homebrew](setup-ord-client-on-mac.md#download-and-install-ord-with-homebrew)
2. [Download pre-built Ord Index (Without Runes)](setup-ord-client-on-mac.md#download-pre-built-ord-index-without-runes) from [https://ordstuff.info/indexes/](https://ordstuff.info/indexes/) using Transmission
   1. Rename the file to `index.redb`
3. [Setup our Ord directory](setup-ord-client-on-mac.md#setup-our-ord-directory) and move `index.redb`
4. [Start indexing Ord](setup-ord-client-on-mac.md#start-indexing-ord)
5. Start Ord Server

## Download and install Ord with Homebrew

{% hint style="warning" %}
Make sure you have installed Homebrew as per the instructions in the Install Tools section. If not, then click here ([#install-homebrew](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#install-homebrew "mention")) to install Homebrew first.
{% endhint %}

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

<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

4. After you hit enter, brew starts installing ord. You should see a screen similar to the one shown below when the installation is complete

<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

5. To verify that the installation worked correctly, you can try the following command

{% hint style="info" %}
Copy and paste the following command in terminal then press enter
{% endhint %}

```bash
ord --version
```

<figure><img src="../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

6. That's it for Ord installation, you have installed Ord, now we'll setup other parts to run and index Ord. :pizza:

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Download pre-built Ord Index (Without Runes)&#x20;

{% hint style="warning" %}
Make sure you have installed Transmission as per the instructions in the Install Tools section. If not, then click here ([#install-transmission](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#install-transmission "mention")) to install Transmission first.
{% endhint %}

Now we will download the pre-built index to save us time. The pre-built Ord index already has a large number of blocks synced, so it will reduce the time needed to sync the remaining blocks. Here are the steps:

1. Make sure your Transmission App is open, if not, you can open it by right clicking on it and then clicking open in Applications Folder

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

2. You may see a warning message like the one shown below when you first open Transmission. Simply click Open here to proceed

<figure><img src="../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

3. Now, let's go get the pre-built Index. Go to [https://ordstuff.info/indexes/](https://ordstuff.info/indexes/) and click on the latest release as shown below

<figure><img src="../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

4. Grab the Index release that has “without” in its name. This indicates it is an index that doesn’t include a Runes Index. We don’t need Runes index for now.

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

5. When you click the file, a torrent file will be downloaded in your downloads folder and it will have an icon similar to Transmission App icon on it. Double click the file and it will open a new Transmission window

<figure><img src="../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

6. Simply select Add to proceed

<figure><img src="../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

7. Download should be in progress after selecting `Add`. When the download is completed, the file will be in the Downloads folder and will have a name similar to this: `index-0.18-without-838791.redb.gz. Note, yours may be slightly different.`

<figure><img src="../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

8. Double click on the index .gz file to decompress it as shown below

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

9. Once the decompression is completed, there will now be a file in your downloads named similar to this one: `index-0.18-without-838791.redb`. Yours migh be named slightly different, but it should end with start with index and end with .redb. You need to renam this file to index.redb as shown below

<figure><img src="../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

10. At this point you should have a file named index.redb in your downloads folder. Good job! You've downloaded a pre-built Ord index using a torrent system! Woohoo! :pizza:. Now let's move on to the [Setup our Ord Directory](setup-ord-client-on-mac.md#setup-our-ord-directory) step

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>





## Setup our Ord directory

1. Make sure you are not running Bitcoin Core before running the follow commands. To close Bitcoin Core (QT) if it is running, click on the app window for Bitcoin Core (QT) and press `CMD+Q`
2. Connect the SSD External Drive to your Mac
3. Press `cmd+space` on your keyboard, this will open a search bar (spotlight search)
4.  Type `terminal` and open the terminal app as shown below\


    <figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>
5. Now copy and paste the following command, then press enter

{% code overflow="wrap" %}
```bash
mkdir -p /Volumes/Bitcoin/Ord
rsync -ah --progress ~/Downloads/index.redb /Volumes/Bitcoin/Ord/
open /Volumes/Bitcoin/Ord
```
{% endcode %}

{% hint style="info" %}
The commands above will create an "Ord" folder inside your SSD (which is named Bitcoin) and it will move the index.redb file from your downloads folder to this nealy created Ord folder in the SSD. This process can take some time, in some cases over 10 minutes. Do not close the terminal or interfere with it after running the command.
{% endhint %}

<figure><img src="../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Do not exit terminal, it is moving the index.redb file which is over 70 GB from downloads on to your SSD. This can take some time, even up to 10 minutes plus. In the next screenshot I’ll show you what it looks like when the process is completed.
{% endhint %}

5. When the process is completed you will see the \~ text on the left of the terminal screen again, and your SSD Finder will open up with the Ord folder selected, which will have the `index.redb` file in it now.

<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

6. Wohoo! Now you have your `index.redb` in the right directory, and you've got a pre-built index, so we can proceed to the next step :pizza:, [Start indexing Ord](setup-ord-client-on-mac.md#start-indexing-ord).

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Start indexing Ord

{% hint style="warning" %}
Do not proceed with this step if your bitcoin node is not synced as shown in step 1 below.
{% endhint %}

1. Make sure Bitcoin Core (QT) applicaiton is running and synced as shown below

<figure><img src="../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>

2. If Terminal is not open, then press `cmd+space` on your keyboard, this will open a search bar (spotlight search)
3.  Type `terminal` and open the terminal app as shown below\


    <figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>
4. Now copy and paste the following command, then press enter

{% code overflow="wrap" %}
```bash
ord --index /Volumes/Bitcoin/Ord/index.redb --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie index update
```
{% endcode %}

{% hint style="warning" %}
If you are facing an error similar to the one shown below:

{% code overflow="wrap" %}
```bash
error: cookie file /Volumes/Bitcoin/Bitcoin/.cookie does not exist
```
{% endcode %}

It is highly likely that your directories are not setup in order to work with the commands in this guide. This is likely because you did not follow this guide from the beginning, or mixed up two guides. To solve this issue, you need to first check and make sure your directories and tooling are correctly setup. You need to check that your files are in your [SSD/Bitcoin folder as described here](../resources/faqs-common-issues-and-resolutions.md#update-bitcoin-directory-if-needed) (3 mins effort), and you need to make sure your SSD is named "Bitcoin", if not, then follow these steps to [Update your SSD name to Bitcoin](../resources/faqs-common-issues-and-resolutions.md#update-ssd-name-to-standardized-name-so-all-commands-work) (2 mins effort) so all standardized commands will work. Additionally, make sure you have installed all tools from [here](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md) (10 mins effort). Then you can proceed to the instructions below.
{% endhint %}

<figure><img src="../.gitbook/assets/image (65).png" alt=""><figcaption><p>The command to start Ord Index</p></figcaption></figure>

5. When the index starts succesfully, it looks like the image shown below. The indexing can take some time, up to 36 hours in some cases. However, since we downloaded a pre-built index, our Ord indexing should be completed in a few hours

<figure><img src="../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>

6. Once indexing completes you will see the bar go away, and terminal should be in a similar state to the screenshot shown below. This means you are ready to [start the Ord server](setup-ord-client-on-mac.md#start-ord-server)! :rocket:

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Backup your Ord Index (daily if possible)

1.  Do not run this command if your Ord client is indexing as shown below\


    <figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
2. If you have started Ord server, make sure to [safely quit the server](setup-ord-client-on-mac.md#safely-close-ord-client)
3. Make sure that Bitcoin Core is not running, you can quit it safely by clicking on the Bitcoin Core (QT) application window and pressing `CMD+Q`.
4. Then open terminal and run the following command

{% code overflow="wrap" %}
```bash
rsync -ah --progress /Volumes/Bitcoin/Ord/index.redb /Volumes/Bitcoin/Ord/index.redb.backup
open /Volumes/Bitcoin/Ord/
```
{% endcode %}

5. This will begin the process of copying the `index.rdb` file to a new file named `index.redb.backup`. The proces can take some time, during it's progress you will see the following screen on terminal

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

5. Wait for this to complete. Once complete, the Ord folder in your SSD will open, and you will see two files, `index.redb` and `index.redb.backup` both with the same size as shown below

{% hint style="info" %}
If you have an index.redb.backup file before from a previous backup, the command will overwrite this file with the backup, this is expected behavior.
{% endhint %}

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Start Ord Server

{% hint style="warning" %}
Once this process starts, do not quit your terminal with `CMD+Q`. If you want to safely exit, you must first press `CTRL+C`, you will see a notice that Ord is safely shutting down, when it is shut down, you will see a new terminal line with `~`. Anytime you see the last line starting with `~` it means the previous command is finished running. At this point, you can quit Terminal first, then quit Bitcoin core.
{% endhint %}

1. Start Bitcoin Core (QT) application if you don't have it running yet and wait for it to finish syncing
2. Once your indexing is complete in the previous section, you can enter the following command in terminal

{% code overflow="wrap" %}
```bash
ord --index /Volumes/Bitcoin/Ord/index.redb --cookie-file /Volumes/Bitcoin/Bitcoin/.cookie server
```
{% endcode %}

{% hint style="info" %}
Note when you enter this command, your terminal will show a blank line, this is normal. Terminal is not stuck, it's running the server. Proceed to the next step.
{% endhint %}

2. Open your browser (chrome, safari etc) and enter this url (go to the site listed below)

```bash
http://localhost
```

<figure><img src="../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

3. Woohoo! You did it! :pizza:You have installed Bitcoin Core, and you have installed and indexed Ord. Both of these setups are working as expected.&#x20;

{% hint style="danger" %}
Do not quit terminal once Ord server is running, it will corrupt the DB, and force you to re-sync. You must safely close Ord client once it's running. Do not close Bitcoin Core before safely closing Ord. See the Safely close Ord section to see how to shutdown safely.
{% endhint %}

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Safely close Ord Client

{% hint style="warning" %}
These steps must be followed in the order listed below to avoid data corruption. Once you have started the Ord server, do not quit your terminal with `CMD+Q`.&#x20;
{% endhint %}

1. Go to terminal where Ord client is running and press `CTRL+C`&#x20;

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
DO NOT PRESS `CTRL+C` again when you see the above notice. Wait for it to shut down.
{% endhint %}

2. You will see a notice that Ord is shutting down gracefully, when it is shut down, you will see a new terminal line with `~`. Anytime you see the last line starting with `~` it means the previous command is finished running.&#x20;
3. At this point, you can quit Terminal first with `CMD+Q`, then quit Bitcoin core.

## X account follow and shoutout

If the guide helped you, please consider [following me on X](https://twitter.com/tahaabbasi) [(@tahaabbasi](https://twitter.com/tahaabbasi)) and giving a shoutout to the mac guide created here. Maybe give a :pizza:in the Ninja Discord using `/pizza user:@officialtahaabbasi reason: anything you'd like to add here`. Thanks for your support!

{% content-ref url="../resources/donation-and-x-shout-out.md" %}
[donation-and-x-shout-out.md](../resources/donation-and-x-shout-out.md)
{% endcontent-ref %}
