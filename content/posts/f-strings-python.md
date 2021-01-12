---
title: "f-strings in Python"
description: "Learn to use f-strings in Python"
date: 2021-01-08T20:51:35+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**F-strings** is a string formatting mechanism introduced by [PEP 498](https://www.python.org/dev/peps/pep-0498/) for Python versions 3.6 and above.

Python supports multiple ways to format text strings.

* % formatting 
* .format()
* string.Template

Each of these methods have their advantages, but in addition have disadvantages that make them cumbersome to use in practice. This PEP proposed to add a new string formatting mechanism: Literal String Interpolation, also called `f-strings`(because of the leading f character preceding the string literal).

#### Create an f-string

To create an f-string, prefix a string with the letter `f`. It works similarly to `str.format()`.

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

#### Embed Python expressions in f-string

f-strings provide a convenient way to embed python expressions inside string literals for formatting.

**Code**

```python3
num1 = 10
num2 = 5
  
# printing values 
print(f"Sum of {num1} and {num2} is {num1+num2}") 
```

**Output**

```bash
Sum of 10 and 5 is 15
```