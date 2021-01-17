---
title: "Python String startswith() Method"
description: "Learn to use startswith() method on Python strings"
date: 2021-01-15T09:15:41+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `startswith()` method

The `startswith()` method in Python returns True if the string starts with the specified value, otherwise it returns False.
**The `startswith()` method is not case sensitive.**

##### Syntax of `startswith()` method

```bash
string.startswith(value, start, end)

value:	The substring to search for(Required)
start:	The integer position to start the search. Default is 0.(Optional)
end:	The integer position to end the search. Default is the end of the string.(Optional)
```

##### Example 1

**Code**

```python3
str1 = "Pylenin loves Python"

print(str1.startswith("Pylenin"))
```

**Output**

```bash
True
```

The string does starts with substring `Pylenin`.

##### Example 2 - Check for case sensitivity
**Code**

```python3
str1 = "Pylenin loves Python"

print(str1.startswith("pylenin"))
```

**Output**

```bash
False
```

##### Example 3 - Search for a different string.

**Code**

```python3
str1 = "Pylenin loves Python"

print(str1.startswith("Python"))
```

**Output**

```bash
False
```

##### Example 4 - Check if string `s1` starts with substring `s2` within a specific position

**Code**

```python3
s1 = 'I like reading Pylenin blogs on Python'
s2 = 'Pylenin'

# Search between position 15 and 30
print(s1.startswith(s2, 15, 30))
```
**Output**

```bash
True
```

As you can see, the substring `Python` occurs at position 15. Hence, the `startswith()` method returns True when searched between position 15 and 30.

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
