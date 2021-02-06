---
title: "Python program to check if a number is odd or even"
description: "Learn how to check if a number is odd or even in Python"
date: 2021-02-06T09:39:27+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

A number is divisible by 2, it is even, else odd. 
You can use the modulus operator `%` to compute the remainder. 
**If the remainder is not zero, the number is odd.**

### Example 1

**Code**

```python3
num = 12

if num%2 == 0:
    print("It is even")
else:
    print("It is odd")
```

**Output**

```bash
It is even
```

### Example 2 - Asking for user input

**Code**

```python3
num = int(input("Enter a number ==> "))

if num%2 == 0:
    print("It is even")
else:
    print("It is odd")
```

**Output**

```bash
Enter a number ==> 9
It is odd
```

The above code uses the [input() function](https://www.pylenin.com/blogs/how-input-works-python/) to ask for user input. 