---
title: "Python String isnumeric() Method"
description: "Learn to use isnumeric() method on Python strings"
date: 2021-01-15T09:12:45+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `isnumeric()` method

The `isnumeric()` method in Python returns `True`, if all characters are numeric (0-9).

##### What are numerical characters in Python?

The following characters are considered numerical in Python

1. Decimal characters (like: 0, 1, 2 etc.) 
2. subscript and superscript 
3. Characters having Unicode numeric value property 
   (e.g. fractions, roman numerals, currency numerators)

**Note**:-

1. Negative integers like `-1` are not numerical as the `-` symbol is not numeric.
2. Floats like `2.3` are not numerical as `.` is not a numeric character.

##### Syntax of `isnumeric()` method

```bash
string.isnumeric()

Returns True or False
``` 

##### Example

**Code/Output**

```
# string with integers
s = '1992'
print(s.isnumeric())
>>> True

# negative integer
s = '-1992'
print(s.isnumeric())
>>> False

# Unicode
s = '\u0660'
print(s.isnumeric())
>>> True

# alphanumeric
s='pylenin1992'
print(s.isnumeric())
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
