---
title: "Python String isdigit() Method"
description: "Learn to use isdigit() method on Python strings"
date: 2021-01-14T11:33:30+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `isdigit()` method

The `isdigit()` method in Python, returns True if all characters are numerical digits. **Exponents are also considered digits.**

##### Syntax of `isdigit()` method

```bash
string.isdigit()

Returns True or False
```

##### Example 

**Code/Output**

```python3
s = "1992"
print(s.isdigit())
>>> True

# Floating point number
s = "1992.10"
print(s.isdigit())
>>> False

# contains alphabets
s = "Pylenin1992"
print(s.isdigit())
>>> False

# contains alphabets and spaces
s = "Pylenin loves Python"
print(s.isdigit())
>>> False

# Empty string
s = ''
print(s.isdigit())
>>> False

# superscripts
s = '1992\u00B2'
print(s)
print(s.isdigit())
>>> 1992²
>>> True

# fractions
s = '\u00BD'
print(s)
print(s.isdigit())
>>> ½
>>> False
```

As you can see, **fractions don't qualify as digits.**

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
