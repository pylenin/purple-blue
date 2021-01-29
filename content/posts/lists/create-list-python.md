---
title: "How to create a list in Python?"
description: "Learn to create and use lists in Python 3 with examples."
date: 2021-01-28T08:21:32+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python lists']
categories_weight: 1
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Python offers a variety of data types. 
List is one of the most frequently used data types in Python.

#### Characteristics of Python Lists

1. Python lists can contain any data type of your choice, e.g., String, Integers, Python objects etc.
2. Lists can also contain lists. They are called **Nested Lists**.
3. **Lists are mutable**. This means, you can alter the contents of a list anytime during the program.
4. The sequence in which data is stored in a list is preserved.

The above characteristics make Python lists very powerful and versatile.

#### How to create a list in Python?

To create an empty list, you cn directly call the `list()` constructor.
You can also declare an empty list with empty square brackets `[]`.

**Code**

```python3
my_list = list()
print(my_list)

my_second_list = []
print(my_second_list)
```

**Output**

```bash
[]
[]
```

To create a **non-empty list**, you can place all the items within the square brackets `[]`.

**Code**

```python3
my_list = [1, 2, 3]
print(my_list)

another_list = ["Pylenin", 1, "loves", "Python"]
print(another_list)

my_nested_list = ["Pylenin", [1, 2, 3]]
print(my_nested_list)
```

**Output**

```bash
[1, 2, 3]
["Pylenin", 1, "loves", "Python"]
["Pylenin", [1, 2, 3]]
```

The nested lists are also called Multi dimensional lists.

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

