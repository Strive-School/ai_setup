### For Mac

## Setup Terminal for Sublime Shorcut "subl":

**Open terminal and type:**

**1. Create a directory at ~/bin:**

```mkdir ~/bin```

**2. Copy sublime executable to your ~/bin directory:**

```ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl```

### BASH (Mac OS default) - use these instructions unless you know you have zsh

**3a. If using bash (Mac OS default) add line to ~/.bash_profile file:**

```echo 'export PATH=$PATH:$HOME/bin' >> ~/.bash_profile```

**4a. Set sublime as your default editor**

```echo "export EDITOR='subl -w'" >> ~/.bash_profile```

or

### ZSH - if you don't know what zsh is you don't have it

**3b. If using zsh add line to ~/.zshrc file:**

```echo 'export PATH=$PATH:$HOME/bin' >> ~/.zshrc```

**4b. Set sublime as your default editor**

```echo "export EDITOR='subl -w'" >> ~/.zshrc```

**5. Restart terminal and type:**

```subl .```

Sublime should open up in the current directory.

**6. Check unix commands:**

```ls ```

You should get a directory listing.

-----

### Windows

Put the ```C:\Program Files\Sublime Text 2``` in your PATH.

Create a ```subl.bat``` file and save it in the directory: ```C:\Program Files\Sublime Text 2```

Inside the file put: ```start sublime_text.exe %*```
