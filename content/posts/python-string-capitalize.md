---
title: "Python String capitalize() Method"
description: "Learn what capitalize() method does in Python strings"
date: 2021-01-13T07:17:38+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

The `capitalize()` method in Python returns a copy of the string with only the **first character capitalized**.

**Code**
```python3
str1 = "pylenin writes about python."

print(str1.capitalize())
```

**Output**
```bash
Pylenin writes about python.
```

If you want to capitalize the first letter of every word, perform something like this.

**Code**
```python3
str1 = "pylenin writes about python."

str_list = str1.split(" ")

new_string = ' '.join(x.capitalize() for x in str_list)
print(new_string)
```

**Output** 
```bash
Pylenin Writes About Python.
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

