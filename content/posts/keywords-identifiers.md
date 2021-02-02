---
title: "Keywords and Identifiers in Python 3"
description: "Learn about reserved keywords, identifiers and their usage in Python 3."
date: 2021-01-21T21:16:02+02:00
draft: false
image: /img/pylenin_logo.png
categories: ['Getting Started with Python']
categories_weight: 5
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Python Keywords

Python has a bunch of reserved words. These are known as **Python keywords**. These keywords can't be used to name objects in Python like variables, functions and classes.

**Keywords in Python are case-sensitive.**

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

##### Simple use of if-else in Python

**Code**

```python3
num = 5

if num%2 == 0:
    print("It is Even")
else:
    print("It is odd")
```

**Output**

```bash
It is odd
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

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

You could also get a list of all reserved keywords in Python.

**Code/Output**

```python3
import keyword

print(keyword.kwlist)
>>> ['False', 'None', 'True', '__peg_parser__', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

#### Python Identifiers

Identifiers are **opposite of reserved keywords**. They are just names that users can choose to name their variables, functions and classes.

##### Rules to remember while writing identifiers

* Can be a combination of lowercase and uppercase letters(`A to Z`), numbers(`0 to 9`) and underscore(`_`). 
   
  **Valid Examples** - `x`, `my_list`, `str123`

* Cannot start with a number.
   
  **Invalid example** - `1name`
   
  **Valid Example** - `name1`
   
* Keywords cannot be used as identifiers

  ```python3
  for = 1
  >>> SyntaxError: invalid syntax
  ```
   
* Special symbols like **!, @, #, $, %** etc. cannot be used

  ```python3
  x@ = 1
  >>> SyntaxError: invalid syntax
  ```

#### Final Suggestions

1. Python is case sensitive. This means `X` and `x` are not the same.
2. Use variable, function and class names that is descriptive of it's functionality.   
3. Use **snake case** to write long variables. Example - `my_int_only_list`.
