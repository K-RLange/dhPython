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
  <a href="../../../de/_build/html/arithmetics.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../../../en/_build/html/arithmetics.html">🇬🇧 English</a>
</div>


# 1. Arithmetics and variables

## Arithmetics
In its most basic form, Python can simply be used as a calculator. You can use it to, among others, add, subtract, multiply, and divide numbers.

The following cell shows you how to add two numbers in Python:
```{code-cell}
print(2 + 3)
```
To show any object within Python in your console, you can use the print(...) command, in which you can replace "..." with the object that you want to display. In this case, it is the answer of 2+2.

Other numeric calculations can be performed like this:
```{code-cell}
print(3 * 4)  # Multiplication
print(3 - 2)  # Subtraction
print(10 / 2)  # Division
print(10 ** 2)  # Exponentiation
print(10 % 3)  # Modulo
```
The "#" symbol is used to comment out code. This means that the code following the # symbol will not be executed. Comments are useful to explain what the code does.

## Variables
````{margin}
```{note}
When naming variables, you should take care to not overwrite existing names. You should, for instance, not name a variable "print", because it would overwrite the meaning of the print function. This would lead to an error, when you try to use the print function later on.
```
````
In Python, you can also store values in variables. This is useful when you want to use a value multiple times in your code. You can assign a value to a variable using the = operator. 
Variables can take any name. In a practical analysis, it is suggested to use meaningful names for your variables. This makes it easier for you and others to understand the code.

The following cell shows how to assign a value to a variable and then print it:
```{code-cell}
x = 5
print(x)
```

If you want to alter the variable, you can also do this using the "=" operator:
```{code-cell}
x = 5
print(x)
x = x + 5
print(x)
```

You can thus use variables as placeholders for objects. In this case, x is assigned to be an integer (a whole number). If we define another variable y to be an integer as well, we can perform calculations with these variables:
```{code-cell}
x = 5
x = x + 2
y = 10
z = x + y
print(z)
```

## Exercise
Now it is your turn! Solve the following exercise and click on the hidden code cell below to view the solution.

### Exercise 1
Calculate the sum of 5 and 7 and store the result in a variable called "var1". Then multiply this variable with itself and store the result in a variable called "var2". Finally, print the result of "var2". 
```{code-cell}
# Your code here
```
```{code-cell}
:tags: ["hide-cell"]
var1 = 5 + 7
var2 = var1 * var1
print(var2)
```

### Exercise 2
```{code-cell}
:tags: ["thebe-remove-input-init"]
example=[{
        "question": "What is the correct syntax for multiplying 3 with 7, storing the result in a variable and printing that variable?",
        "type": "multiple_choice",
        "answers": [
            {
                "code": """x = 3 * 7
print(x)""",
                "correct": True,
                "feedback": "Correct." 
            },
            {
                "code": """3 * 7
print(x)""",
                "correct": False,
                "feedback": "x would not be defined here, so there is nothing to print."
            },
            {
                "code": "print(3 * 7)",
                "correct": False,
                "feedback": "This does print the result of 3 * 7, but does not store it in a variable for later use."
            },
            {
                "code": "print(x = 3 * 7)",
                "correct": False,
                "feedback": "The print function would be confused, because you are trying to assign a value to x and print it at the same time. Try to separate these two steps."
            }
        ]
    }]
```