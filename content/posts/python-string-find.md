---
title: "Python String find() Method"
description: "Learn to use find() method on Python strings"
date: 2021-01-13T19:31:38+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

The `find()` method in Python, finds the first occurrence of a specified value in a given string. It returns the index where the substring `s1` occurs.
It returns **-1** if the value is not found.

The `find()` method is similar to the `index()` method. 
Only difference - `index()` method raises an exception if the value is not found.

##### Syntax of `find()` method

```bash
string.find(value, start, end)

value:	The value to search for(Required)
start:	The integer position to start the search. Default is 0.(Optional)
end:	The integer position to end the search. Default is the end of the string.(Optional)
```

##### Example 1

**Code**

```python3
s2 = "I like Pylenin"
s1 = 'like'

print(s2.find(s1))
```

**Output**

```bash
2
```

The above result tells us that the `like` substring first occurs at **2nd index**.

##### Example 2

Let's check for another substring.

**Code**

```python3
s2 = "I like Pylenin"
s1 = 'Python'

print(s2.find(s1))
```

**Output**

```bash
-1
```

The above result tells us that the substring `Python` doesn't exist in `s1`.

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

