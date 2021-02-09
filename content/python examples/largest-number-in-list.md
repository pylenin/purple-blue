---
title: "Python program to find the largest number in a list"
description: "Learn multiple ways to find the largest number in a list in Python"
date: 2021-02-09T08:50:42+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Given a list of numbers, the objective is to find the largest number in the list.

```bash
input 1 ==> [1, 2, 3]
output 1 ==> 3

input 2 ==> [10, 20, 40, 100, 5, 9]
output 2 ==> 100
```

#### Method 1 - Use `max()` method

You can find the largest element ina list by using the 
`max()` built-in method in Python.

**Code**

```python3
my_list = [1, 2, 3]
print(max(my_list))
```

**Output**

```bash
3
```

#### Method 2 - Sort in ascending order and show the last element

**Code**

```python3
my_list = [3, 1, 2]

my_list.sort()
# Print the last element
#after sorting
print(my_list[-1])
```

**Output**

```bash
3
```

#### Method 3 - Using for loop

**Code**

```python3
my_list = [3, 1, 200]

max_number = None

for i in my_list:
    # if max_number is not set, set it to the 1st element
    if not max_number:
        max_number = i
    # if i > max_number, set max_number to i
    elif i > max_number:
        max_number = i
    else:
        continue

print(max_number)
```

**Output**

```bash
200
```

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp-2021/).