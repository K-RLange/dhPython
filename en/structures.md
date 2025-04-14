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
  <a href="../de/structures.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/structures.html">🇬🇧 English</a>
</div>

# 2. Data types
In the last chapter, we learned that variables can be assigned a whole number, resulting in an integer variable.
In Python, there are different types of data that can be stored in variables, an integer is just one of many forms a variable can take.
In this chapter, we will introduce you to the most common data types in Python.

## Variable types
### Numeric data types
In Python, there are two important numeric data types: integers ("int") and floating-point numbers ("float").
Integers are whole numbers, while floating-point numbers are numbers with a decimal point.
```{note}
Python is a dynamically typed language. This means that you do not need to declare the data type of a variable when you create one. Python will automatically infer the data type of the variable based on the value that you assign to it. This is true for all data types in Python, not just for numbers.
```
 ```{code-cell}
 x = 5
 y = 5.5
 print(type(x))
 print(type(y))
 ```

````{margin} Be careful!
Python will always try to detect what it deems to be the correct data type. This might lead to problems, when you want to have a specific data type, but Python converts your variables to a different type.

Let's say, we want to only use integers in a division. But in a divison, Python always converts numbers to floating numbers. To correct this mistake Python does, we might want to type-cast the result back to an integer:
````
```{code-cell}
:tags: [margin]
x = 10
y = 2
z = x / y
print(z, type(z))
z = int(z)
print(z, type(z))
```
````{margin}
We see that the value does not change, but only the decimal point disappears. Type-casting is an advanced technique, and should only be used if you require one specific data type.
You can read more about it [here](https://www.geeksforgeeks.org/type-conversion-python/). 
````
You can perform arithmetic operations on both types of numbers. 
Python will automatically convert the result to the data type, it deems to be most appropriate:
```{code-cell}
x = 5
y = 5.5
print(type(x + x))
print(type(x + y))
print(type(y + y))
```


### Strings
Strings are sequences of characters (letter, symbols, etc.). They can be created by enclosing characters in single or double quotes. You can also use triple quotes for multi-line strings.
While these are three options to define a string, they ultimately all have the same data type:
```{code-cell}
x = "Hello, World!"
y = 'Hello, World!'
z = """Hello,
World!"""
print(x, type(x))
print(y, type(y))
print(z, type(z))
```

### Booleans
Booleans are a data type that can only take two values: `True` or `False`. They are used to represent the truth value of an expression. You can check the data type of a boolean using the `type()` function:
```{code-cell}
x = True
y = False
print(type(x))
print(type(y))
```
We can also define a boolean relative to another variable. In the following code block, we define a boolean that checks if the number x is greater than 3. The result is then printed to the console:
```{code-cell}
x = 5
y = x > 3
print(y)
```
You can alter the number that is assigned to x to see how the boolean changes.

Booleans are often used in conditional statements, which we will discuss in a later chapter.

## Variable collection types
To not only store single values in variables, Python also offers the possibility to store multiple values in a single variable. These are called collections. The most common collection types in Python are lists, tuples, sets, and dictionaries.

### Lists
Lists are the most flexible way to store multiple variables. You can create a list by enclosing items in square brackets and separating them with commas:
In the following code block, we define a list x that contains the numbers 1 to 5 as integers:
```{code-cell}
x = [1, 2, 3, 4, 5]
print(x)
```

You can access items in a list by referring to the index number.
```{attention} Indexing
Counterintuitively, the indexing in Python starts at 0. This means that the first element in a list has the index 0, the second element has the index 1, and so on.
```
```{code-cell}
x = [1, 2, 3, 4, 5]
print(x[0])
```

You can also use negative indexing to get items "from the back" of the list. By using the index -1, you can access the last item in the list. By using -2, you can access the second-to-last item, and so on.
```{code-cell}
x = [1, 2, 3, 4, 5]
print(x[-1])
print(x[-2])
```

Lists are flexible. You can change a list at any time by adding, removing, or changing items. You can also add items to a list by using the `append()` method and remove items from a list by using the `remove()` method.
```{code-cell}
x = [1, 2, 3, 4, 5]
x.append(6)
x.remove(2)
print(x)
```

### Tuples
Tuples are the least flexible data type. Once a tuple is created, you cannot change its values. 
You should thus only use a tuple when you are sure that the data will not change.

You can create a tuple by enclosing items in parentheses and separating them with commas:
```{code-cell}
x = (1, 2, 3, 4, 5)
print(x)
```

A unique feature of tuples is the ability to assign multiple variables at once. This is called tuple unpacking:
```{code-cell}
x = (1, 2, 3)
a, b, c = x
print(a)
print(b)
print(c)
```


### Sets
Sets are unordered and unindexed. This means that you cannot access items in a set by referring to an index number.

You can create a set by enclosing items in curly brackets and separating them with commas:
```{code-cell}
x = {1, 2, 3, 4, 5}
print(x)
```

Set objects are always unique. You cannot have two items with the same value in a set.
```{code-cell}
x = {1, 2, 3, 4, 5, 5}
print(x)
```
You can also use this feature to turn a list into a set and back to a list to remove duplicates:
```{code-cell}
x = [1, 2, 3, 1, 4, 5]
x = set(x)
x = list(x)
print(x)
```

A second great advantage of sets is the ability to almost instantaneously search for objects within a set. The difference in speed between searching for an object in a list and a set becomes more apparent, the larger the data set becomes.
In the following code block, we define a set and then check if the number 3 is in the set. The code "3 in x" returns a boolean that is printed to the console:
```{code-cell}
x = {1, 2, 3, 4, 5}
print(3 in x)
```

### Dictionaries
Dictionaries extend the concept of sets. While sets only contain values, dictionaries contain key-value pairs.
That means that you are able to give each object you are interested in a unique identifier. 

In the following example you want to store the age of a person. You can do this by creating a dictionary with the name of the person as the key and the age as the value.
By indexing the dictionary with the name of the person, you can access the age of the person.
```{code-cell}
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
print(x["Alice"])
```
Dictionaries are very similar to sets: Firstly, they are unordered. This means that you cannot access items in a dictionary by referring to an index number. You must use the keys to index the elements.
Secondly, they use a hash algorithm, just like sets, with which you can instantainously search for a key in a dictionary.
```{code-cell}
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
print("Alice" in x)
```

Dictionaries are very flexible. You can add, remove, or change items at any time. You can also add items to a dictionary by using the key and the assignment operator and remove items from a dictionary by using the `pop()` method.
```{code-cell}
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
x["David"] = 40
x.pop("Bob")
print(x)
``` 

You can get all keys or all values of a dictionary by using the `keys()` and `values()` methods, respectively.
```{code-cell}
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
print(x.keys())
print(x.values())
```

## Exercises
Now it is your turn! Solve the following exercise and click on the hidden code cell below to view the solution.

### Exercise 1
Create a list that contains the numbers 1 to 10. Then, remove the number 5 from the list and add the number 11 to the list.
```{code-cell}
# Your code here
```
```{code-cell}
:tags: ["hide-cell"]
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
x.remove(5)
x.append(11)
print(x)
```

### Exercise 2
Create a list that contains the numbers 1 to 3. Then append the String "Four" to the list. Finally, print the list.
```{code-cell}
# Your code here
```
```{code-cell}
:tags: ["hide-cell"]
x = [1, 2, 3]
x.append("Four")
print(x)
```


### Exercise 3
Create a list that contains the numbers 1 to 3 twice. Turn this list into a list with only unique elements.
```{code-cell}
# Your code here
```
```{code-cell}
:tags: ["hide-cell"]
x = [1, 2, 3, 1, 2, 3]
x = set(x)
x = list(x)
print(x)
```

### Exercise 4
Create a dictionary that contains the names "Alice", "Bob" and "Charlie" as keys and their ages as values. Then, add anoter person with the name "David" with the same age as "Bob" to the dictionary. Then turn the values of the dictionary into a unique list. 
```{code-cell}
# Your code here
```
```{code-cell}
:tags: ["hide-cell"]
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
x["David"] = x["Bob"]
y = x.values()
y = list(set(y))
print(y)
```


