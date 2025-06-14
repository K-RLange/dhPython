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
  <a href="../de/data_processing.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/data_processing.html">🇬🇧 English</a>
</div>

# 7. Data Processing

## What do we use Python for?
In ‘DaLi topic 1: Basics of data evaluation’, the most important forms of visualisation and key figures required for 
data evaluation were presented.

As soon as we are dealing with the processing of real data sets (usually very extensive), software can help 
us to create certain key figures and forms of visualisation. This DaLi topic is therefore about analysing and 
visualising these data sets using software (Python or R).

To get a first impression of how we can use Python in this context, we use the ‘Tips’ dataset from "DaLi Topic 1: 
Fundamentals of data analysis" that we are already familiar with.

## Brief description of the data set Tips
A waiter recorded information on every tip he received in a restaurant over a period of several months. Several 
variables were recorded:
- Bill amount in dollars (total_bill)
- Tip in dollars (tip)
- Gender of the bill payer (sex)
- Smokers among the guests (smoker)
- Day of the week (day)
- Time of day (time)
- Size of the group (size)

## Get initial information about a data set
To plot this time-dependent data, we can first turn the timestamp-column into a date format and then plot it.
```{code-cell}
from skimpy import skim
import pandas as pd
tips = pd.read_csv("tips.csv")
skim(tips)
```






