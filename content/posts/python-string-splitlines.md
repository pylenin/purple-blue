---
title: "Python String splitlines() Method"
description: "Learn to use splitlines() method on Python strings"
date: 2021-01-15T09:15:30+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `splitlines()` method

The `splitlines()` method in Python splits the string at line breaks and returns a list of lines in the string.

The following symbols are considered as line breaks for `splitlines()`.

1. `\n` - Line Feed
2. `\r` - Carriage Return
3. `\r\n` - Carriage Return and Line Feed
4. `\v` - Line Tabulation
5. `\f`- Form Feed

##### Syntax of `splitlines()` method

```bash
string.splitlines(keepends)

keepends: Specifies if the line breaks 
          should be included - True or False(Optional)
          Default value is False. 
```

##### Example

**Code/Output**

```python3
str1 = "Pylenin loves Python.\nHe also likes Apples."
print(str1.splitlines())
>>> ['Pylenin loves Python.', 'He also likes Apples.']

str1 = "Pylenin loves Python.\nHe also likes Apples."
print(str1.splitlines(True))
>>> ['Pylenin loves Python.\n', 'He also likes Apples.']

str1 = "Pylenin\rPython\nApples\r\nBlogs\vYoutube\f"
print(str1.splitlines())
>>> ['Pylenin', 'Python', 'Apples', 'Blogs', 'Youtube']

str1 = "Pylenin\rPython\nApples\r\nBlogs\vYoutube\f"
print(str1.splitlines(True))
>>> ['Pylenin\r', 'Python\n', 'Apples\r\n', 'Blogs\x0b', 'Youtube\x0c']
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
