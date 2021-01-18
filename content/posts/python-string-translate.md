---
title: "Python String translate() Method"
description: "Learn to use translate() method on Python strings"
date: 2021-01-14T11:33:30+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `translate()` method

The string `translate()` method in Python returns a string 
where each character is mapped to its corresponding character in the translation table.

The translation table is created by using the [maketrans()](https://www.pylenin.com/blogs/python-string-maketrans/) method.

##### Syntax of `translate()` method

```bash
string.translate(table)

table: a translation table containing the 
       mapping between characters.
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

##### Example 2 - Mapping table with a dictionary

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

##### Example 3 - Removing characters

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
