# ![alt text](https://github.com/ArmandGiraud/test/blob/master/img/jupyter.svg) Jupyter Doc



:link: [The official site](http://jupyter.org/)

:green_book: [Read the Doc](http://jupyter-notebook.readthedocs.io/en/stable/)

Table of contents: 
 - [Installation](#installation)
    1. locally
    2. On remote machine
 - [Configuration](#configuration)
 - [Tip & tricks](#tip--tricks)
    - [Adding a new kernel](#adding-a-new-kernel)
    - [Adding a new language](#adding-a-new-programming-language)
    - [Magic functions](#magic-functions)
    - Iwidgets
    
 
 ---
 
 ### Installation:
 
 **1. Locally:**
 
 - The Jupyter notebook is shipped in a [conda installation](https://www.anaconda.com/download/)
 - It can alternatively be installed via pip:
 ```bash pip3 install --upgrade pip```
 
 ```pip3 install jupyter```
 
 :runner: Just launch ``` jupyter notebook``` from a shell and the notebook listens by default on ```localhost:8888```
 
 **2. On remote machine:**
 
- Use the [JupyterHub](https://github.com/jupyterhub/jupyterhub) on Production environment:

... TO DO ..

On a remote machine run ```jupyter notebook --no-browser --ip your.server.ip --port your.local.port```
and jupyter should be available at your.server.ip:your.local.port on any browser. (on production might use some tunneling)



---
### Configuration:

The notebook server can be run with a [variety of command line arguments](http://jupyter-notebook.readthedocs.io/en/stable/config.html#options).
```$ jupyter notebook --help``` to get the list of possible options.

The configuration file enables to control the behaviour of jupyter, for example adding a password to proctect your jupyter session.
```$ jupyter notebook --generate-config```
command creates a default config file. 

---
### Tip & Tricks
#### Basic Tutorial

To explore the basic Jupyter notebook (Execution & shortcuts) many tutorials are available on the web.

Visit the [jupyter UI tour](http://jupyter-notebook.readthedocs.io/en/stable/ui_components.html#).

###### The Jupyter enables basic 3 modes for cells: 
 - Code (default): wtrite python code in cell then press ```Ctrl + enter``` to execute, you should see the output below.
 - Markdown ```Esc + M``` to convert the cell type in [markdown](http://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Working%20With%20Markdown%20Cells.html). you can also add directly html code in cells this is useful if you want to customize the cells like adding images and formatting cells.
 - Raw cells
 
 :+1: A few useful shortcuts are (beware some of them are os dependant):
  -```Ctrl + shift +P``` open the command palette.
  - ***displays all shortcuts:***  press ```H``` while in command mode (cell is selected in blue).
  - ***merge several cells*** select them (command mode) and press M
  
 

#### Adding a new kernel
![alt text](https://github.com/ArmandGiraud/test/blob/master/img/change_kernel.PNG)

You can directly refer to [the Docs](https://ipython.readthedocs.io/en/latest/install/kernel_install.html) for more infos
The default kernel for Jupyter is [Ipython](https://ipython.readthedocs.io/en/latest/) but some custom kernels can be added:

The recommended way is to make a conda virtual env and install [ipykernel](https://github.com/ipython/ipykernel) inside

```bash
conda create -n ipykernel_py2 python=2 ipykernel
source activate ipykernel_py2    # On Windows, remove the word 'source'
python -m ipykernel install --user
```
You can make a kernel for any of your venv... 

#### Adding a new programming language
To add a programming language on jupyter you will can also install a new kernel 
Originally Jupyter was intended to support **Ju**lia **Pyt**hon and **R** (Jupyter), now the [list of available kernels](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels) is much longer including for example [**Scala**](https://github.com/jupyter-scala/jupyter-scala#quick-start),  [**Lua**](https://github.com/pakozm/IPyLua) and [**C#**](https://github.com/zabirauf/icsharp)

:flashlight: [Irkernel](https://irkernel.github.io/installation/) For linking R with your Jupyter:

In a R console (preferably in R console launched from a terminal):
```R
install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))
devtools::install_github('IRkernel/IRkernel')
IRkernel::installspec()
```
**This should add a Display Name to the dropdown menu:**
![alt text](https://github.com/ArmandGiraud/test/blob/master/img/ipy4_demo.png)


#### Magic functions
   The Ipython notebook is an enhanced version of python where you can do much more.
   The best way to know all its features is to explore the [Official CookBook](https://github.com/ipython/ipython/wiki/Cookbook%3A- Index) or the [Ipython.org Tip & Tricks](https://ipython.org/ipython-doc/3/interactive/tips.html#tips).
   
:bulb:  Any line starting with a '%' will be interpreted by Ipython as a special magic function, they allow you to control the behaviour of Ipython itself.
These functions are very useful, the most popular are:

* Tab Completion
Press Tab after the name of a variable, function or class, to display the different options..
You can also navigate through your system files just by adding a string..
![alt text](https://github.com/ArmandGiraud/test/blob/master/img/tab_completion.png)

* inline documentation:

```python
str.join?
```
The syntax ```function?``` will display an inline documentation popup for the function or class you are using, this allows to rapidly know the function/class parameters.

* Unix/powershell command
```python
In [1]: !ls -la
In [2]: !pip install nltk
```

* Run
```python
In [1]: %run foo.py
```
to run an external file without importing.

* load_ext
```python 
In [1]: %load_ext autoreload
In [2]: %autoreload 2
```
%load_ext enables to load an extension
and %autoreload 2 reload all module before execution
This enables to modify the script of an imported python file/module.

* Time
```python
In [1]: %%time
```

Which enable to record the Running time of a single cell.
![alt text](https://github.com/ArmandGiraud/test/blob/master/img/time.PNG)
Which enables to run a unix command directly in the Notbook

* matplotlib inline
```python
In [1]: %%matplotlib inline
```
The output of plotting commands is displayed inline, which means having embeeded plots and visualisations

* lateX

```python
In [1]: %%latex
```
The latex magic enables to have equation in cells without having to write the ```$$``` wrapper for each line


   - [Ipywidgets](https://ipywidgets.readthedocs.io/en/stable)
   
   The ipywidgets are a series of embedded ipywidgets, very useful for demo purposes. 
   ![alt text](https://github.com/ArmandGiraud/test/blob/master/img/interact.PNG)
   
   - Jupyter and Spark
