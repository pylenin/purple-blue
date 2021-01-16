---
title: "Python String islower() Method"
description: "Learn to use islower() method on Python strings"
date: 2021-01-15T09:12:34+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `islower()` method

The `islower()` method in Python returns `True`, if all characters are lowercase.

**It doesn't take numbers, symbols and spaces into account.**

##### Syntax of `islower()` method

```bash
string.islower()

Returns True or False
``` 

##### Example

**Code/Output**

```python3
# all lowercase alphabets
s = "pylenin"
print(s.islower())
>>> True

# lowercase alphabets with numbers
s = "pylenin1992"
print(s.islower())
>>> True

# lowercase alphabets with spaces
s = "pylenin loves python"
print(s.islower())
>>> True

# lowercase alphabets with special symbols
s = "https://www.youtube.com/pylenin"
print(s.islower())
>>> True

# string containing uppercase characters
s = "Pylenin loves python"
print(s.islower())
>>> False
```

**The `islower()` method in Python doesn't make changes to the original string.** It actually returns a new string.

You can confirm this by using the `id()` function in Python. It is a built-in function in Python that **returns the unique identity of an object.**

**Code/Output**

```python3
s1 = "pylenin"
s2 = "pylenin"

print(id(s1) == id(s2))
>>> True

print(id(s1) == id(s1.islower()))
>>> False

print(id(s2) == id(s2.islower()))
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
