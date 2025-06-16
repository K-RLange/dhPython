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
  <a href="../de/pandas.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/pandas.html">🇬🇧 English</a>
</div>

# 4. pandas and matplotlib
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
As you can see, pandas allows us to neatly organize our data into a table.

We can now use pandas group_by function to group our data by a certain column and then apply another function to each group. In this case, we will group by the "Hobby" column and check how many people have the same hobby:
```{code-cell}
df_grouped = df.groupby("Hobby").size()
print(df_grouped)
```

Now, lets say we have a csv-file called "prices.csv" that we would normally open in Microsoft Excel that contains data we want to analyze. pandas allows us to read Excel files and turn them into a pandas DataFrame in just one line.
```{code-cell}
price_data = pd.read_csv("prices.csv")
print(price_data)
```

It contains timestamps and the differences in a stock course that happened between the timestamps. If we only want to see the data for a specific time period, we can filter the DataFrame by using the "loc" function. In this case, we want to see the data from 2023-01-01 to 2023-01-31:
```{code-cell}
start_date = "2022-02-01"
end_date = "2023-09-01"
filtered_data = price_data.loc[(price_data["timestamp"] >= start_date) & (price_data["timestamp"] <= end_date)]
print(filtered_data)
```

To plot this time-dependent data, we can first turn the timestamp-column into a date format and then plot it.
```{code-cell}
import matplotlib.pyplot as plt
price_data["timestamp"] = pd.to_datetime(price_data["timestamp"])
price_data.plot(x="timestamp", y="difference")
plt.show()
```