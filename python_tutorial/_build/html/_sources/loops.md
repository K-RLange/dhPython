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

# 3. Conditions and Loops
Programming often does not stop at creating variables. In many cases, you want to perform certain actions only under specific conditions or you want to repeat certain actions multiple times. This is where conditions and loops come into play.

## Conditions
Conditions are used to check whether a certain statement is true or false. 
If the statement is true, a certain action is performed. If the statement is false, 
another action is performed. Such conditions are always binary and can thus be represented
by a boolean variable.

```{note} Code blocks
In Python, the colon ":" is used to indicate the start of a block of code. All following lines that belong to that code block are then indented by four spaces (usually one tabulator-press). This is the way, Python interprets, which lines of code belong together and is a must. Otherwise, your code will throw errors.
This structure - a colon followed by intended lines - happens whenever you want to check for a condition, loop over something, create a function or a class. 
How these other blocks of code work will be explained in later sections, but it is important to remember that they always follow this simple structure.
```
We check for conditions using the "if" keyword and create an intended code block that is executed if and only if the condition is met.

In the following cell, we define a boolean and check whether it is true or not. If it is true, we print "The boolean is true".
```{code-cell}
boolean = True
if boolean:
    print("The boolean is true")
```

We can also define what happens, if the condition is not met. We can do this by using the "else" keyword directly after the "if"-code block has ended. 

The following code cell checks if a certain number is larger than 5. If this is the case, it prints "The number is larger than 5". If the number is not larger than 5, it prints "The number is not larger than 5".

```{code-cell}
number = 6
if number > 5:
    print("The number is larger than 5")
else:
    print("The number is not larger than 5")
```

We can even go further and check multiple conditions. We can do this by using the "elif" keyword. This keyword is short for "else if" and is used to check another condition if the first condition is not met.
It is different from "else", because it does not always execute its code block, if the original "if" condition wasn't met, but only if an additional condition is met..

In the following cell, we check if a number is larger than 0, larger than 5 or larger than 10. We print the result of each check.

```{code-cell}
number = 6
if number > 10:
    print("The number is larger than 10")
elif number > 5:
    print("The number is larger than 5 but smaller or equal to 10")
elif number > 0:
    print("The number is larger than 0 but smaller than 5")
else:
    print("The number is smaller or equal to 0")
```