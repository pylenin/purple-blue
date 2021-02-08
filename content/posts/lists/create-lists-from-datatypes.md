+++ 
draft = true
date = 2021-02-07T17:48:09+05:30
title = ""
description = ""
slug = "" 
tags = []
categories = []
externalLink = ""
series = []
+++

#### Create lists from strings in Python

You can convert a string to a list in Python by using the `list()` constructor.

**Code**

```python3
my_string = "Pylenin"
print(list(my_string))
```

**Output**

```bash
['P', 'y', 'l', 'e', 'n', 'i', 'n']
```

**Output**

#### Create lists from tuples and sets in Python

Similarly to strings, you can also convert tuples and sets to lists in Python.

**Code**

```python3
my_tuple = (1, 2, 3)
print(list(my_tuple))

my_set = {1, 2, 3, 4}
print(list(my_set))
```

**Output**

```bash
[1, 2, 3]
[1, 2, 3, 4]
```

#### Create lists from dictionary in Python

You can also convert a dictionary to a list in Python by using the `list()` constructor.

**Code/Output**

```python3
my_dict = {
    "name" : "Pylenin",
    "language" : "Python",
    "age": 29
}
# Passing my_dict as argument
print(list(my_dict))
>>> ['name', 'language', 'age']

# Passing my_dict.keys() as argument
# Same result as above
print(list(my_dict.keys()))
>>> ['name', 'language', 'age']

# Passing my_dict.values() as argument
print(list(my_dict.values()))
>>> ['Pylenin', 'Python', 29]

# Passing my_dict.items as argument
# Result contains tuples of key-value pairs
print(list(my_dict.items()))
>>> [('name', 'Pylenin'), ('language', 'Python'), ('age', 29)]
```
