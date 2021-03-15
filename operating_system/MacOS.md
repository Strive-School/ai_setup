# Setup instructions
The following instructions will help you to get ready for Strive School 6 intense months!

- Grab a decent text editor- Install a package manager
- Pimp your Terminal
- Setup git and GitHub
- Install Anaconda
- Install Jupyter Notebook
- Pick an IDE

You are here because you invested in an (expensive) awesome computer. Let's get it AI ready!

## Command Line Tools
First, you must have xcode. Here is an article explaining [why](https://www.quora.com/What-is-Xcode-and-why-do-I-need-it)

```bash
xcode-select --install
```

## Sublime Text 3
Sublime is a text editor. You will later use an IDE most likely, but this is still super nice to open any type of files at glance. 

[Download](http://www.sublimetext.com/3) and install it. Package Control / Config is now automatic at step "Dotfiles" below.

## Homebrew
Homebrew is a package manager that makes your life easier. Basically, when you install a package it may have certain dependancies, homebrew makes sure to download them as well so that you [don't have any problems](https://www.quora.com/What-is-Homebrew-for-macOS#:~:text=Homebrew%20is%20a%20package%20manager%20for%20OS%20X.,to%20do%20one%20thing%20well.&text=Homebrew%20is%20an%20app%20for,(on%20the%20command%20line).)
```bash
sudo rm -rf /usr/local/Homebrew
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
sudo chown -R $(whoami) $(brew --prefix)/*
brew update
function install_or_upgrade { brew ls | grep $1 > /dev/null; if (($? == 0)); then brew upgrade $1; else brew install $1; fi }
install_or_upgrade "git"
install_or_upgrade "wget"
install_or_upgrade "imagemagick"
install_or_upgrade "jq"
install_or_upgrade "openssl"
```

## Oh-my-zsh

Oh My Zsh is an open source, community-driven framework for managing your Zsh configuration.

Sounds boring. Let's try again.

Oh My Zsh will not make you a 10x developer...but you may feel like one! 

Basically, it will make your **terminal useful** and look nice, which will make you want to code more with it!


```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

(`⌘` + `Q`) your terminal and restart it.

## GitHub

Github is the place where all developers upload their code. Kind of like a Dropbox of code. But it does much more than that. For the moment. Just installing it should be enough. 

First, sign up for github if you don't have an account already. [Sign UP](https://github.com) 

Then, you can download and install [Github Desktop](https://desktop.github.com/).

There are two ways in which you talk to Github in the web from your computer:
- Using an application such as github desktop
- Directly from the terminal

We will let you pick which you prefer the most during the course. For today, we will make sure that you have both options ready. 

### Since you have Hombrew:

Open your terminal and install Git using Homebrew:

```$ brew install git```
Verify the installation was successful by typing `which git --version`:

```$ git --version git version 2.9.2```

You have git connected to github (the website). You can verify that by typing in the terminal:
```git```
or
```git help -a```

The thing is... how does github know who we are? What if we want to work in a **super secret project**?
![alt text](https://i.imgur.com/fpHasnV.jpeg)

We can configure your Git username and email using the following commands, replacing Elon's name with your own. 
These details will be associated with any commits that you create:

```$ git config --global user.name "Elon Musk"```
```$ git config --global user.email "elon@tesla.com"```

Now, github is connected with your account, you can verify that by typing:
```git config --list```, which will list the settings. There you should also find `user.name` and `user.email`.

Since a hacker could steal your computer, there are two protocols of communicating with Github:
- HTTPS, from when you log in from a Cybercafe
- SSH, when you log in from the safety of your home

HTTPS is the one applied by default. Basically, every time you try to upload something, it will ask you for the email and password, even if it knows who you are. 
SSH is similar to when you wanna always be **logged in to your email**. You create a key that tells github that this computer is always safe. 

Here is an article explaining the differences [1](https://git-scm.com/book/en/v2/Git-on-the-Server-The-Protocols) [2](https://serverfault.com/questions/832899/difference-between-https-git-clone-and-ssh-git-clone)

Here is how we can generate a new SSH key:

```bash
mkdir -p ~/.ssh && ssh-keygen -t ed25519 -o -a 100 -f ~/.ssh/id_ed25519 -C "TYPE_YOUR_EMAIL@HERE.com"
cat ~/.ssh/id_ed25519.pub
```

Copy-paste the public SSH key which we outputed with the last command and [add it to GitHub](https://github.com/settings/ssh).

## Discord

[Install Discord](https://discord.com/download).

-Make sure you upload a picture of you and have your name + last name visible in the chat.
-You can also sign in to Discord on your iPhone or Android device!
-The idea is that you'll have Discord open all day, so that you can share useful links / ask for help / decide where to go to lunch / etc.


## Install Anaconda and Jupyter notebook
[Follow this tutorial](https://www.datacamp.com/community/tutorials/installing-anaconda-mac-os-x)

## Launching your first Jupyter Notebook instance
[Follow this tutorial done by Christian, City leader of Guayaquil]()

## Something missing?
Open an issue or add your own contribution!!
Let's go Strive :)
