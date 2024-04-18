# 🛠️ Install required tools, Homebrew, Oh My Zsh, Visual Studio, Rust,Transmission

Overview

We are going to install a few tools to make your Bitcoin Node running experience super easy. Don't worry, I know this page seems long, but think of it like shopping for ingredients for your perfect Pizza, we'll pick each item up from the grocery store, and put it all together in a delicious Pizza. So grab a slice and read on.

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Tools we are installing

1. [Homebrew - A package manager that makes it easy to install all things](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#install-homebrew)
2. [Oh My Zsh - A great tool to add privacy and make managing your terminal easy](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#install-oh-my-zsh)
3. [Visual Studio - Will make your life easy when interacting with any scripts we make](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#install-visual-studio-code)
4. [Rust - We need this for Ord setup, and other future activities](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#installing-rust)
5. [Transmission - To help us get pre-built Ord Indexes](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#install-transmission)

Let's get to it.&#x20;

## Install Homebrew

1. Press `cmd+space` on your keyboard, this will open a search bar (spotlight search)
2.  Type `terminal` and open the terminal app as shown below\


    <figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>
3. Now copy and paste the following command, then press enter

{% hint style="warning" %}
IMPORTANT: Do not get click happy, or type enter quickly, we need to type these commands in a very specific manner, so follow the guide exactly. Copy the command below, paste it in terminal and hit enter once.
{% endhint %}

{% code overflow="wrap" %}
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
{% endcode %}

4.  When you hit enter, it will ask for your computer password as shown below. When you type your password, nothing appears or changes on the screen. So carefully type your computer password and then hit enter\


    <figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>


5.  Then you will be presented with a confirmation screen, simply hit enter to continue\


    <figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>


6. Once you hit enter, the install process will begin. This can take sometime, between 2 to 10 minutes or more depending on your internet speed. Here is a 30x speed GIF of the install process on my machine

{% hint style="warning" %}
At the end of the install process there will be some commands provided by the installer that you need to enter. Make sure to see the next step before closing terminal.\

{% endhint %}

<figure><img src="../.gitbook/assets/Brew Install (1).gif" alt=""><figcaption></figcaption></figure>

7. Once the install process is finished, you will see the following screen and the next commands you need to enter are provided as shown in the screenshot below, copy these commands and enter them

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption><p>Once you enter, you will see a black line on Terminal, no confirmation is provided</p></figcaption></figure>

8. At this point Homebrew is installed and setup, you can verify that the installation by running the following command

```bash
brew --version
```

<figure><img src="../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

9. That's it, you have setup Homebrew! Congrats! Now let's install [Oh My Zsh](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#oh-my-zsh)

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Install Oh My Zsh

1. Copy the command below, paste it in terminal and hit enter

{% code overflow="wrap" %}
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
{% endcode %}

2. Just like that, Oh My Zsh will be installed and your terminal window will have a slightly updated UI

<figure><img src="../.gitbook/assets/Screen Recording 2024-04-16 at 2.31.06 AM (1).gif" alt=""><figcaption></figcaption></figure>

3. Now your terminal has privacy, when you share screenshots for support etc, your name will be less likely to be shared. You can see below, the terminal window went from mentioning the computer and user profile name to simply mentioning `~`
   1.  Before Oh My Zsh\


       <figure><img src="../.gitbook/assets/Before Oh My Zsh.jpg" alt=""><figcaption></figcaption></figure>


   2.  After Oh My Zsh\


       <figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>


4. Congrats on installing Oh My Zsh, now let's get started on [installing Visual Studio Code](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#install-visual-studio-code)

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Install Visual Studio Code

1. Go to [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
2. Click the Mac download link as shown below

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

3. This will download a zip file in your downloads folder. Double click the file to unzip it, this will create a Visual Studio Code app in your downloads folder. Simply move the Visual Studio Code app into the Applications folder as shown below

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

4.  After moving the Visual Studio Code application to Applications folder, double click it to open it from the Applications folder\


    <figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>


5. Click `OK` to proceed if you see a warning as shown below

<figure><img src="../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

6. That's it! You are done with Visual Studio Code for now, feel free to Quit it for now using `cmd+q`
7. Let's move on to installing Rust! :pizza:

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Installing Rust

1. Thanks to Homebrew that we installed earlier, installing rust is as easy as entering the following command in terminal

```bash
brew install rust
```

<figure><img src="../.gitbook/assets/Rust Installation (1).gif" alt=""><figcaption></figcaption></figure>

2. The installation takes a few minutes, the above video is sped up about 20x. Once the installation is complete you will see this window

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

3. That's it! You've installed Rust! :pizza: Now let's move to the next step, [Install Transmission](install-required-tools-homebrew-oh-my-zsh-visual-studio-rust-transmission.md#install-transmission)

<figure><img src="../.gitbook/assets/pizza.gif" alt=""><figcaption></figcaption></figure>

## Install Transmission

1. Go to [https://transmissionbt.com/download](https://transmissionbt.com/download)
2. Download Transmission, we will use this to download a pre-built Ord index to save time

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. A Transmission dmg file will be added to your downloads folder

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4.  This will open a pop up window. You need to take a few steps here as shown in the image below\


    <figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>


5. Woohoo! You've got Transmission setup too! That's it for now, you will use Transmission while setting up the Ord Client. Next step is to [setup the Ord Client](setup-ord-client-on-mac.md).

## X account follow and shoutout

If the guide helped you, please consider [following me on X](https://twitter.com/tahaabbasi) [(@tahaabbasi](https://twitter.com/tahaabbasi)) and giving a shoutout to the mac guide created here. Maybe give a :pizza:in the Ninja Discord using `/pizza user:@officialtahaabbasi reason: anything you'd like to add here`. Thanks for your support!
