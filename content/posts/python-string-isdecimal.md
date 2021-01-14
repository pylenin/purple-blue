---
title: "Python String isdecimal() Method"
description: "Learn to use isdecimal() method on Python strings"
date: 2021-01-14T11:33:30+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `isdecimal()` method

The `isdecimal()` method in Python returns **True** if all the characters in the string are **decimal characters**. For empty strings, it returns **False**.

##### What are Decimal characters?

Any character that can be used to form a number in base 10, is a decimal character.

Example:-
1. All numbers from 0 to 9
2. All numbers from 0 to 9 in various languages like Arabic Indic, Devnagri etc.

You can find all the decimal characters in [Unicode General Category Nd](https://www.compart.com/en/unicode/category/Nd).

##### Syntax of `isdecimal()` method

```bash
string.isdecimal()

Returns True or False
```

##### Example

**Code**

```python3
s = "1992"
print(s.isdecimal())

# Floating point number
s = "1992.10"
print(s.isdecimal())

# contains alphabets
s = "Pylenin1992"
print(s.isdecimal())

# contains alphabets and spaces
s = "Pylenin loves Python"
print(s.isdecimal())

# Empty string
s = ''
print(s.isdecimal())

# superscripts
s = '1992\u00B2'
print(s)
print(s.isdecimal())

# fractions
s = '\u00BD'
print(s)
print(s.isdecimal())
```

**Output**

```bash
True
False
False
False
False

# superscript result
1992²
False

# fraction result
½
False
```

##### Difference between `isdigit()` and `isdecimal()`

Difference between the above methods crop up with various unicode characters, such as **superscripts**:

```python3
# superscripts
s = '2345\u00B2'
print(s)

print(s.isdecimal())
print(s.isdigit())
```

**Output**

```bash
2345²
False #isdecimal()
True #isdigit()
```

Check out other [commonly used Python string methods](https://www.pylenin.com/blogs/common-python-string-methods).

#### Related Articles

1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
4. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
5. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
6. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
7. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
8. [Python String Formatting - The Definitive Guide](https://www.pylenin.com/blogs/python-string-formatting/)
