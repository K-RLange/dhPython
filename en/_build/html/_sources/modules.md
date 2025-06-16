---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
    class: no-execute
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
<div style="float: right;">
  <a href="../de/modules.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/modules.html">🇬🇧 English</a>
</div>

# 3. Modules
While basically anything can be coded from scratch in Python, it is wise to first see if someone has already implemented what you are trying to do. That can save time and effort and the implementation is hopefully done well from someone confident enough to share their code online.

To use functions, classes and other code that has been published online, you must import their respective modules.

Modules are what we call code files. They are organized in libraries (also called packages), which are an organized collection of modules.


## Installing libraries
Python comes with a small number of pre-installed modules and libraries. But there are many more out there, which you will have to install first.

The releases of Python libraries are usually released on the [Python Package Index (PyPi)](https://pypi.org/). 

To install libraries from PyPi, you can use **pip**, which comes pre-installed with every Python version from Python 3.0 onwards.

You can call pip to install a certain package within Python, but it is generally recommended to call it outside of Python in a terminal.

Let's say, we want to install the very popular "pandas" package. To install it directly from Python, you can call the "main" function of the pip library. This function takes a list as an input. The first object of this list is the string "install", denoting that we want to install a library. The second is the name of the library you want to install:
```{code-block}
import pip
pip.main(["install", "pandas"])
```

If you are in a terminal instead (which is what I would recommend), you can use the following command:
```bash
pip install pandas
```

## Importing modules
To import a module or libraries, you can just use "import module_or_library_name" in your Python console.

When you import a module, you can call the functions within it using "module_or_library_name.function()". Let's see how this looks like, if we want to calculate the mean of a list, for which we need to import the statistics module:
```{code-cell}
import statistics
print(statistics.mean([1, 2, 3]))
```

Alternatively, you can also import only certain functions from that module. To do this, you can use "from module_or_library_name import function".
```{code-cell}
from statistics import mean
print(mean([1, 2, 3]))
```

If we want to import the entire library but do not want to write out the full name of the library every time or if we already have a variable with the same name in your namespace, we can give the library a nickname while importing by using the key word "as". Here is an example for the library pandas:
```{code-cell}
import pandas as pd
```

### Importing local modules
You can import local code files in the same manner in which you import modules created by other people. If you have created a code file called "module.py", you can import it using:
```{code-block}
import module
```

When module is in a different directory, you can still import it. When the module is two directories above the current one, you need to add two dots in front of the module's name:
```{code-block}
import ..module
```

If you want to import a module in a subdirectory, you can import it like this:
```{code-block}
import subdirectory.module
```