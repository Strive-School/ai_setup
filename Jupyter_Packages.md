## (Optional) Recommended Jupyter Packages
Our recommended packages for the course are:
- **nbextesions**:
nbextensions is a plugin manager that allows you to enable and disable extensions with just a few clicks, thereby eliminating the need for executing commands for activating and deactivating add-ons. Apart from managing the extension, nbextensions comes with a wide range of plugins, which are added while installing nbextensions. 

Run the below command from the anaconda terminal to install the nbextensions: –

`conda install -c conda-forge jupyter_contrib_nbextensions` 

if this doesn't work you can also try to do the following from the Anaconda command prompt: 

```
conda install -c conda-forge jupyter_contrib_nbextensions 
conda install -c conda-forge jupyter_nbextensions_configurator
jupyter contrib nbextension install --user
```

- **Hinterland**

Open the nbextensions and search and enable Hinterland. This extension helps in autocompleting the code. Without this, you would require to press tab and check for the available options for **code completion**. However, Hinterland enables the autosuggestion as you type. You can also configure the behaviour of the extension such as hint delay, hint inside comments, and more. The parameters can be changed from the nbextensions menu.

- **Execute Time**

This extension is a part of the nbextensions and can be activated to get insights into the time your cell took to run. Besides, it shows the date the cell was last executed. As a data science practitioner, it is essential to optimise the code to run faster & check if you are caught in an endless loop. Since this extension provides you with the time your code takes to execute, you can optimise the code depending on the requirements. Although the execution time of a cell can be checked with magic commands, this extension will by default show the time and save you a few keystrokes as you won’t require to add the magic command every time.  

- **Jupyter Themes**


Jupyter theme extension allows you to beautify not only the plain white background of your Jupyter Notebook but also the fonts of text and size of cells. In addition, you can plot appealing visualisations using the style() method. Jupyter themes extension doesn’t come with nbextensions, and you need to install them using the below command: –

`conda install -c conda-forge jupyterthemes`
