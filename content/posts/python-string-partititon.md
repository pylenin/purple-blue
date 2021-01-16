---
title: "Python String partition() Method"
description: "Learn to use partition() method on Python strings"
date: 2021-01-14T11:33:30+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `partition()` method

The `partition()` method in Python searches for the **first occurence of the specified string** and splits the string into a tuple containing three elements.

1. The first element  - Contains the part before the specified string.
2. The second element - Contains the specified string.
3. The third element - Contains the part after the string.

##### Syntax of `partition()` method

```bash
string.partition(value)

value: The substring to partition on
```

##### Example 1

**Code**

```python3
str1 = "Pylenin loves Python"
print(str1.partition("loves"))
```

**Output**

```bash
('Pylenin ', 'loves', ' Python')
```

##### Example 2 - When the substring doesn't exist

**Code**

```python3
str1 = "Pylenin loves Python"
print(str1.partition("cake"))
```

**Output**

```bash
('Pylenin loves Python', '', '')
```

As you can see, it returned the entire string as first element of the tuple and the last 2 elements are empty strings. The `partition()` method doesn't throw any error if it is unable to find the substring.

##### Example 3 - When the substring occurs multiple times

**Code**

```python3
str1 = "Pylenin loves Python and Python loves Pylenin"
print(str1.partition("Python"))
```

**Output**

```bash
('Pylenin loves ', 'Python', ' and Python loves Pylenin')
```

The `partition()` method separates at the first occurence of the provided substring.

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
