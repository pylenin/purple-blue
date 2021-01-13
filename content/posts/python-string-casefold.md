---
title: "Python String casefold() Method"
description: "Learn what casefold() method does in Python strings"
date: 2021-01-13T08:56:47+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

The `casefold()` method in Python returns a case folded copy of a string where all characters are lowercase.

**Code**
```python3
str1 = "Pylenin writes about Python."

print(str1.casefold())
```

**Output** 
```bash
pylenin writes about python.
```

The `casefold()` method is similar to `lower()` method. However, it is more aggresive.

`casefold()` method is best suited for **caseless matching**. 

#### What is Caseless Matching?

Caseless Matching is a way of erasing case differences in strings by mapping characters of different cases to a single form.

For example, the German lowercase letter `ﬂ` is equivalent to `ss`.

Let's look at the example below.

**Code**
```python3
str1 = "Pylenin has a nice dress."
str2 = "Pylenin has a nice dreﬂ."

# Experiment with lower()
print(str1.lower() == str2.lower())

# Experiment with casefold
print(str1.casefold() == str2.casefold())
```

**Output** 
```bash
False
True
```

While the `lower()` method was unable to convert the german character, `casefold()` method converted it successfully and hence showed that both the strings are the same.

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

