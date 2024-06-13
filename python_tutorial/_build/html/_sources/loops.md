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

The following code cell checks if a certain number is larger than 5. If this is the case, it prints "The number is larger than 5". If the number is not larger than 5, it prints "The number is not larger than 5".

```{code-cell}
number = 6
if number > 5:
    print("The number is larger than 5")
else:
    print("The number is not larger than 5")
```