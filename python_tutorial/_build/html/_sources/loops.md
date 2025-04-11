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
number = 4
if number > 5:
    print("The number is larger than 5")
else:
    print("The number is not larger than 5")
```

We can even go further and check multiple conditions. We can do this by using the "elif" keyword. This keyword is short for "else if" and is used to check another condition if the first condition is not met.
It is different from "else", because it does not always execute its code block, if the original "if" condition wasn't met, but only if an additional condition is met.

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


## Loops
```{note} Copy-Pasting
When you want to repeat a certain action multiple times, you might think that just copying and pasting the code is a good idea. But this is not a good idea. 

Copy-Pasting is inefficient code usage. Your code will become bloated and more difficult to read for yourself and others.

Also, when you made a mistake in the code you copied, you will have to correct it not just once, but you will have to correct in every copy you made.
```
When you want to repeat a certain action multiple times, you can use a loop.
A loop can also be useful when you want to perform a certain action for each element in a list or other iterable object.

In Python, there are two types of loops: the "for" loop and the "while" loop.

### while loop
When you use a while-loop, the code will be executed only if a certain condition is met.

For instance, the while loop in the following code block checks if the variable "number" is smaller than 10 at the start of every iteration. If this condition is met, the code is executed, if not, the loop ends.
```{code-cell}
number = 0

while number < 10:
    number = number + 1
    print(number)
print("Loop has ended")
```

When the condition is not met, the loop does not execute at all.
```{code-cell}
number = 11

while number < 10:
    number = number + 1
    print(number)
print("Loop has not been executed")
```

Sometimes you want to check a condition during the run of a while loop, not at the start of each iteration. In these cases, you can check a condition that is always true in the header of the loop and use the "break" command in the code block:
```{code-cell}
number = 0
while True:
    if number >= 10:
        break
    number = number + 1
    print(number)
print("Loop has ended")
```

You can also use a combination of both:
```{code-cell}
number = 0
limit = 8

while number < 10:
    number = number + 1
    if number == limit:
        break 
    print(number)
print("Loop has ended")
```

### for loop
When you want to iterate over a list or a different type of iterable object, you can use a for loop.

For instance, if you want to iterate over the numbers from 0 to 9 and print them, you can use the following loop:
```{code-cell}
numbers = range(0, 10) # A quick iterable object between two numbers
# Alternatively you can use 
# numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

for number in numbers: # You iterate over a limited list, you need no end condition
    # We also do not need to update our "number" parameter, because that is done in the header of the for loop 
    print(number)
print("Loop has ended")
```

The enumerate function allows you to not just iterate over the objects within the list, but also over their indexes at the same time.
This is helpful, if you want to have two lists of the same size and want to work with both:
```{code-cell}
numbers = range(0, 10) 
larger_numbers = range(10,20)

for index, number in enumerate(numbers):
    print(larger_numbers[index] + number)
print("Loop has ended")
```

In the for loop, you can also use the break command to prematurely end your loop:
```{code-cell}
numbers = range(0, 10) 

for number in numbers:
    if number > 7:
        break
    print(number)
print("Loop has ended")
```

### List comprehention
A list comprehention is a way to create a list with a loop with just one line.

A list comprehention is written in the following structure: [f(x) for x in iterable]. On the left hand side, you apply a function f to x. x is an object from an iterable that you are looping over. You surround this with square brackets to indicate that you want the results of f(x) to create a list.

In practice, it might look like this:
```{code-cell}
numbers = range(0, 10) 
larger_numbers = range(10,20)

even_larger_numbers = [number + larger_numbers[index] for index, number in enumerate(numbers)]
print(even_larger_numbers)
print("Loop has ended")
```

## Exercises