---
title: "Python program to merge dictionaries"
description: "Learn 3 different ways to merge dictionaries in Python 3"
date: 2021-08-11T06:57:35+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python Dictionary Examples']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Pre-requisite knowledge**

1. [Python dictionary](https://www.pylenin.com/blogs/python-dictionary/)
2. [*args vs **kwargs in Python](https://www.pylenin.com/blogs/args-vs-kwargs-python/)

## Method 1 - Using ** operator

**Code**

```python3
x = {"name":"Pylenin", "age":30}
y = {"city":"Gurgaon", "age":29}

print({**x, **y})
```

**Output**

```bash
{'name': 'Pylenin', 'age': 29, 'city': 'Gurgaon'}
```

## Method 2 - Using | operator

**Note:-** The `|` operator can only be used in Python 3.9 and above.

**Code**

```python3
x = {"name":"Pylenin", "age":30}
y = {"city":"Gurgaon", "age":29}

print(x|y)
```

**Output**

```bash
{'name': 'Pylenin', 'age': 29, 'city': 'Gurgaon'}
```

## Method 3 - Using update()

By using `update()` in Python 3, one dictionary can be merged into 
another. **Note:-** This will change the original dictionary.

**Code**

```python3
x = {"name":"Pylenin", "age":30}
y = {"city":"Gurgaon", "age":29}

x.update(y)
print(x)
```

**Output**

```bash
{'name': 'Pylenin', 'age': 29, 'city': 'Gurgaon'}
```