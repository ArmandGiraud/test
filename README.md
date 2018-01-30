# Jupyter Doc

:link: [The official site](http://jupyter.org/)

:green_book: [Read the Doc](http://jupyter-notebook.readthedocs.io/en/stable/)

Table of contents: 
 - [Installation](#installation)
    1. locally
    2. On remote machine
 - [Tip & tricks](#tip--tricks)
    - [Adding a new kernel](#adding-a-new-kernel)
    - Adding a new language
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

### Tip & Tricks

#### Adding a new kernel
You can directly refer to [the Docs](http://jupyter.readthedocs.io/en/latest/install-kernel.html) for more infos
The default kernel for Jupyter is [Ipython](https://ipython.readthedocs.io/en/latest/) but some custom kernels can be added:

The recommended way is to make a conda virtual env and install ipykernel inside

```bash
conda create -n ipykernel_py2 python=2 ipykernel
source activate ipykernel_py2    # On Windows, remove the word 'source'
python -m ipykernel install --user
```


    - Adding a new language
    - Jupyter and spark
    - Magic functions
    - Iwidgets
