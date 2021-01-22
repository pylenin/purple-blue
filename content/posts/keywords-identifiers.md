---
title: "Keywords and Identifiers in Python 3"
description: "Learn about reserved keywords, identifiers and their usage in Python 3."
date: 2021-01-21T21:16:02+02:00
draft: true
image: /img/python-print/python-print.png
categories: ['Getting Started with Python']
categories_weight: 5
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Python Keywords

Python has a bunch of reserved words. These are known as **Python keywords**. These keywords can't be used to name objects in Python like variables, functions and classes.

The following is a list of reserved keywords in Python 3.9.

```bash
False      await      else       import     pass
None       break      except     in         raise
True       class      finally    is         return
and        continue   for        lambda     try
as         def        from       nonlocal   while
assert     del        global     not        with
async      elif       if         or         yield
```

##### How to check if a string is a keyword?

Python provides a `keyword` module that allows you to check for reserved keywords.

**Code/Output**

```python3
import keyword

print(keyword.iskeyword("for"))
>>> True

print(keyword.iskeyword("str"))
>>> False
```

You could also get a list of all reserved keywords in Python.

**Code/Output**

```python3
import keyword

print(keyword.kwlist)
>>> ['False', 'None', 'True', '__peg_parser__', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

#### Python Identifiers

