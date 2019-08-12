# Installing Jupyter Locally

To locally use Jupyter:

- Install Python
- Install Jupyterlab 
- Running the Notebook

## Installing Python

First go to the official python website's download page: [https://www.python.org/downloads/](https://www.python.org/downloads/) and click on "Download Python 3.x.x" where "x" is any version number.

It's important that the version you install is version 3 and up as it's older version 2 is very different.

Once the installer is finished downloading, run the installer. Before clicking "Install Now", __check the "Add Python 3.x to PATH"__ if it's available and you're on windows:

![](/img/others/add-py-to-path.PNG)

To test, open your terminal (CMD for windows) and type in:

```
python
```

It should output something like:

```
Python 3.7.4 (tags/v3.7.4:e09359112e, Jul  8 2019, 19:29:22) [MSC v.1916 32 bit (Intel)] on win32                       Type "help", "copyright", "credits" or "license" for more information.
>>>  
```

Try printing out anything:

```python
print("Hello World")
```

And when it prints, you're sure that python is working well without problems. To exit, just type in:

```
exit()
```

## Install Jupyterlab

Open your terminal (CMD in windows) and type in the command:

```
pip install jupyterlab
```

This will download the package jupyterlab which enables you to run jupyter notebooks.

The installation should look something like this:
![](/img/others/installing-jupyterlab.PNG)

This process will usually take some time so just leave it until it's done.

## Running the Notebook

In your terminal (CMD in windows), type in the command:

```
jupyter notebook
```

This will open a page on your browser that should look something like below:

![](/img/others/active-notebook.PNG)

To turn it off, just press CTRL + C on the terminal or close it.