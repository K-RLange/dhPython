---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
<div style="float: right;">
  <a href="../de/installation.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/installation.html">🇬🇧 English</a>
</div>

# 0. Installing Python, an IDE and packages
## Installing Python
To install Python on your local machine, you can either download the installer
from the official website or install conda, which is a version manager for
Python and other programming languages (like R).

To complete this tutorial, you will **not** need to install Python or an Integrated Development Engine (IDE, basically a graphical interface), as the code can be run in your browser.
If you would like to work with Python after completing this course however, we suggest you install Python and an IDE on your local machine.
### 1) Using conda (recommended)
To download conda, please visit the [official conda website](https://conda.io/projects/conda/en/latest/user-guide/install/index.html).
You can choose to either install miniconda or Anaconda distribution (recommended). Miniconda is a barebone installation, while Anaconda distribution provides additional pre-installed features, which might be useful for you.
Follow the download instructions on the website and install the version of conda that you prefer.

After conda is installed, you can, at any time, create a new programming environment for Python. Thus, if you have different projects that require different Python versions of packages, you can simply use conda to create a new environment. This is recommended to avoid conflicts between different packages and their versions.

You can call conda from your terminal by entering 
```bash
conda
```
If it is correctly installed, it should respond with a list of possible commands. If you get an error and you are using Windows, you might need to run the command 
```bash
activate
```
or 
```bash
conda activate
```
first. 


To create a Python environment, open a terminal and run the following command in your terminal:

```bash
conda create --name myenv python=3.11
```
In this case, we create a new environment called `myenv` with Python version 3.11. You can choose any name for your environment and any Python version that you need. The latest Python version, as of writing this tutorial, is Python 3.11.

Within the terminal, you can then type
```bash 
conda activate myenv
```
to activate your environment. You can then install any packages that you need for your project.

### 2) Using the official installer
To install Python using the official installer, please visit the [official Python website](https://www.python.org/downloads/) and install the version that you would like to use.
Please note that it is recommended to use the conda installer, because this will make it easier for you to manage different Python versions and packages later on.

## Installing packages
Python has two major package managers: conda and pip. Conda is the package manager that comes with the Anaconda distribution, while pip is the package manager that comes with every Python installation by default.

Please note that these two package managers are not always compatible with each other. If you are using conda, it is recommended to install packages using conda. If you need to use both managers for the same Python environment, please make sure to first install as many packages as possible using conda and then install the rest using pip.

For the most purposes, pip should suffice.
### 1) Using pip
To install a package using pip, you can simply open a terminal and type
```bash
pip install package_name
```
where `package_name` is the name of the package that you would like to install. For example, to install the package `numpy`, you can type
```bash
pip install numpy
```
### 2) Using conda
To install a package using conda, you can simply open a terminal and type
```bash
conda install package_name
```
where `package_name` is the name of the package that you would like to install. For example, to install the package `numpy`, you can type
```bash
conda install numpy
```

## Installing an IDE
An IDE (Integrated Development Environment) is a software that provides you with a graphical user interface to write and run your code. There are many different IDEs available for Python, but we recommend using either Jupyter Notebook or PyCharm. 
These can be installed manually or with the help of Anaconda Navigator, which comes with the installation of Anaconda distribution (not with miniconda though). To install them via Anaconda Navigator, just open said Navigator and as soon as it has started, you should see a list of programs that it supports. When you are at that screen, you can simply choose which IDE to install. 
If you are not using Anaconda Navigator, you can follow these steps:

### 1) Jupyter Notebook
Jupyter Notebook is designed to work with interactive Jupyter Notebooks. It is organized in individual code blocks, which can be executed one at a time.
This is often used for teaching or demonstration purposes. E.g. this project is organized using Jupyter notebook-esque code blocks.
The downside of this IDE is that it is not very well suited for larger projects, as it is not designed to work with multiple files. For larger projects, we recommend using PyCharm.

The installation of Jupyter Notebook is included in the Anaconda distribution, so if you have installed Anaconda, you can simply open a terminal and type
```bash
jupyter notebook
```
to start the Jupyter Notebook server.

### 2) PyCharm
PyCharm is a professional IDE, which is designed to work with larger projects. It follows a similar design pattern like the IDEs of other languages, such as R's RStudio. It provides you with a graphical user interface to write and run your code, and it is very well suited for working with multiple files and projects.
It has an integrated debugger, which allows you to easily find and fix errors in your code. It also directly integrates conda into the IDE - you will not have to use the terminal to create new python environments, but can do it whenever you create a new project via the graphic interface.
It is however not as beginner friendly, as it provides many expert features, which might be overwhelming for beginners.

To install PyCharm, please visit the [official PyCharm website](https://www.jetbrains.com/pycharm/download/) and download the version that you would like to use. You can choose between the free community edition and the professional edition.
When logging into the jetbrains-website and linking it to your university account, you can use the professional edition for free.

For a tutorial, on how to use PyCharm, please visit the [official PyCharm tutorial](https://www.jetbrains.com/help/pycharm/quick-start-guide.html).