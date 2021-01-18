---
title: "Python String isidentifier() Method"
description: "Learn to use isidentifier() method on Python strings"
date: 2021-01-15T09:12:23+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `isidentifier()` method

The `isidentifier()` method in Python returns `True`, if the string is a valid identifier.

##### What is a valid identifier in Python?

1. Should contain alphanumeric characters - `(a-z)` and `(0-9)`.
2. Can have underscores (`_`).
3. Shouldn't contain spaces.
4. Cannot start with a number.

##### Syntax of `isidentifier()` method

```bash
string.isidentifier()

Returns True or False
```

##### Example 1

**Code/Output**

```python3
# only alphabets
str1 = "Pylenin"
print(str1.isidentifier())
>>> True

# Only numbers
str2 = "1992"
print(str2.isidentifier())
>>> False

# alphanumeric characters
str3 = "Pylenin1992"
print(str3.isidentifier())
>>> True

# alphanumeric characters starting with numbers
str4 = "1992Pylenin"
print(str4.isidentifier())

# special characters like '@'
str5 = "pylenin1992@gmail.com"
print(str5.isidentifier())
>>> False

# sentences
str6 = "Pylenin loves Python"
print(str6.isidentifier())
>>> False
```

As you can see, the `isidentifier()` method in Python returns `False` even for numerical strings.

##### Example 2 - Working with underscores

**Code/Output**

```python3
# underscores
str1 = "_"
print(str1.isidentifier())
>>> True

# alphabets with underscores
str2 = "Pylenin_loves_Python"
print(str2.isidentifier())
>>> True

# numbers with underscores
str3 = "1234_5678_90"
print(str3.isidentifier())
>>> False

# alphanumeric with underscores
str4 = "Pylenin_1992"
print(str4.isidentifier())
>>> True
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
