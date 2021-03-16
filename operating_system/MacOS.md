# Setup instructions
The following instructions will help you to get ready for Strive School 6 intense months!

- Install a package manager
- Pimp your Terminal
- Grab a decent text editor
- Setup git and GitHub
- Install Anaconda
- Install Jupyter Notebook
- Pick an IDE

You are here because you invested in an (expensive) awesome computer. Let's get it AI ready!

## GitHub account

Have you signed up to GitHub? If not, [do it right away](https://github.com/join).

:point_right: **[Upload a picture](https://github.com/settings/profile)** and put your name correctly on your GitHub account. This is important for several reasons: 
- employability
- in case we use an internal dashboard with your avatars. --> WE DO!

Please do it **now**.

## Launching your terminal
All the code snippets you see in this tutorial are meant to be launched from your Terminal. 
![image](https://user-images.githubusercontent.com/22689750/111239088-59ca2f80-85f0-11eb-8fde-14fa56f55262.png)

One important notion to learn is what type for terminal you have: 
- By default, Ubuntu and Mac have are based on bash, which allows for [quite complex scripts](https://devhints.io/bash). We will actually prompt you to use zsh, a more new and neat terminal language. Here is a [cheat sheet](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet)   
- The main difference is that ubuntu allows unrestricted acceess to many folders (open source). [Ubuntu terminal commands](https://techlog360.com/basic-ubuntu-commands-terminal-shortcuts-linux-beginner/)
- On contrast, mac is more restricted on the types of things it lets its users do.
- Windows is in between and actually it uses a slightly different [terminal language](https://www.makeuseof.com/tag/mac-terminal-commands-cheat-sheet/).

Make sure your terminal is nearby, and get ready to type some code!

## Command Line Tools
First, you must have xcode. Here is an article explaining [why](https://www.quora.com/What-is-Xcode-and-why-do-I-need-it)

Open your terminal. Then copy this line with `⌘` + `C`:

```bash
xcode-select --install
```
:bulb: To **paste it in the terminal**, you need to use `⌘` + `Shift` + `V`.

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
## The power of homebrew

One quick way to test how good is homebrew. We don't have to use the default terminal provided by Apple. 
We can install a neat alternative to it called [iterm2](https://iterm2.com/features.html). 

``` 
brew cask install iterm2
```

If you decide to keep using this after the installation after your main terminal, the only difference will be which terminal program you launch and the interface. 

## Install ZSH
> Zsh is a shell designed for interactive use, although it is also a powerful **scripting language**.

By default, macOs ships with zsh located in `/bin/zsh`.

Let’s install zsh using brew and make iTerm2 or terminal _-whatever your prefer-_ use it.

```
brew install zsh
```

## Installing Oh-my-zsh

Oh My Zsh is an open source, community-driven framework based on the [ZSH](https://www.zsh.org/) script language.

Sounds boring. Let's try again:

Oh My Zsh will not make you a 10x developer...but you **may feel like one**! 

Basically, it will make your **terminal useful** and **look nice**, which will make you want to code more with it!

It runs on Zsh to provide cool features configurable within the ~/.zhrc config file. Install [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh) by running the command

```bash 
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
if you are already on bash, the following might also work

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
Now, we can check the version we have just installed

```
zsh --version
```
You can keep up to date by downloading the latest version with the new features they added.

```
upgrade_oh_my_zsh
```

Press (`⌘` + `Q`) to close your terminal/iTerm2 and restart it.

## Personalizing Oh-My-Zsh
Time to make your terminal look super neat and make it helpful towards your coding journey. For this, we will add a series of packages to Oh-My-Zsh

### Syntax Highlighting
You want Zsh syntax highlighting. It will tell you **if your command is valid even before you run it**. It’s handy.

To enable syntax highlighting, run
```
cd ~/.oh-my-zsh 
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
```
and then enable it by running
```
source ~/.oh-my-zsh/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```
Restart your terminal for your changes to take effect.

### Add ZSH-AutoSuggestion Plugin

This plugin auto suggests any of the previous commands. Pretty handy! **To select the completion, simply press → key.**

1.     Install the plugin
`git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions`

2. Open `~/.zshrc` and add `zsh-autosuggestions` in the plugins section

3. and then enable it by running
```
source ~/.zshrc
```

Restart your terminal for your changes to take effect.

### Sublime Text 3
Sublime is a text editor. You will later use an IDE most likely, but this is still super nice to open any type of files at glance. 

-[Download](http://www.sublimetext.com/3) and install it. Package Control / Config is now automatic at step "Dotfiles" below.
-You want to be able to launch sublime from your terminal with a simple `subl`, follow this [tutorial](https://github.com/Strive-School/ai_setup/blob/master/sublime_terminal.md)
- However, since we have oh-my zsh, we can just also just add it to the plugin list, run `source ~/.zshrc` and launch it with another simple command `stt`.

### BONUS: Customize your Terminal Theme
Many options and settings to [choose from!](https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/)

You can check how they look like [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

### BONUS: Look and install other useful packages
-This is a list of [all the oh-my-zsh plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins)
-It is probably worth checking the [most useful one's only :)](https://safjan.com/top-popular-zsh-plugins-on-github/)

Am example of interesting plugins one could have in the `~/.zshrc` config file. If you want to modify it directly, you can also use sublime for it (if you have the package installed) `subl ~/.zshrc` --> edit the text, save, close and then enable it by running `source ~/.zshrc`

```
# Useful oh-my-zsh plugins
plugins=(git gitfast last-working-dir common-aliases sublime zsh-syntax-highlighting history-substring-search zsh-autosuggestions git-flow-completion)
```

## GitHub

Github is the place where all developers upload their code. Kind of like a Dropbox of code. But it does much more than that. For the moment. Just installing it should be enough. 

First, sign up for github if you don't have an account already (2nd warning!). [Sign UP](https://github.com) 

Then, you can download and install [Github Desktop](https://desktop.github.com/).

There are two ways in which you talk to Github in the web from your computer:
- Using an application such as github desktop
- Directly from the terminal

We will let you pick which you prefer the most during the course. For today, we will make sure that you have both options ready. 

### Since you have Hombrew:

Open your terminal and install Git* using Homebrew:
* more on the differences between _git_ and _github_ on Friday

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

Copy-paste the public SSH key which we outputed with the last command and [add it to GitHub](https://github.com/settings/ssh). Click on
**Add SSH key**, fill in the Title with your computer name, and paste the **Key**.
Finish by clicking on the **Add key** green button.

To check that this step is completed, in the terminal run this. **You will be
prompted a warning**, type `yes` then `Enter`.

```bash
ssh -T git@github.com
```

If you see something like this, you're done!

```bash
# Hi --------! You've successfully authenticated, but GitHub does not provide shell access
```

## Discord

[Install Discord](https://discord.com/download).

-Make sure you upload a picture of you and have your name + last name visible in the chat.
-You can also sign in to Discord on your iPhone or Android device!
-The idea is that you'll have Discord open all day, so that you can share useful links / ask for help / decide where to go to lunch / etc.


## Install Anaconda and Jupyter notebook
[Follow this tutorial](https://www.datacamp.com/community/tutorials/installing-anaconda-mac-os-x)

## Install Jupyter Notebook Extensions

Open a terminal with anaconda using your custom environment and run
`conda install -c conda-forge jupyter_nbextensions_configurator`.

Then enables it by running `jupyter nbextensions_configurator enable --user` in the same terminal.

Open a jupyter notebook and you should see the following:
![image](https://github.com/Jupyter-contrib/jupyter_nbextensions_configurator/raw/master/src/jupyter_nbextensions_configurator/static/nbextensions_configurator/tree_tab/icon.png) that is another tab beyond Files, Running and Clusters named Nbextensions. Click on it, then uncheck "disable configuration for extensions without explicit..." and choose the ones you prefer.

[Here](https://www.loom.com/share/285ec5ee08f04b0cbab05f3ea519acef) a quick loom on how to enable some of the available extensions.


## Something missing?
Open an issue or add your own contribution!!

**Time to Strive :)**

