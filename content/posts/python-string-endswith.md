---
title: "Python String endswith() Method"
description: "Learn to use endswith() method with Python strings"
date: 2021-01-13T10:36:16+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

The `endswith()` method in Python returns `True` if the string ends with the specified value, otherwise, returns `False`.
**It is not case sensitive.**

#### Syntax of `endswith()` method

```bash
string.endswith(value, start, end)

value: Value to check if the string endswith(Required)
start: The integer position to start the search. Default is 0.(Optional)
end:   The integer position to end the search. Default is the end of the string.(Optional)
```

##### Example 1

**Code**

```python3
str1 = "Pylenin makes videos on Python"

print(str1.endswith('Python'))
print(str1.endswith('videos'))
```

**Output**

```bash
True
False
```

##### Example 2 - Check for case sensitivity

**Code**

```python3
str1 = "Pylenin makes videos on Python"

print(str1.endswith('python'))
```

**Output**

```bash
False
```

##### Example 3 - Check within specified positions of a string

**Code**

```python3
str1 = "Pylenin makes videos on Python"

# Check between position 5 and 10
print(str1.endswith('Python', 5, 10))

print(f"It occurs at position - {str1.find('Python')}")
```

**Output**

```bash
False
It occurs at position - 24
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
