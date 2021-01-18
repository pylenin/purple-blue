---
title: "Python String center() Method"
description: "Learn what center() method does to Python strings"
date: 2021-01-13T09:16:00+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

The `center()` method in Python will **align the string to the center**, using a specified character(by default, it is space) as the fill character.

#### Syntax of `center()` method

```bash
string.center(length, character)

length - The length of the required string(Required)
character - The fill character for the missing space(Optional).
            By default is space.
```

##### Example 1

**Code**

```python3
str1 = "Pylenin"

str2 = str1.center(10)

print(str2)

print(f"Str1 length was {len(str1)}")
print(f"Str2 length is {len(str2)}")
```

**Output**

```bash
 Pylenin  
Str1 length was 7
Str2 length is 10
```
The length of the new string has become 10. The increase in length was due to addition of space characters to the original string.

##### Example 2

**Code**

```python3
str1 = "Pylenin"

str2 = str1.center(10, '*')

print(str2)

print(f"Str1 length was {len(str1)}")
print(f"Str2 length is {len(str2)}")
```

**Output**

```bash
*Pylenin**
Str1 length was 7
Str2 length is 10
```

By providing the optional `character` parameter, you can see how the new string has changed.

##### Example 3 - Printing Pyramid Patterns in Python

You can do many exciting things with `center()` method in Python. For example - Constructing a Pyramid.

**Code**

```python3
for i in range(1, 10, 2):
    x = i*'*'
    print(x.center(10))
```

**Output**

```bash
    *     
   ***    
  *****   
 *******  
********* 
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

