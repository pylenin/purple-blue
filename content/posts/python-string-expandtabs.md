---
title: "Python String expandtabs() Method"
description: "Learn to use expandtabs() method with Python strings"
date: 2021-01-13T11:02:49+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

The `expandtabs()` method in Python, sets the tabsize to the specified number of characters for every occurence of `\t`. **Default is 8**.

#### Syntax of `expandtabs()` method

```bash
string.expandtabs(tabsize)

tabsize: A positive integer specifying the tabsize. 
         Default tabsize is 8
```

Tab positions occur every tabsize character. Default is 8, giving tab positions at columns 0, 8, 16 and so on.

#### Example 

**Code**

```python3
str1 = "Pylenin\tloves\tPython"
print(str1)

# Using default value
str2 = str1.expandtabs(8)
print(str2)

str3 = str1.expandtabs(10)
print(str3)
```

**Output**

```bash
Pylenin	loves	Python
Pylenin loves   Python
Pylenin             loves               Python
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
