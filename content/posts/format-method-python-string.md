---
title: "Python String format() method"
description: "Learn to perform string formatting with format() method in Python"
date: 2021-01-11T00:30:30+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string formatting']
categories_weight: 11
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

#### Python String format() method

The `format()` method in Python, formats the specified value(s) and inserts them inside the string's replacement fields and returns the formatted string.

The replacement fields for the values is defined using curly braces `{}`.

**Code**

```python3
print("My name is {}. I love {}".format("Pylenin", "Python"))
```

**Output**

```bash
My name is Pylenin. I love Python
```

##### How does it work?

When placeholders `{}` in the string are empty, 
Python will replace the values passed through `str.format()` **in order**.

Check out the following example.

**Code**

```python3
# Method 1
print("My name is {}. I love {}".format("Pylenin", "Python"))
print("My name is {}. I love {}".format("Python", "Pylenin"))

```

**Output**

```bash
My name is Pylenin. I love Python
My name is Python. I love Pylenin
```

#### Formatters with Positional Arguments

Similar to [indexing in strings](https://www.pylenin.com/blogs/access-characters-in-string/), the values present inside `string.format()` method also start with index 0 and increments by 1 with every value.
These index numbers can be passed into the curly braces(replacement fields) serving as the placeholders in the original string. 

Let's look at the following example.

**Code**

```python3
print("My name is {0}. I love {1}".format("Pylenin", "Python"))
print("My name is {1}. I love {0}".format("Pylenin", "Python"))
```

**Output**

```bash
My name is Pylenin. I love Python
My name is Python. I love Pylenin
```

**Beware** - If you try to escape the index 0 or start with a different number, Python will throw you an `IndexError`.

**Code**

```python3
print("My name is {1}. I love {2}".format("Pylenin", "Python"))
```

**Output**

```bash
Traceback (most recent call last):
  File "some_file_location", line 2, in <module>
    print("My name is {1}. I love {2}".format("Pylenin", "Python"))
IndexError: Replacement index 2 out of range for positional args tuple
```

It basically means, you are trying to access the **2nd index** from the values within the `string.format()` method and it doesn't exist.

However, the following example will work.

**Code**

```python3
print("My name is {1}. I love {2}".format("Pylenin", "Python", "Programming"))```

**Output**

```bash
My name is Python. I love Programming
```

In this case, you have values inside the `string.format()` method with index from 0 to 2. You are just not using the 0th index in your string.

#### Formatters with Keyword Arguments

Instead of empty curly braces or curly braces with index, you can also use keyword arguments.

**Code**

```python3
print("My name is {name}. I love {language}"\
      .format(name="Pylenin", language="Python"))
```

**Output**

```bash
My name is Pylenin. I love Python
```

Keyword arguments are like keys in a dictionary. Their order doesn't matter, as they are matched against a name.

#### Specifying Formatting Type

You can also use a specific format in string formatting in Python.

Let's look at the below example.

**Code**

```python3
# integer
print("Integer representation of 99 is {:d}".format(99))

# float
print("Float representation of 99 is {:.2f}".format(99))

# binary
print("Binary representation of 99 is {:b}".format(99))

# exponent
print("Exponential representation of 99 is {:.2e}".format(99))
```

**Output**

```bash
Integer representation of 99 is 99
Float representation of 99 is 99.00
Binary representation of 99 is 1100011
Exponential representation of 99 is 9.90e+01
```

You can find a list of available formatters [here](https://docs.python.org/3/library/string.html#format-specification-mini-language).

**Python offers 3 other ways of String Formatting. Check out [the definite guide to Python String Formatting](https://www.pylenin.com/blogs/python-string-formatting/)** 

#### Related Articles

1. [f-strings in Python](https://www.pylenin.com/blogs/f-strings-python/)
2. [Python String Template Class](https://www.pylenin.com/blogs/python-string-template-class/)
3. [% operator - Python String formatting](https://www.pylenin.com/blogs/string-formatting-percentage-operator/)
4. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
5. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
6. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
7. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
8. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
9. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
10. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
11. [Commonly used Python string methods](https://www.pylenin.com/blogs/common-python-string-methods)