---
title: "Python String replace() Method"
description: "Learn to use replace() method on Python strings"
date: 2021-01-15T09:14:34+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `replace()` method

The `replace()` method in Python replaces a specified substring with another substring.

**It's not case sensitive.**

##### Syntax of `replace()` method

```bash
string.replace(old_value, new_value, count)

old_value: The substring to be replaced(required)
new_value: The substring to replace with(required)
count: A number specifying the number of occurences 
       of old_value to replace. (Optional)
       If nothing is mentioned, all occurences are replaced.
```

##### Example 1

**Code/Output**

```python3
str1 = "Pylenin loves Python"
print(str1.replace("Python","Apples"))
>>> Pylenin loves Apples

# replacing a non-existing substring
str1 = "Pylenin loves Python"
print(str1.replace("mangoes","Apples"))
>>> Pylenin loves Python

# check for case sensitivity
str1 = "Pylenin loves Python"
print(str1.replace("python","Apples"))
>>> Pylenin loves Python
```

##### Example 2 - Changing multiple occurences of a substring

**Code/Output**

```python3
str1 = "Pylenin loves Python and Python loves Pylenin"
print(str1.replace("Python","Apples", 1))
>>> Pylenin loves Apples and Python loves Pylenin
```

As you see, only the first occurence of `Python` is changed to `Apples`.

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

