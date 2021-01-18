---
title: "Python String isprintable() Method"
description: "Learn to use isprintable() method on Python strings"
date: 2021-01-15T09:12:45+05:30
draft: true
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `isprintable()` method

The `isprintable()` method in Python returns `True`, if all characters are printable. Carriage return (`\r`), line feed (`\n`) and tabs(`\t`) are examples of non printable characters in Python.

##### Syntax of `isprintable()` method

```bash
string.isprintable()

Returns True or False
```

##### Example 

**Code/Output**

```python3
str1 = "\r"
print(str1.isprintable())
>>> False

str2 = "\n"
print(str2.isprintable())
>>> False

str3 = "\t"
print(str3.isprintable())
>>> False

str4 = "https://youtube.com/pylenin"
print(str4.isprintable())
>>> True
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
