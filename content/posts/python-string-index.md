---
title: "Python String index() Method"
description: "Learn to use index() method on Python strings"
date: 2021-01-14T10:02:11+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Difference between `index()` and `find()` in Python

Similar to [find()](https://www.pylenin.com/blogs/python-string-find/) method in Python, the `index()` method finds the first occurence of a certain value.

If the value is not found, it raises a `ValueError` exception. The `find()` method in Python on the other hand, returns **-1**, if the value is not found.

**The `index()` method is not case sensitive.**

##### Syntax of `index()` method

```bash
string.index(value, start end)

value:	The value to search for(Required)
start:	The integer position to start the search. Default is 0.(Optional)
end:	The integer position to end the search. Default is the end of the string.(Optional)
```

##### Example 1

**Code**

```python3
str1 = "Pylenin loves Python"

print(str1.index("Python"))
```

**Output**

```bash
14
```

The substring `Python` occurs first time at **position 14** in the string.

##### Example 2 - Check for case sensitivity
**Code**

```python3
str1 = "Pylenin loves Python"

print(str1.index("python"))
```

**Output**

```bash
ValueError: substring not found
```

##### Example 3 - Search for a non-existing string.

**Code**

```python3
str1 = "Pylenin loves Python"

print(str1.index("Apples"))
```

**Output**

```bash
ValueError: substring not found
```

##### Example 4 - Search a substring `s1` in a specific portion of string `s2`.

**Code**

```python3
s2 = 'I like reading Pylenin blogs on Python'
s1 = 'Python'

# Search between position 10 and 20
try:
    print(s2.index(s1, 10, 20))
except Exception as e:
    print(e.__class__, e)

print(f"'{s1}' occurs at index {s2.index(s1)}")
```
**Output**

```bash
<class 'ValueError'> substring not found
'Python' occurs at index 32
```

As you can see, the substring `Python` occurs at index 32, but we are searching within the index 10 and 20.

Because, we are using a `try-except` block, `ValueError` exception is not being raised. Learn more about [Python Exceptions and ways to handle them](https://www.pylenin.com/blogs/python-try-except-else-finally/).

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
