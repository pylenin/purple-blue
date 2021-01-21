---
title: "Python program to add first and last n characters in a string"
description: "Learn to concatenate the first and last n characters of a string in Python 3"
date: 2021-01-21T06:57:35+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python String Examples']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Objective

Write a Python program to get a string made of the first n and the last n characters from a given string. 
If the string length is less than n, return an empty string.

```bash
# Example 1
n = 2
str = "Pylenin"
Output ==> "Pyin"

# Example 2
n=4
str = "Pylenin loves Python"
Output ==> "Pylethon"

# Example 3
n=4
str = "Blog"
Output ==> "BlogBlog"

# Example 4
n=5
str = "Blog"
Output = ""
```

#### Solution

**Code**

```python3
user_input = input("Provide a string ==> ")
n = int(input("Provide the value of n ==> "))

if len(user_input) < n:
    print("")
else:
    print(user_input[:n] + user_input[(-1*n):])
```

**Output**

```bash
# Example 1
Provide a string ==> Pylenin
Provide the value of n ==> 2
Pyin

# Example 2
Provide a string ==> Pylenin loves Python
Provide the value of n ==> 4
Pylethon

# Example 3
Provide a string ==> Blog
Provide the value of n ==> 4
BlogBlog

# Example 4
Provide a string ==> Blog
Provide the value of n ==> 5

```

#### Related Articles

1. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
2. [How input() function works in Python](https://www.pylenin.com/blogs/how-input-works-python/)
3. [Common Python String Methods](https://www.pylenin.com/blogs/common-python-string-methods/)
