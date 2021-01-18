---
title: "Python String zfill() Method"
description: "Learn to use zfill() method on Python strings"
date: 2021-01-15T09:13:58+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `zfill()` method

The `zfill()` method in Python concatenates zeros (0) at the beginning of the string, until it reaches the specified length.

If the value of the `len` parameter is less than the length of the original string, no filling is done.


##### Syntax of `zfill()` method

```bash
string.zfill(len)

len: The length of the new string after filling(Required)
```

##### Example 1

**Code**

```python3
a = "Pylenin"
b = "Pylenin loves Python"
c = "@pylenin"

print(a.zfill(10))
print(b.zfill(10))
print(c.zfill(10))
```

**Output**

```bash
000Pylenin
Pylenin loves Python
00@pylenin
```

##### Example 2 - Working with sign prefix (`+` and `-`)

If your strings are prefixed with signs like `+` and `-`, then the filling happens after the sign.

**Code**

```python3
a = "+Pylenin"
b = "-Pylenin"

print(a.zfill(10))
print(b.zfill(10))
```

**Output**

```bash
+00Pylenin
-00Pylenin
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
