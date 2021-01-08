---
title: "Python program to add two numbers"
description: "Learn to add two numbers in Python3"
date: 2021-01-08T19:49:42+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Method 1 - Simple addition

**Code**

```python3
num1 = 10
num2 = 5
  
# Adding both numbers 
sum = num1 + num2 
  
# printing values 
print(f"Sum of {num1} and {num2} is {sum}") 
```

**Output**

```bash
Sum of 10 and 5 is 15
```

#### Method 2 - Adding two number provided by user input

**Code**

```python3
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")

# User might enter float
sum = float(num1) + float(num2)

# We get a float value
print(f"The sum of {num1} and {num2} is {sum}")
```

**Output**

```bash
Enter first number: 10
Enter second number: 2
The sum of 10 and 2 is 12.0
```

Now be careful with this method. We are usiong the `input()` built in function of Python. Since it returns a string, we convert the string into number using the `float()` function. Then, the numbers are added.

Using the built in `int()` function will chop off the decimal places.

