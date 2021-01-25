---
title: "Python program to print over the same line"
description: "Learn how to print over and over the same line in Python"
date: 2021-01-25T23:40:42+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Let's say you have a bunch of print statements.

**Code**

```python3
print("Pylenin")
print("loves")
print("Python")
```
The output will look like below.

**Output**

```bash
Pylenin
loves
Python
```

However, **if you want to print over and over the same line in Python**, you have to use the **carriage return `\r` symbol.**

**Code**

```python3
print("Pylenin", end="\r")
print("loves", end="\r")
print("Python")
```

**Output**

```bash
Python
```

Even though the first 2 print statements are executed, the carriage returns makes the next **stdout** line start at the beginning of the current line.

Learn about `end`, `sep` and `flush` parameters of `print()` function [here](https://www.pylenin.com/blogs/python-print/).

**Recommended Reading**

* **[Installing IDEs for Python](https://www.pylenin.com/tags/python-ide/)**
* **[Dive Deeper into Python Print](https://www.pylenin.com/blogs/python-print/)**
* **[Using Comments in Python](https://www.pylenin.com/blogs/python-comments/)**
* **[Keywords and Identifiers in Python](https://www.pylenin.com/blogs/keywords-identifiers/)**
* **[Understanding Variables in Python](https://www.pylenin.com/blogs/python-variables/)**
