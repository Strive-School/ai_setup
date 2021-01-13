You are here because you invested in an (expensive) awesome computer. Let's get it AI ready!

## Command Line Tools

```bash
xcode-select --install
```

### Warning
**Do not pip install!**. 
Unless you really need to, but then be aware that conflicts may arise.
## Sublime Text 3

[Download](http://www.sublimetext.com/3) and install it. Package Control / Config is now automatic at step "Dotfiles" below.

## Homebrew

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

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

(`⌘` + `Q`) your terminal and restart it.

## GitHub

You have a new computer, let's generate a new SSH key:

```bash
mkdir -p ~/.ssh && ssh-keygen -t ed25519 -o -a 100 -f ~/.ssh/id_ed25519 -C "TYPE_YOUR_EMAIL@HERE.com"
cat ~/.ssh/id_ed25519.pub
```

Copy-paste the public SSH key which we outputed with the last command and [add it to GitHub](https://github.com/settings/ssh).

## Discord

[Install Discord](https://discord.com/download).



Make sure you upload a picture there.

You can also sign in to Discord on your iPhone or Android device!

The idea is that you'll have Discord open all day, so that you can share useful links / ask for help / decide where to go to lunch / etc.



## Install Anaconda and Jupyter notebook
[Follow this tutorial](https://www.datacamp.com/community/tutorials/installing-anaconda-mac-os-x)

## Launching your first Jupyter Notebook instance
[Follow this tutorial done by Christian, City leader of Guayaquil]()

## Option A: Setup Google Collab
[Follow this tutorial done by Christian, City leader of Guayaquil]()

## Something missing?
Open an issue or add your own contribution!!
Let's go Strive :)
