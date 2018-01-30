# ![alt text](http://jupyter.org/assets/main-logo.svg) Jupyter Doc



:link: [The official site](http://jupyter.org/)

:green_book: [Read the Doc](http://jupyter-notebook.readthedocs.io/en/stable/)

Table of contents: 
 - [Installation](#installation)
    1. locally
    2. On remote machine
 - [Tip & tricks](#tip--tricks)
    - [Adding a new kernel](#adding-a-new-kernel)
    - [Adding a new language](#adding-a-new-programming-language)
    - Jupyter and spark
    - Magic functions
    - Iwidgets
    
 
 ---
 
 ### Installation:
 
 **1. Locally:**
 
 - The Jupyter notebook is shipped in a [conda installation](https://www.anaconda.com/download/)
 - It can alternatively be installed via pip:
 ```bash pip3 install --upgrade pip```
 
 ```pip3 install jupyter```
 
 **2. On remote machine:**
 
- Use the [JupyterHub](https://github.com/jupyterhub/jupyterhub) on Production environment:

... TO DO ..

---
### Tip & Tricks

#### Adding a new kernel
![alt text](https://i.stack.imgur.com/RGnZT.png)
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
This should add a Display Name to the dropdown menu:
   - Jupyter and spark
   - Magic functions
   - Iwidgets
   
