---
title: "Python String count() Method"
description: "Learn what count() method does to Python strings"
date: 2021-01-13T09:50:32+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

The `count()` method returns the number of times a substring `s1` appears in the string `s2`. **It is not case sensitive.**

#### Syntax of `count()` method

```bash
string.count(value, start, end)

value:	The substring to search for(Required)
start:	The integer position to start the search. Default is 0.(Optional)
end:	The integer position to end the search. Default is the end of the string.(Optional)
```

##### Example 1
**Code**

```python3
s2 = "I like Pylenin"
s1 = 'like'

if s2.count(s1) > 0:
    print(f"'{s1}' exists in '{s2}'")
```

**Output**

```bash
'like' exists in 'I like Pylenin'
```

##### Example 2 - Check for case sensitivity
**Code**

```python3
s2 = "I like Pylenin"
s1 = 'Like'

if s2.count(s1) > 0:
    print(f"'{s1}' exists in '{s2}'")
else:
    print(f"'{s1}' does not exist in '{s2}'")
```

**Output**

```bash
'Like' does not exist in 'I like Pylenin'
```

##### Example 3 - Search for a non-existing string.

**Code**

```python3
s2 = "I like Pylenin"
s1 = 'Python'

if s2.count(s1) > 0:
    print(f"'{s1}' exists in '{s2}'")
else:
    print(f"'{s1}' doesn't exist in '{s2}'")
```

**Output**

```bash
'Python' doesn't exist in 'I like Pylenin'
```

##### Example 4 - Search a substring `s1` in a specific portion of string `s2`.

**Code**

```python3
s2 = "I like reading Pylenin blogs on Python"
s1 = 'Python'

# Search between position 10 and 20
if s2.count(s1, 10, 20) > 0:
    print(f"'{s1}' exists in '{s2}'")
else:
    print(f"'{s1}' doesn't exist in '{s2}'")

print(s2.find(s1))
```
**Output**

```bash
'Python' doesn't exist in 'I like reading Pylenin blogs on Python'
32
```

As you can see, the substring `Python` doesn't occur between the positions 10 and 20. The `find()` method shows that **it occurs at position 32**.

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

