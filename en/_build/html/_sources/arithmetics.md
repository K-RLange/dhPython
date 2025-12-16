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
  <a href="../de/arithmetics.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/arithmetics.html">🇬🇧 English</a>
</div>


# 1. Arithmetics and variables

## Arithmetics
In its most basic form, Python can simply be used as a calculator. You can use it to, among others, add, subtract, multiply, and divide numbers.

The following cell shows you how to add two numbers in Python:
```{code-cell}
print(2 + 3)
```
To show any object within Python in your console, you can use the print(...) command, in which you can replace "..." with the object that you want to display. In this case, it is the answer of 2+3.

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

`````{margin}
```{attention}
To edit and run the Python code in this course, you will find this ![live code symbol](code_symbol.PNG) symbol on the top of each page that contains Python code. You can click on it and then choose "Live code" to edit and run code yourself. Please feel free to test different things out and play around with the code. You cannot break anything here and nobody (including us) can see your code, so feel free to experiment.
```
`````

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
```{raw} html
<style>
  :root {
    --accent: #4f46e5;
    --accent-light: #eef2ff;
    --bg: #ffffff;
    --border: #e5e7eb;
    --text: #111827;
    --gray: #6b7280;
    --success: #16a34a;
    --error: #dc2626;
    --warning: #facc15;
  }

  #quiz-container {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 2rem;
    max-width: 750px;
    font-family: "Segoe UI", Roboto, sans-serif;
    color: var(--text);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
    transition: box-shadow 0.3s ease;
    margin-bottom: 2rem;
  }

  #quiz-container:hover {
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  }

  #quiz-container p.question {
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 1.5rem;
  }

  #quiz-form label {
    display: block;
    margin: 0.75rem 0;
    padding: 0.75rem 1rem;
    border-radius: 12px;
    border: 1px solid transparent;
    background-color: var(--accent-light);
    cursor: pointer;
    transition: all 0.25s ease;
  }

  #quiz-form label:hover {
    background-color: #e0e7ff;
    border-color: var(--accent);
  }

  #quiz-form input[type="radio"] {
    margin-right: 0.75rem;
    transform: scale(1.2);
    accent-color: var(--accent);
  }

   #quiz-form pre {
    margin: 0.2rem 0 0;
    background-color: transparent !important;  /* no background */
    border: none !important;                   /* no border */
    display: inline;
    font-size: 0.95rem;
    white-space: pre-wrap;
    padding: 0;                                /* no padding */
    font-family: 'Courier New', Courier, monospace;
  }

  #quiz-form button {
    margin-top: 1.5rem;
    background-color: var(--accent);
    color: white;
    padding: 0.6rem 1.2rem;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  #quiz-form button:hover {
    background-color: #4338ca;
  }

  #quiz-feedback {
    margin-top: 1.25rem;
    padding: 0.75rem 1rem;
    border-radius: 8px;
    font-weight: 500;
    font-size: 1rem;
    display: inline-block;
  }

  .success {
    background-color: #dcfce7;
    color: var(--success);
    border: 1px solid var(--success);
  }

  .error {
    background-color: #fee2e2;
    color: var(--error);
    border: 1px solid var(--error);
  }

  .warning {
    background-color: #fef9c3;
    color: var(--warning);
    border: 1px solid var(--warning);
  }
</style>

<div id="quiz-container">
  <p class="question">🧠 What is the correct syntax for multiplying 3 with 7, storing the result in a variable, and printing that variable?</p>
  <form id="quiz-form">
    <label>
      <input type="radio" name="answer" value="a">
      <pre><code>x = 3 * 7
print(x)</code></pre>
    </label>
    <label>
      <input type="radio" name="answer" value="b">
      <pre><code>3 * 7
print(x)</code></pre>
    </label>
    <label>
      <input type="radio" name="answer" value="c">
      <pre><code>print(3 * 7)</code></pre>
    </label>
    <label>
      <input type="radio" name="answer" value="d">
      <pre><code>print(x = 3 * 7)</code></pre>
    </label>

    <button type="button" onclick="checkAnswer()">Submit Answer</button>
    <p id="quiz-feedback"></p>
  </form>
</div>

<script>
  function checkAnswer() {
    const answers = {
      a: {
        correct: true,
        feedback: "✅ Correct! You assigned 3 * 7 to a variable and printed it."
      },
      b: {
        correct: false,
        feedback: "❌ x would not be defined here, so there is nothing to print."
      },
      c: {
        correct: false,
        feedback: "❌ This prints the result but doesn’t store it for reuse."
      },
      d: {
        correct: false,
        feedback: "❌ You can’t assign and print in one step like that."
      }
    };

    const selected = document.querySelector('input[name="answer"]:checked');
    const feedback = document.getElementById("quiz-feedback");

    if (!selected) {
      feedback.textContent = "⚠️ Please select an answer before submitting.";
      feedback.className = "warning";
      return;
    }

    const result = answers[selected.value];
    feedback.textContent = result.feedback;
    feedback.className = result.correct ? "success" : "error";
  }
</script>
```


