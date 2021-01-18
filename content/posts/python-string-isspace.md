---
title: "Python String isspace() Method"
description: "Learn to use isspace() method on Python strings"
date: 2021-01-15T09:13:06+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `isspace()` method

The `isspace()` method in Python returns `True` if all characters in your string are whitespace.
If the string contains one or more non-white space characters, it returns `False`.
 
Each of the following characters are considered whitespace.

1. ` ` - Empty space
2. `\n` - Newline
3. `\r` - Carriage return
4. `\f` - feed
5. `\t` - Horizontal tab
6. `\v` - Vertical Tab

##### Syntax of `isspace()` method

```bash
string.isspace()

Returns True or False
``` 

##### Example

**Code/Output**

```python3
s = " "
print(s.isspace())
>>> True

s = "\n"
print(s.isspace())
>>> True

s = "\r"
print(s.isspace())
>>> True

s = "\t"
print(s.isspace())
>>> True

s = "\v"
print(s.isspace())
>>> True

s = "\f"
print(s.isspace())
>>> True

s = "\n \r \f"
print(s.isspace())
>>> True

s = "Pylenin"
print(s.isspace())
>>> False
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


