# Setup instructions

The following instructions will help you to get ready for [Akademy.ai](http://www.akademy.ai) 10 intense weeks!
- Grab a decent text editor- Install a package manager
- Pimp your Terminal
- Setup git and GitHub
- Install Anaconda
- Install Jupyter Notebooks


## GitHub account

Have you signed up to GitHub? If not, [do it right away](https://github.com/join).

:point_right: **[Upload a picture](https://github.com/settings/profile)** and put your name correctly on your GitHub account. This is important for several reasons 1) employability and 2)in case we use an internal dashboard with your avatars. Please do it **now**.


## Git

To install `git`, first open a terminal. To open a terminal, you can click on the Ubuntu Start button in the sidebar and type `Terminal`. Then click on the terminal icon.

Then copy this line with `Ctrl` + `C`:

```bash
sudo apt install -y git
```

:bulb: To **paste it in the terminal**, you need to use `Ctrl` + `Shift` + `V`.


## Sublime Text 3 - Your text editor

A text editor is one of the most important tools of a developer. This doesn't necessarly have to be yours, since you can pick between this, and IDE and something on the web like Jupyter notebooks. Nevertheless, great asset to have installed just in case. u
Follow these instructions in the Terminal:

```bash
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```

:point_up: This command will ask for your password with: `[sudo] password for <username>:`. Don't panick! Calmy type your password key by key. You won't have a visual feedback (like little `*`), that's **perfectly normal**, keep on typing. When you're done, hit `Enter` :muscle:.

```bash
sudo apt install -y apt-transport-https
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt update
sudo apt install -y sublime-text
```

Sublime Text is free without any time limitation but a popup will appear every ten saves to remind you there is a license to buy. You can hit `Esc` when this happens, but feel free to buy Sublime Text if you really like this one (there are alternatives).


## Oh-my-zsh - Fancy your Terminal

We will use the shell named `zsh` instead of `bash`, the default one.

```bash
sudo apt install -y zsh curl vim nodejs imagemagick jq
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
# it will ask for your session password
```

Be careful, those commands will ask you to type your password twice. At the end
your prompt should look like this:

![](images/ubuntu_oh_my_zsh.png)

If it doesn't, **ask a facilitator or search the error online!**.

To make this change stick, restart your laptop (or virtual machine):

```bash
sudo reboot
```

Once the installation is done, you can verify the Zsh version by running the following command;

```zsh --version
zsh 5.4.2 (x86_64-ubuntu-linux-gnu)
```

## Configure Zsh

Now that Zsh in installed, make it your default shell by running the command below;

```
chsh -s $(which zsh)
```
This will the default shell for the current user. If run sudo `chsh -s $(which zsh)` it will change the default shell for root.
If this doesn't work, **let us know** and we will come sort it out manually :)

### Syntax Highlighting
You want Zsh syntax highlighting. It will tell you if your command is valid even before you run it. It’s handy.

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
If `git` is not installed, download and extract a snapshot of the latest development tree from:
```
https://github.com/zsh-users/zsh-syntax-highlighting/archive/master.tar.gz
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

### Sublime text

By adding sublime to the plugin list, you will be able to launch it with a simple `stt` command in the terminal

## GitHub

We need to generate SSH keys which are going to be used by GitHub and Heroku
to authenticate you. Think of it as a way to log in, but different from the
well known username/password couple. If you already generated keys
that you already use with other services, you can skip this step.

Open a terminal and type this, replacing the email with **yours** (the
same one you used to create your GitHub account). It will prompt
for information. Just press enter until it asks for a **passphrase**.

```bash
mkdir -p ~/.ssh && ssh-keygen -t ed25519 -o -a 100 -f ~/.ssh/id_ed25519 -C "TYPE_YOUR_EMAIL@HERE.com"
```

**NB:** when asked for a passphrase, put something you want (and that you'll remember),
it's a password to protect your private key stored on your hard drive. You'll type,
nothing will show up on the screen, **that's normal**. Just type the passphrase,
and when you're done, press `Enter`.

Then you need to give your **public** key to GitHub. Run:

```bash
cat ~/.ssh/id_ed25519.pub
```

It will prompt on the screen the content of the `id_ed25519.pub` file. Copy that text,
then go to [github.com/settings/ssh](https://github.com/settings/ssh). Click on
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

If it does not work, try running this before trying again the `ssh -T` command:

```bash
ssh-add ~/.ssh/id_ed25519
```

Don't be in a rush, take time to [read this article](https://developer.github.com/v3/guides/managing-deploy-keys/) to get a better understanding of what those keys are used for or follow [this tutorial](https://help.github.com/en/articles/connecting-to-github-with-ssh) for a more detailed step-by-step guide. 


## Slack

[Install Slack for Linux (beta)](https://get.slack.help/hc/en-us/articles/212924728-Slack-for-Linux-beta-).

Launch the app and sign in to `akademyai.slack.com` organization.

Make sure you upload a picture there as well.

You can also sign in to Slack on your iPhone or Android device!

The idea is that you'll have Slack open all day, so that you can share useful links / ask for help / decide where to go to lunch / etc.

## Installing Anaconda and Jupyter Notebook
[Follow this tutorial done by Christian, City leader of Guayaquil](https://medium.com/@christian_tutiven/empezando-a-usar-jupyter-notebook-para-python-parte-1-instalaci%C3%B3n-94e97b4c5f37)

## Option A: Setup Google Collab
[Follow this tutorial done by Christian, City leader of Guayaquil](https://medium.com/@christian_tutiven/empezando-a-usar-google-colab-con-pytorch-4efb53933624?sk=4e97d2efe9ca54ce705bc081d19f6e14)

## Option B: Setup Google Cloud (300€ free credits) linked to the fast.ai library
[Follow this tutorial](https://medium.com/@howkhang/ultimate-guide-to-setting-up-a-google-cloud-machine-for-fast-ai-version-2-f374208be43)

## Something missing?
Open an issue or add your own contribution!!

Enjoy your ride with Ai Saturdays :)
