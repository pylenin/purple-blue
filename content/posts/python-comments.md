---
title: "Using comments in Python 3"
description: "Learn to use various types of comments in Python 3"
date: 2021-01-21T10:35:47+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Getting Started with Python']
categories_weight: 5
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

A lot of times you will have difficulties figuring out what is going on in a Python program.
Even if you are the author of the program, you might have difficulties navigating your own code after a period of time.

Comments are very useful in such scenarios as they describe the intent and functionality of your code.

In Python, you can write comments in 3 different ways.

1. [Single line comments](#single-line-comments)
2. [Multi-line Comments](#multi-line-comments)
3. [Docstrings](#docstrings)

#### Single line Comments

You can use the hash symbol `#` to write single-line comments in Python.
Everything that comes after the hash symbol `#` is ignored by the Python interpreter.

**Code**

```python3
# printing Hello World
print("Hello World!")

x = 10
y = 20
# Tuple Swap
x, y = y, x

str1 = "Pylenin loves Python"
# Return the first and last character
print(str1[0] + str1[-1])
```

#### Multi-line Comments

Python doesn't provide any unique way for multi-line comments.
However, any string can be used as a comment in Python, as long as it is not asigned to a variable. Python interpreter ignores such strings.

**Code**

```python3
 
"This line will be ignored"
print("Pylenin loves Python")

"""
Bigger comments can be written
over multiple lines.
This is a multi-line comment.
"""
print("Pylenin loves Python")
```

Run the above code and you will see that no errors are raised by Python.

#### Docstrings

Docstrings are not similar to comments. However, they have a similar purpose.

Docstring is short for **documentation string**.

Python docstrings are the string literals that appear right after the definition of a function, method, class, or module.
They are used to provide a meaningful description about the above mentioned objects.

Use triple quotes to write docstrings.

**Code**

```python3
def addition(x,y):
    """Takes x and y and returns their sum"""
    return x+y

print(addition.__doc__)
```

**Output**
```bash
Takes x and y and returns their sum
```

You can also use Docstrings in a Python class.

**Code**
```python
class Person:
    """Stores the name, age and country of a person"""
    def __init__(self, name, age, country):
        self.name = name
        self.age = age
        self.country = country

print(Person.__doc__)
```

**Output**

```bash
Stores the name, age and country of a person
```

#### Where to use comments and Docstrings?

**Use comments** where you believe the way your code written is not too obvious to understand for a programmer.

**Use docstrings** to provide information about various objects like functions and classes in your code.


