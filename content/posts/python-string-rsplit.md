---
title: "Python String rsplit() Method"
description: "Learn to use rsplit() method on Python strings"
date: 2021-01-14T11:33:30+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `rsplit()` method

The `rsplit()` method in Python splits a string into a list, starting from the right.

If no `maxsplit` parameter is specified, this method will return the same as the [split()](https://www.pylenin.com/blogs/python-string-split) method.

When `maxsplit` is specified, the list will contain the specified number of elements plus one.

##### Syntax of `rsplit()` method

```bash
string.rsplit(separator, maxsplit)

separator: Specifies the separator to 
           use when splitting the string(Optional). 
           By default any whitespace is a separator
maxsplit:  Specifies how many splits to do(Optional). 
           Default value is -1, which is "all occurrences"
```

##### Example

**Code/Output**

```python3
str1 = "Pylenin loves Python"
print(str1.rsplit())
>>> ['Pylenin', 'loves', 'Python']

# Using the maxsplit parameter
str1 = "Pylenin loves Python"
print(str1.rsplit(" ", 1))
>>> ['Pylenin loves', 'Python']

str1 = "Pylenin loves Python"
print(str1.rsplit("loves", 1))
>>> ['Pylenin ', ' Python']
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

