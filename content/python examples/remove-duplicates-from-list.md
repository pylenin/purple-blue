---
title: "Python program to remove duplicates from a list"
description: "Learn multiple ways to remove duplicates from a list in Python"
date: 2021-02-09T09:58:58+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Given a list of numbers in Python, 
the objective is to remove any possible duplicates in the list.

```bash
input 1 ==> [10, 20, 30, 30, 40, 60]
output 1 ==> [10, 20, 30, 40, 60]

input 2 ==> [10, 20, 30, 40, 50, 60, 30]
output 2 ==> [10, 20, 30, 40, 50, 60]
```

#### Method 1 - Using a for loop

**Code**

```python
my_list = [10, 20, 30, 40, 50, 60, 30]

result_list = []

for i in my_list:
    if i not in result_list:
        result_list.append(i)
    else:
        continue

print(result_list)
```

**Output**

```bash
[10, 20, 30, 40, 50, 60]
```

#### Method 2 - Using sets

A **set data type** cannot store duplicates. 
So you can also use this method to remove duplicates from a list.

Be careful, the `set()` will change the order of the elements in the list.

**Code**

```python
my_list = [10, 20, 30, 40, 50, 60, 30]

print(list(set(my_list)))
```

**Output**

```bash
[40, 10, 50, 20, 60, 30]
```

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).