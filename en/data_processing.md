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

# 7. Descriptive data analysis

## What do we use Python for?
In ‘DaLi topic 1: Basics of data evaluation’, the most important forms of visualisation and key figures required for 
data evaluation were presented.

As soon as we are dealing with the processing of real data sets (usually very extensive), software can help 
us to create certain key figures and forms of visualisation. This DaLi topic is therefore about analysing and 
visualising these data sets using software (Python or R).

To get a first impression of how we can use Python in this context, we use the ‘Tips’ dataset from ‘DaLi Topic 1: 
Fundamentals of data analysis’ that we are already familiar with.

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

In the following, we will first briefly explain what the following code does and then you will find the code and 
the corresponding output.

## Get initial information about a data set
The following two functions are built into Python via the pandas library. They are useful for gaining an initial 
overview of a dataset and the characteristics of its features.
- *info()* provides details about the data structure, such as column names, data types, and the number of non-missing 
values.
- *describe(include='all')* returns summary statistics for each column — including minimum, maximum, mean, quartiles, 
and more. It also includes categorical variables if include='all' is specified.

These functions are ideal for quickly identifying potential issues (e.g. missing values or incorrect data types) and 
getting a basic sense of the data distribution.
```{code-cell}
import pandas as pd
tips = pd.read_csv("tips.csv")

tips.info()
tips.describe(include='all')
```

You can obtain similar information by using the *skim()* function from the *skimpy* library.
```{code-cell}
from skimpy import skim
import pandas as pd
tips = pd.read_csv("tips.csv")

skim(tips)
```

## Create bar chart
Below you can see a variant for creating a bar chart. The *bar()* function from the *matplotlib* library is used to 
display the frequencies of the categories 'Female' and 'Male' in the 'sex' column of the dataset.

First, the *Pandas* library is used to load the dataset *tips.csv*. Then, the *value_counts()* function is applied to 
the'sex' column to count how often each gender appears. These counts are stored in the variable 'sex_counts', and the 
corresponding category labels and values are extracted.

Finally, a simple vertical bar chart is created with *plt.bar()*. The chart includes a title and axis labels to make the 
information easier to interpret.
```{code-cell}
import pandas as pd
import matplotlib.pyplot as plt
tips = pd.read_csv("tips.csv")

sex_counts = tips["sex"].value_counts()
labels = sex_counts.index
values = sex_counts.values

plt.bar(labels, values)

plt.title("Number of guests by gender")
plt.xlabel("Gender")
plt.ylabel("Number")
plt.show()
```

## Split bar chart
The following code creates a grouped bar chart that shows the number of guests by gender, separated by time of day 
(Lunch vs. Dinner). This is achieved using Seaborn’s *catplot()* function, which allows for the creation of multiple 
subplots based on the values of a categorical feature.

The argument *col="time"* specifies that a separate chart should be created for each value in the time column. The 
result is two side-by-side bar charts showing the distribution of genders for lunch and dinner, respectively.

This visualization is helpful to compare how the gender distribution of guests differs between the two meal times.
```{code-cell}
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
tips = pd.read_csv("tips.csv")
tips = sns.load_dataset("tips")

g = sns.catplot(
    data=tips,
    x="sex",
    kind="count",
    col="time",
)

g.set_titles("Time: {col_name}")
g.set_axis_labels("Gender", "Count")
plt.show()
```

## Create histogram
The following code creates a histogram that visualizes the frequency distribution of invoice amounts in the dataset. 
The function plt.hist() from the Matplotlib library is used to display how often invoice amounts within specific value 
ranges occur. 

*edgecolor="black"* adds clear borders to each bar.

The x-axis represents the invoice amounts in dollars, while the y-axis shows the number of invoices that fall into 
each interval.
```{code-cell}
import pandas as pd
import matplotlib.pyplot as plt
tips = pd.read_csv("tips.csv")

plt.hist(
    tips["total_bill"],
    edgecolor="black"
)
plt.title("Frequency distribution of the invoice amount")
plt.xlabel("Invoice amount in $")
plt.ylabel("Number")
plt.show()
```

## Create scatter plot
The following code creates a scatter plot to visualize the relationship between the total bill and the tip amount. 
The *plt.scatter()* function from the Matplotlib library is used to plot each observation as a point, where:
- the x-axis represents the total bill in dollars
- the y-axis represents the corresponding tip amount

Each point in the diagram corresponds to one row in the dataset. This type of visualization is useful for identifying 
patterns or trends — for example, whether higher bills are associated with higher tips.
```{code-cell}
import pandas as pd
import matplotlib.pyplot as plt
tips = pd.read_csv("tips.csv")

plt.scatter(
    tips["total_bill"],
    tips["tip"]
)

plt.title("Tip vs. Total Bill")
plt.xlabel("Total Bill ($)")
plt.ylabel("Tip ($)")
plt.show()
```

## Create scatter plot with regression line
The following code creates a scatter plot that shows the relationship between the total bill and the tip amount. 
In addition to the individual data points, it includes a regression line, which models the linear relationship between 
the two variables.

This is done using the *lmplot()* function from the Seaborn library.
- The parameter x="total_bill" defines the variable on the x-axis,
- y="tip" defines the variable on the y-axis,
- and Seaborn automatically fits and draws a linear regression line through the data.
```{code-cell}
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
tips = pd.read_csv("tips.csv")

sns.lmplot(
    data=tips,
    x="total_bill",
    y="tip"
)

plt.title("Tip vs. Total Bill with Regression Line")
plt.xlabel("Total Bill ($)")
plt.ylabel("Tip ($)")
plt.show()
```

## Create mosaic plot
The following code creates a mosaic plot to visualize the relationship between the categorical variables gender (sex) 
and time of day (time) in the dataset.

A mosaic plot shows the relative frequencies of combinations of categorical values using rectangles whose areas are 
proportional to the number of observations. In this example:

The x-axis is split according to the values of sex (Female / Male),
and each section is further divided based on time (Lunch / Dinner).
This allows you to easily see whether, for example, a higher proportion of men or women visited the restaurant at a 
particular time of day.

The plot is created using the *mosaic()* function from the statsmodels library, which is specifically designed for this 
type of categorical visualization.
```{code-cell}
import pandas as pd
from statsmodels.graphics.mosaicplot import mosaic
import matplotlib.pyplot as plt
tips = pd.read_csv("tips.csv")

mosaic(tips, ['sex', 'time'])

plt.title("Mosaic Plot: Gender vs. Time")
plt.xlabel("Sex")
plt.ylabel("Proportion")
plt.show()
```

## Create Boxplot
The following code creates a boxplot that compares the distribution of total bill amounts for the two time categories: 
Lunch and Dinner.

Each box represents the spread of the data for one group and includes:
- the median (horizontal line inside the box),
- the interquartile range (the box itself),
- and potential outliers (individual dots).

The x-axis shows the two time categories (time), while the y-axis displays the corresponding invoice 
amounts (total_bill).
This visualization makes it easy to compare whether bills are generally higher at dinner than at lunch.
```{code-cell}
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
tips = pd.read_csv("tips.csv")

sns.boxplot(
    data=tips,
    x="time",
    y="total_bill",
)

plt.title("Boxplot of Total Bill by Time")
plt.xlabel("Time of Day")
plt.ylabel("Total Bill ($)")
plt.show()
```

## Determine distribution function
The following code computes and visualizes the empirical cumulative distribution function (ECDF) for the 
variable total_bill.

An ECDF shows, for each value on the x-axis, the proportion of observations that are less than or equal to that value. 
The result is a step-shaped curve that increases from 0 to 1. This type of plot is useful to understand how values are 
distributed across the dataset — for example, to estimate what share of bills are below a certain amount.

The function *plt.step()* is used to draw the ECDF as a step function, and grid lines are added to improve readability.
```{code-cell}
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.distributions.empirical_distribution import ECDF
tips = pd.read_csv("tips.csv")

ecdf = ECDF(tips["total_bill"])

plt.step(ecdf.x, ecdf.y, where="post")
plt.title("Empirical CDF of Total Bill")
plt.xlabel("Total Bill ($)")
plt.ylabel("Cumulative Probability")
plt.grid(True)
plt.show()
```
 