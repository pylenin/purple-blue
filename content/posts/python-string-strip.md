---
title: "Python String strip() Method"
description: "Learn to use strip() method on Python strings"
date: 2021-01-15T09:15:49+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `strip()` method

The `strip()` method in Python, 
returns a new string by removing(stripping)
 all the characters from the left and right that are 
 passed as string argument. **If no arguments are passed, it removes the leading and trailing whitespaces.**

##### Syntax of `strip()` method

```bash
string.strip()

Returns a new string
```

##### Example

**Code/Output**

```python3
x = "  Pylenin loves Python   "
print(x.strip())
>>> Pylenin loves Python

x = "*Pylenin loves Python*"
print(x.strip('*'))
>>> Pylenin loves Python

x = "*@Pylenin loves Python@*"
print(x.strip('*@'))
>>> Pylenin loves Python
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
