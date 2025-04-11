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

# 6. pandas and numpy
```{code-cell}
#:tags: [remove-cell]
!pip install pandas numpy
#import pip
#pip.main(["install", "pandas"])
import pandas
print(pandas.__version__)
```
Remember the library we installed in the last chapter? That library is called pandas and is arguably the most commonly used library in Python. It allows us to turn any data into a table, which we can then plot and analyze.

Let's look at it in action:
```{code-cell}
import pandas as pd
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
hobby = ["Completing Python tutorials", "sports", "Completing Python tutorials"]
data = {"Name": names, "Age": ages, "Hobby": hobby}
df = pd.DataFrame(data)
print(df)
```
