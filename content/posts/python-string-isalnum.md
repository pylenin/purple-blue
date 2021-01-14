---
title: "Python String isalnum() Method"
description: "Learn to use isalnum() method on Python strings"
date: 2021-01-14T10:32:47+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `isalnum()` method

The `isalnum()` method in Python checks if all characters in the string are **alphanumeric**.

**Alphanumeric characters** - Alphabet letters (a-z) and numbers (0-9)

##### Syntax of `isalnum()` method

```bash
string.isalnum()

Returns True or False
```

##### Example 1

**Code**

```python3
s1 = "Pylenin1992"

print(s1.isalnum())
```

**Output**

```bash
True
```

##### Example 2 - Check for a sentence

**Code**

```python3
s1 = "Pylenin was born in 1992"

print(s1.isalnum())
```

**Output**

```bash
False
```

##### Example 3 - Check for special characters

**Code**

```python3
s1 = "pylenin1992@gmail.com"

print(s1.isalnum())
```

**Output**

```bash
False
```

As you can see, `@` is not an alphanumeric character.

Let's check for random characters.


**Code**

```python3
s1 = "!#%&?"

print(s1.isalnum())
```

**Output**

```bash
False
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
