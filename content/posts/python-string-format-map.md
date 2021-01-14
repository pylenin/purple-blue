---
title: "Python String format_map() Method"
description: "Learn to use format_map() method on Python strings"
date: 2021-01-13T19:36:11+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Difference between `format()` and `format_map()` in Python

The `format_map()` method is similar to `format()` method in Python., except that it only accepts a dictionary as input.

Learn more about [Python String format() method](https://www.pylenin.com/blogs/format-method-python-string/).

#### Syntax of `format_map()` method

```bash
string.format_map(mapping)

mapping: The Input dictionary
```

##### Example 1

**Code**

```python3
s = '{name} lives in {country}'

my_dict = {'name': 'Pylenin', 'country': 'India'}

# Using format_map() method
print(s.format_map(my_dict))

# Using format() method
print(s.format(**my_dict))
```

**Output**

```bash
Pylenin lives in India
Pylenin lives in India
```

##### Example 2 - If mapping has more keys

If mapping dictionary has more keys, then only the necessary keys are used for [string formatting](https://www.pylenin.com/blogs/python-string-formatting/).

**Code**

```python3
s = '{name} lives in {country}'

my_dict = {'name': 'Pylenin',
           'country': 'India',
           'language': 'Python'}

# Using format_map() method
print(s.format_map(my_dict))

# Using format() method
print(s.format(**my_dict))
```

**Output**

```bash
Pylenin lives in India
Pylenin lives in India
```

##### Example 3 - If mapping has missing keys

If mapping dictionary has missing keys, both `format()` and `format_map()` will throw a `KeyError`.

**Code**

```python3
s = '{name} lives in {country}'

my_dict = {'name': 'Pylenin',
           'country': 'India',
           'language': 'Python'}

# Using format_map() method
print(s.format_map(my_dict))

# Using format() method
print(s.format(**my_dict))
```

**Output**

```bash
# format_map()
KeyError: 'country'

# format()
KeyError: 'country'
```

##### Advantage of format_map() over format()

With the `format_map()` method, you can avoid such `KeyError` issues by working with a **dict subclass**.

Let's look at the below example.

**Code**
```python3
class PyleninDict(dict):
    def __missing__(self, key):
        return '{}'

s = '{name} is born in {country}'
my_dict = PyleninDict(name='Pylenin')
print(s.format_map(my_dict))
```

**Output**

```bash
Pylenin is born in {}
```

As you can see, we didn't receive a `KeyError` anymore. The `__missing__` function was called and `format_map()` was able to handle the missing key.

The above doesn't work for `format()` method

**Code**
```python3
class PyleninDict(dict):
    def __missing__(self, key):
        return '{}'

s = '{name} is born in {country}'
my_dict = PyleninDict(name='Pylenin')

# Using format() instead of format_map()
print(s.format(**my_dict))
```

**Output**

```bash
KeyError: 'country'
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

