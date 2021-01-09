---
title: "Python program to find the square root"
description: "Learn to find square roots of numbers in Python3"
date: 2021-01-08T19:49:42+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Square root of Positive Numbers

**Code**

```python3
num = 4

sqrt_num = num ** 0.5
print(f"Square root of {num} is {sqrt_num}")
```

**Output**

```bash
Square root of 4 is 2.0
```

#### Square root of Positive numbers - through User Input

**Code**

```python3
num = input("Enter a number: ")

sqrt_num = float(num) ** 0.5
print(f"Square root of {num} is {sqrt_num}")
```

**Output**

```bash
Enter a number: 9
Square root of 9 is 3.0
```

Now be careful with this method. We are using the `input()` built in function of Python. Since it returns a string, we convert the string into number using the `float()` function. Then, the square root is calculated.

Using the built in `int()` function will chop off the decimal places.

#### Square root of Complex Numbers

**Code**

```python3
import cmath

num = 3+5j

sqrt_num = cmath.sqrt(num)
print(f"Square root of {num} is {sqrt_num}")
```

**Output**

```bash
Square root of (3+5j) is (2.101303392521568+1.189737764140758j)
```

#### Square root of Complex Numbers - through user input

**Code**

```python3
import cmath

user_input = input("Enter a complex number: ")
num = eval(user_input)

sqrt_num = cmath.sqrt(num)
print(f"Square root of {num} is {sqrt_num}")
```

Here we are using the `eval()` built in function in Python instead of `float()` to convert user input string to complex numbers.

**Output**

```bash
Enter a complex number: 2+3j
Square root of (2+3j) is (1.6741492280355401+0.8959774761298381j)
```

All the above codes use **f-strings**. Learn about python f-strings [here](https://www.pylenin.com/blogs/f-strings-python/).

