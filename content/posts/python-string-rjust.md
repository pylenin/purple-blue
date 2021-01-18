---
title: "Python String rjust() Method"
description: "Learn to use rjust() method on Python strings"
date: 2021-01-14T11:33:30+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String rjust() method

The `rjust()` method in Python right aligns the string, using a specific number of characters (space is used as default) as the provided fill character.

##### Syntax of `rjust()` method

```bash
string.rjust(length, fill_character)

length:         The length of the output string(Required).
fill_character: A character to fill the missing space 
                to the left of the string(Optional).
                Default is space.     
```

##### Example 1

**Code**

```python3
x = "Pylenin"
y = x.rjust(20)
print(len(y))
print(y)
```

**Output**

```bash
20
             Pylenin        
```

As you can see, the length of the new string is **20 characters long**.

##### Example 2 - Using a different fill character

**Code**

```python3
x = "Pylenin"
y = x.rjust(20, "*")
print(len(y))
print(y)
```

**Output**

```bash
20
*************Pylenin     
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


