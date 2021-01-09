---
title: "How input() works in Python?"
description: "Learn to use input() built-in function in Python"
date: 2021-01-10T00:49:17+05:30
draft: false
image: /img/pylenin_logo.png
tags: []
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

The `input()` method prompts user for an input, reads the line from input, converts into a string and returns it.

##### Example 1

**Code**

```python3
user_input = input("Enter a string==> ")

print(f"The user input is {user_input}")

print(type(user_input))
```

**Output**

```bash
Enter a string==> Hello
The user input is Hello
<class 'str'>
```

##### Example 2

Even if you enter numerical values, the `input()` built-in function converts it to strings.

**Code**

```python3
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")

print(type(num1), type(num2))

# User might enter float
sum = float(num1) + float(num2)

# We get a float value
print(f"The sum of {num1} and {num2} is {sum}")
```

**Output**

```bash
Enter first number: 2
Enter second number: 3
<class 'str'> <class 'str'>
The sum of 2 and 3 is 5.0
```

The above codes use **f-strings**. Learn about python f-strings [here](https://www.pylenin.com/blogs/f-strings-python/).