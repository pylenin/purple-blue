---
title: "Check if a Substring is Present in a Given String in Python"
description: "Check if a Substring is Present in a Given String in Python"
date: 2021-01-10T09:59:53+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

Given two strings, check if `s1` is present in `s2`.

#### Method 1 - Using *in* and *not in* keywords

**Code**

```python3
s2 = "I like Pylenin"
s1 = 'like'

print(s1 in s2)
print(s1 not in s2)
```

**Output**

```bash
True
False
```

#### Method 2 - Python String find() Method

The `find()` method in Python, finds the first occurrence of a specified value in a given string. It returns the index where the substring `s1` occurs.
It returns **-1** if the value is not found.

The `find()` method is similar to the `index()` method. 
Only difference - `index()` method raises an exception if the value is not found.

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

#### Method 3 - Python String count() Method

The `count()` method returns the number of times a substring `s1` appears in the string `s2`.

**Syntax**
```bash
string.count(value, start, end)

value:	The substring to search for(required)
start:	The integer position to start the search. Default is 0.(Optional)
end:	The integer position to end the search. Default is the end of the string.(Optional)
```

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

Let's search for a non-existing string.

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

Let's now search a substring `s1` in a specific portion of string `s2`.

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

#### Related Articles
1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
4. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
5. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
6. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
7. [Python String Formatting - The Definitive Guide](https://www.pylenin.com/blogs/python-string-formatting/)