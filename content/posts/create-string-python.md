---
title: "How to create a string in Python?"
description: "Learn to create and use Python strings"
date: 2021-01-09T12:38:43+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

#### What are strings in Python?

Strings are amongst the most popular data types in Python. A string can be defined as a sequence of characters. 

Strings can be created by enclosing characters inside a single quote, double-quotes and triple quotes.

**Code**

```python3
# Single Quotes
my_string = 'Pylenin'
print(my_string)

# Double Quotes
my_string = "Pylenin"
print(my_string)

# Triple Quotes
# can be extended over multiple lines
my_string = """Check out Pylenin
               for Python related blogs and videos"""
print(my_string)
```


**Output**

```bash
Pylenin
Pylenin
Check out Pylenin
               for Python related blogs and videos
```

As you can see in the code above, we are assigning a string to a variable. It is done with **the variable name followed by an equal sign and the string**.

> Unless necessary, **try not to use triple quotes for strings**. It is generally used for writing docstrings in your Python code, which acts like a documentation.

#### Related Articles

1. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
2. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
3. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)