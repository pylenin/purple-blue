---
title: "Getting Started with Jupyter Notebook for Python"
description: "This article helps in installing Jupyter Notebook and exploring its various functionalities for programming in Python."
date: 2019-06-18T13:02:49+02:00
draft: false
image: /img/getting-started-with-jupyter/jupyter-meta-img.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Paritosh Gupta](https://www.pylenin.com/authors/#paritosh-gupta)*

**Jupyter Notebook** is a web application that allows you to create and share documents that contain:

* Live code (e.g. Python code)
* Visualizations
* Explanatory Text (written in markdown syntax)

The [Python Developer Survey](https://www.jetbrains.com/research/python-developers-survey-2018/) by Jetbrains in 2018, showed that Jupyter Notebook is among the top 5 IDEs preferred by programmers, especially for **Machine Learning and Data Analysis**. 

Jupyter Notebook's ability to combine code, visualizations and rich text and the fact that you can share your notebook with the community, makes it suitable for performaing data anlysis in real time and adding a **story telling** aspect to your analysis.

This blog will help you in installing Jupyter Notebook for programming in Python. We’ll explore the basic functionality of Jupyter Notebook.

Let’s get started and install Jupyter Notebook on your computer.

**Sections Covered**

1. [Setting-up Jupyter Notebook](#setting-up-jupyter-notebook)
2. [Managing Python version on the Jupyter Notebook](#managing-python-version-on-the-jupyter-notebook)
3. [Uninstalling old kernels](#uninstalling-old-kernels)
4. [Creating a new jupyter notebook](#creating-a-new-jupyter-notebook)
5. [Working with the Notebook](#working-with-the-notebook)
6. [Edit and Command Mode](#edit-and-command-mode)
7. [Exporting the Notebook](#exporting-the-notebook)

##### Setting-up Jupyter Notebook

The first step to get started is to visit the project’s [website](http://www.jupyter.org).

![Jupyter Homepage](/img/getting-started-with-jupyter/jupyter-homepage.png)

Here you’ll find two options:

* Try it in your browser
* Install the Notebook

In the first option, **Try it in your browser** you can access a hosted version of Jupyter Notebook. This will get you direct access without needing to install it on your computer.

The second option, **Install the Notebook** will take you to another page which gives you detailed instructions for the installation. There are two different ways:

* Installing Jupyter Notebook by using the Python’s package manager `pip`
* Installing Jupyter Notebook by installing the Anaconda distribution

Especially if you’re new to Python and would like to set up your development environment from scratch using the Anaconda distribution is a great choice. If you follow the [link](https://www.anaconda.com/download/) to the Anaconda download page you can choose between installers for Windows, macOS, and Linux.

![Anaconda Homepage](/img/getting-started-with-jupyter/anaconda-homepage.png)

Go for Installers with Python version more than 3. Python 2 is soon going to be deprecated. If you are unaware of the differences between Python 3 and 2, check out this [article](https://www.pylenin.com/blogs/10-benefits-of-switching-to-python-3/).

##### Managing Python version on the Jupyter Notebook

If you already have jupyter installed with a version lower than 3.7 you can create a new kernel with python version by executing the following commands on the conda prompt.

`Start->Anaconda3->Anaconda Prompt`

Once you are in the prompt, execute the following commands.
```bash
$ conda create -n Python_3.7 python=3.7 ipykernel
```
This command will create a new kernel with python version 3.7.

```bash
$ activate Python_3.7
```
This command will activate the new Kernel.

```bash
$ pip install ipykernel
```
Now we’ll install the ipykernel module for our new python version.
```bash
$ python -m ipykernel install –name Python_3.7
```
By using this command we are installing the new kernel into Jupyter.

##### Uninstalling old kernels

To uninstall the old kernel we’ll run these commands in the conda prompt.
```bash
$ jupyter kernelspec list
```
Here you will find all the kernel installed on the jupyter notebook. Find the name of the default kernel (Mostly it is Python 3).

To uninstall the kernel we’ll run this command:
```bash
$ jupyter kernelspec uninstall <unwanted-kernel>
```
##### Creating a new jupyter notebook

Having installed the Anaconda distribution, we can now start Jupyter Notebook by using the following command.

```bash
$ jupyter notebook
```
You’ll see the following response on the command line.

![Jupyter Notebook Starting Up](/img/getting-started-with-jupyter/jupyter-start.png)

The web server is started, and the Jupyter Notebook application is opened in your default browser automatically. You should be able to see a browser output which is similar to the following screenshot.

![Jupyter Notebook Homepage](/img/getting-started-with-jupyter/jupyter-nb-home.png)

As you can see the user interface of Jupyter Notebook is split up into three sections (tabs) -

* Files
* Running
* Clusters

The default view is the *Files* tab from where you can open or create notebooks.

Creating a new Jupyter Notebook is easy. Just use the **New** dropdown menu and you’ll see the following options as below.

![New notebook screenshot](/img/getting-started-with-jupyter/new-nb-screenshot.png)

Select option **Python 3** to open a new Jupyter Notebook for Python. The notebook is created, and you should be able to see something similar to the below screenshot.

![New notebook Home](/img/getting-started-with-jupyter/new-nb-home.png)

The notebook is created but still untitled. By clicking into the text *Untitled* on the top you can give it a name. By giving it a name, the notebook will also be saved as a file of the same name with extension `.ipynb`. E.g. name the notebook `code1`.

![Rename notebook](/img/getting-started-with-jupyter/rename-nb.png)

Switching back to the `Files` tab you’ll be able to see a new file *code1.ipynb*.

![New Notebook in Files](/img/getting-started-with-jupyter/new-nb-in-files.png)

Because this notebook file is opened right now, the file is marked with status **Running**. From here you can decide to shut down this notebook by clicking on the button **Shutdown**.

However, before shutting down the notebook let’s switch back to the notebook view and try out a few things to get familiar with the notebook concept.

##### Working with the Notebook

The notebook itself consists of cells. A first empty cell is already available after having created the new notebook.

![First empty cell in Notebook](/img/getting-started-with-jupyter/first-empty-cell.png)

This cell is of type `Code` and you can start typing in Python code directly. Executing code in this cell can be done by either **clicking on the run** cell button or hitting `Shift + Enter` keys.

![First python code in Notebook](/img/getting-started-with-jupyter/first-code.png)

The resulting output becomes visible right underneath the cell.

##### Edit and Command Mode

If a cell is active, two modes can be distinguished -

* edit mode
* command mode

If you just click in one cell the cell is opened in command mode which is indicated by a **blue border** on the left.

![Notebook Command Mode](/img/getting-started-with-jupyter/notebook-command-mode.png)

The edit mode is entered if you click **into the code area** of that cell. This mode is indicated by a green border on the left side of the cell.

![Notebook Edit Mode](/img/getting-started-with-jupyter/notebook-edit-mode.png)

If you’d like to leave edit mode and return to command mode again you just need to hit `ESC`.

To get an overview of functions which are available in command and in edit mode, you can open up the overview of key shortcuts by using menu entry `Help → Keyboard Shortcuts`.

![Notebook Keyboard Shortcuts](/img/getting-started-with-jupyter/keyboard-shortcuts.png)

##### Exporting the Notebook

Jupyter Notebook gives you several options to export your notebook. Those options can be found in menu `File → Download as`.

![Notebook Download](/img/getting-started-with-jupyter/download-nb.png)

This was a generic overview on Getting Started with the Jupyter Notebooks. If you are interested to learn more about Jupyter Notebooks, make sure to put them down in the comments section below. We will come back with a blog or video on the topic.

_**Recommended articles**_

1. [Unpacking Iterables in Python](https://www.pylenin.com/blogs/unpacking-iterables-in-python/)
2. [Power of zip() in Python](https://www.pylenin.com/blogs/python-zip-function/)
3. [A Step-by-Step guide to Python Logging](https://www.pylenin.com/blogs/python-logging-guide/)
