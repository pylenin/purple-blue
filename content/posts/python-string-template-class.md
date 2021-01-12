---
title: "Python String Template Class"
description: "Learn to perform string formatting with String Template class in Python"
date: 2021-01-12T12:09:04+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Python String Template

The String Template class in Python is used to create a **template string** using a `$` sign. These fields can be replaced later on to create a string object.

This class has 2 key methods:

```bash
===============================
1. substitute(mapping, **kwds):
=============================== 
This method performs substitutions using a 
"dictionary like" key-value based mapping objects.
If keys are missing, it returns a KeyError.

====================================
2. safe_substitute(mapping, **kwds):
==================================== 
Similar behavior as above, but it doesn’t throw a 
KeyError if a key is missing. It just returns the 
placeholder in the result string.
```

Let's look at a few examples.

##### String Template substitute() method

##### Example 1

**Code**

```python3
from string import Template

t = Template('$name writes blogs on $language')
s = t.substitute(name='Pylenin', language='Python')
print(s)

# dictionary as substitute argument
d = {'name': 'Pylenin', 'language': 'Python'}
s = t.substitute(**d)
print(s)
```

**Output**

```bash
Pylenin writes blogs on Python
Pylenin writes blogs on Python
```

##### Example 2

**Code**

```python3
from string import Template

# Students and their respective heights
Student = [('Lenin', 190), ('Darshana', 180), ('Chinmayee', 150)]

# Create a basic structure
# to print the name and height
t = Template('Hi $name, your height is $height cm')

for i in Student:
    print(t.substitute(name=i[0], height=i[1]))
```

**Output**

```bash
Hi Lenin, your height is 190 cm
Hi Darshana, your height is 180 cm
Hi Chinmayee, your height is 150 cm
```

Let's look at the possible errors in String Template substitute() method.

1. If a key is missing from your **dictionary like** object, it will throw a `KeyError`.
2. Any other appearance of `$` in the string will result in a `ValueError`.

**Code - Example 1**

```python3
from string import Template

t = Template('$name writes blogs on $language')

d = {'name': 'Pylenin'}
s = t.substitute(**d)
print(s)
```

**Output - Example 1**

```bash
KeyError: 'language'
```

**Code - Example 2**

```python3
from string import Template

t = Template('Give $name $100')

s=t.substitute({"name":"Pylenin"})
print(s)
```

**Output - Example 2**

```bash
ValueError: Invalid placeholder in string: line 1, col 12
```

You can get rid of the above 2 errors using the following:-

1. `KeyError` - Use safe_substitute() method
2. `ValueError` - Use safe_substitute() method **or** Escape the `$` sign using `$$`.

#### String Template safe_substitute() method

If placeholders are missing from mapping and kwds, instead of raising a KeyError exception, the original placeholder will appear in the resulting string.

**Code**

```python3
from string import Template

t = Template('$name writes blogs on $language')

d = {'name': 'Pylenin'}
s = t.safe_substitute(**d)
print(s)
```

**Output**

```bash
Pylenin writes blogs on $language
```

It can also escape any other appearances of the `$` sign.

**Code**

```python3
from string import Template

t = Template('Give $name $100')

s=t.safe_substitute({"name":"Pylenin"})
print(s)
```

**Output**

```bash
Give Pylenin $100
```

#### Escaping `$` sign with `$$`

Another way to escape any other appearances of the `$` sign, is to use `$$` sign.

If you use `$$`, you can safely use the `substitute()` method.

**Code**

```python3
from string import Template

t = Template('Give $name $$100')

s=t.substitute({"name":"Pylenin"})
print(s)
```

**Output**

```bash
Give Pylenin $100
```

**Python offers 3 other ways of String Formatting. Check out [the definite guide to Python String Formatting](https://www.pylenin.com/blogs/python-string-formatting/)** 

#### Related Articles

1. [f-strings in Python](https://www.pylenin.com/blogs/f-strings-python/)
2. [Python String format() method](https://www.pylenin.com/blogs/format-method-python-string/)
3. [% operator - Python String formatting](https://www.pylenin.com/blogs/string-formatting-percentage-operator/)
4. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
5. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
6. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
7. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
8. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
9. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
10. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)

