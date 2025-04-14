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
  <a href="../../../de/functions.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../../../en/functions.html">🇬🇧 English</a>
</div>

# 4. Functions and Classes
Functions and Classes are Python's primary way to store code blocks for repeated executions.

## Functions
```{note}
## Namespaces
```
Functions are a way to assign a name to a certain code block so that it can be repeatedly executed with different starting values (inputs).

Each function starts with a header that contains the key word "def" followed by the name you want to give the function. After that, there must be a pair of round brackets and the required inputs within these brackets. A double colon follows after the brackets and the corresponding function code block is intended, just like we saw for loops and conditions. The function code block usually ends with a return statement, which defines what the function gives back to the user. We can then call the function using its function name and the desired input in round brackets.

For example, if we want to create a function that returns the value of x^2+2 where x is our input:
```{code-cell}
def example_function(x):
    result = x ** 2 + 2
    return result

function_result = example_function(2)
print(function_result)
```

You can also give a function multiple inputs. For instance, if we want to calculate x^k+2 with x and k as inputs:
```{code-cell}
def example_function(x, k):
    result = x ** k + 2
    return result

function_result = example_function(2, 3)
print(function_result)

```

We can also assign a default value to one or more inputs in the function header. Here is an example, where we use k=2 as a default value:
```{code-cell}
def example_function(x, k=2):
    result = x ** k + 2
    return result

# Default
function_result = example_function(2) # We don't have to specify k
print(function_result)

# When we want something other than the default:
function_result = example_function(2, 3) # We need to define k
print(function_result)
```

Sometimes functions can have dozens of input variables. In these cases, we might not want to assign every single variable in the function call if we just want to change one default value. We can do that by assigning a value to that variable during the function call explicitly: 
```{code-cell}
def example_function(x, a=1, b=1, c=1, d=1, e=1, f=1, k=2):
    result = x ** k + 2
    return result

function_result = example_function(2, k=3) # We change only the default value of k
print(function_result)
```

If we want to describe our functions, which can be helpful if other people want to use them, we can use docstrings. These are created when you create a string with three quotation marks directly after the function header:

```{code-cell}
def example_function(x, k=2):
    """This is an example function. That calculates x^k + 2
    Args:
        x: The number to calculate the exponential + 2 for.
        k: The exponent
    Returns:
        x^k + 2
    """
    result = x ** k + 2
    return result

print(help(example_function))
```


## Classes
```{note}
The names of classes are usually capitalized while the names of functions and variables are written in lowercase.
```
Classes are bigger structures that can store multiple functions and variables. This is usually done to create a coherent object that can perform complex operations that need multiple functions to work.

Classes are created using a header with the structure "class Class_Name". Additionally, each class must contain the initialization function "__init__(self, ...)". 
- The underscores indicate, that the function is not to be tempered with by users. 
- The input "self" is used in (almost) every function in a class. Using that input, the function can call other functions and variables within the class.

Let's test this. Let's first create a class that takes a variable x as an input during the initialization. Then we create two functions: One calculates x^k and the other calculates x^k+m. We call the first function during the second one to calculate x^k:  

```{code-cell}
class Example_Class:
    def __init__(self, x):
        self.x = x  # use self to set a variable for the entire class
        # Also note that we have two intends here, because we define a function within a class, so we need to use the tabulator twice
        
    def exponential(self, k=2):
        result = self.x ** k  # reference the global variable x with self.x 
        return result
        
    def exponential_plus_m(self, k=2, m=2):
        exponential_result = self.exponential(k)  # call the exponential function of the same class with self.exponential(...)
        result = exponential_result + m
        return result

exponential_calculator = Example_Class(x=2)
result1 = exponential_calculator.exponential(k=3) # Calling the first function 
print(result1)
result2 = exponential_calculator.exponential_plus_m(k=3, m=4) # Calling the second function
print(result2)
# We can also directly reference variables within the class:
print(exponential_calculator.x)
```
As you can see, we call functions and variables within the class after creating an object of the class by simply using a "." after the name of our class object. 


