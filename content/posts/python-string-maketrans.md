---
title: "Python String maketrans() Method"
description: "Learn to use maketrans() method on Python strings"
date: 2021-01-14T11:33:30+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `maketrans()` method

The `maketrans()` method in Python 
is used to specify the list of characters that need to be replaced or deleted in the whole string.

It returns a translation table that can be used with the `translate()` method.

##### Syntax of `maketrans()` method

```bash
string.maketrans(str1, str2, str3)

str1 : Specifies the list of characters that need to be replaced.
str2 : Specifies the list of characters with which the characters need to be replaced.
str3 : Specifies the list of characters that need to be deleted.
```

##### Example 1

**Code**

```python3
str1 = "Pylenin"

table = str1.maketrans("n", "m")

print(str1.translate(table))
```

**Output**

```bash
Pylemim
```

As you can see, all instances of `n` were replaced with `m`.

##### Example 2 - Using a dictionary with `maketrans()`

**Code**

```python3
mapping_dict = {"n":"m"}
str1 = "Pylenin"

table = str1.maketrans(mapping_dict)

print(str1.translate(table))
```

**Output**

```bash
Pylemim
```

##### Example 3 - How to remove characters with `maketrans()`

**Code**

```python3
str1 = "Pylenin?"

table = str1.maketrans("","","?")

print(str1.translate(table))
```

**Output**

```bash
Pylenin
```

Since the 3rd argument is used to pass in the characters to be removed, the first 2 arguments are being left empty above.

We can achieve the same result by passing in a dictionary.

**Code**
```python3
mapping_dict= {"?":None}
str1 = "Pylenin?"

table = str1.maketrans(mapping_dict)

print(str1.translate(table))
```

**Output**

```bash
Pylenin
```

Just use `None` as values for characters you want removed from your string.

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
