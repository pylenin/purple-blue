---
title: "% operator - Python String formatting"
description: "Learn to perform string formatting with % operator in Python"
date: 2021-01-12T08:35:06+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string formatting']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> **Note:-** Python community support better ways of string formatting using the [string.format()](https://www.pylenin.com/blogs/format-method-python-string/) method and [f-strings](https://www.pylenin.com/blogs/f-strings-python/).

#### % operator

In this article, you will learn to format strings using the `%` operator.
The `%` operator allows you to do simple positional formatting very easily.

**Code**

```python3
name = "Pylenin"
print("I am on %s website"%name)
```

**Output**

```bash
I am on Pylenin website
```

By using the `%s` format specifier, you are telling Python where to substitute the value of **name**.

You can also use other format specifiers that produce a different output format.

**Code**

```python3
name = "Pylenin"
num = 50
print("I am on %s website. It has %d blogs"% (name, num))
```

**Output**

```bash
I am on Pylenin website. It has 50 blogs
```

**The order in which you pass the values is very important.**

Let's look at the example.

**Code**

```python3
print("My name is %s. I love %s"%("Pylenin", "Python"))
print("My name is %s. I love %s"%("Python", "Pylenin"))
``` 

**Output**

```bash
My name is Pylenin. I love Python
My name is Python. I love Pylenin
```

This feature of the `%` operator can make your code unmaintainable.

You can avoid this by using **variable substitution** in your strings.

**Code**

```python3
name = "Pylenin"
language = "Python"

print("My name is %(name)s. I love %(language)s"\
      %{"name":"Pylenin", "language":"Python"})
```

**Output**

```bash
My name is Pylenin. I love Python
```

Apart from `%s` and `%d`, you can also use other format specifiers.

```bash
%s - string representation

%d - Integer representation

%f - Floating point representation

%.<number of digits>f - Floating point representation
                        with a fixed amount of digits 
                        to the right of the decimal.

%e - Exponential representation

%x/%X - Integers in hex representation (lowercase/uppercase)
```

Let's look at a few examples.

**Code**

```python3
str1 = "Pylenin"
num = 100

# String representation
print("My name is %s"%str1)

# Integer Representation
print("The number is %d"%num)

# Floating Point representation
print("Floating point representation of %s is %f"%(num, num))
print("Floating point representation of %s with precision 2 is %.2f"%(num, num))

# Exponential Representation
print("Exponential representation of %s is %e"%(num, num))
print("Exponential representation of %s with precision 2 is %.2e"%(num, num))

# Hex representation
print("Hex representation of %s is 0x%X"%(num, num))
```

**Output**

```bash
My name is Pylenin
The number is 100
Floating point representation of 100 is 100.000000
Floating point representation of 100 with precision 2 is 100.00
Exponential representation of 100 is 1.000000e+02
Exponential representation of 100 with precision 2 is 1.00e+02
Hex representation of 100 is 0x64
```

**Python offers 3 other ways of String Formatting. Check out [the definite guide to Python String Formatting](https://www.pylenin.com/blogs/python-string-formatting/)** 

#### Related Articles

1. [f-strings in Python](https://www.pylenin.com/blogs/f-strings-python/)
2. [Python String format() method](https://www.pylenin.com/blogs/format-method-python-string/)
3. [Python String Template Class](https://www.pylenin.com/blogs/python-string-template-class/)
4. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
5. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
6. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
7. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
8. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
9. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
10. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
11. [Commonly used Python string methods](https://www.pylenin.com/blogs/common-python-string-methods)