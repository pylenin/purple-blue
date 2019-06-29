---
title: "Finding N Largest(Smallest) items in Python with Heapq"
description: "A simple way to return the N largest or smallest elements using the heapq module in Python 3"
date: 2019-06-29T09:47:23+02:00
draft: false
image: /img/heapq/python-heapq.png
---

<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Let's look at this list.

```python3
x = [1, 3, 7, 21, -90, 67, 42, 12]
```

Now we want to write a Python script to return the 2 largest elements in the list.

A simple way would be to scan the whole list and find the maximum value at the current state. Then append it to a new list and remove the value from the original list. You continue this process for as many (N) numbers you want.

```python3
x = [1, 3, 7, 21, -90, 67, 42, 12]

def max_finder(lst, N, result_lst = list()):
    while N > 0:
        max_value = max(lst)
        result_lst.append(max_value)
        lst.remove(max_value)
        N-=1
    return result_lst

print(max_finder(x, 2))
```

The above script will return you the **2 largest elements** in the python list.

```bash
[67, 42]
```

The same process can be used for finding the 2 smallest elements of the list.
```python3
x = [1, 3, 7, 21, -90, 67, 42, 12]

def min_finder(lst, N, result_lst = list()):
    while N > 0:
        min_value = min(lst)
        result_lst.append(min_value)
        lst.remove(min_value)
        N-=1
    return result_lst

print(min_finder(x, 2))
```

This will return you
```bash
[-90, 1]
```

Now especially if you are a beginner, I would highly recommend you trying to solve such a problem this way. This ia great way to learn the various nuances of the Python programming languages.

But Python is known for its **kickass modules**. By importing a module, you can accomplish the same task with much lesser lines of code. For the above problem, you can use the `heapq` module in Python.

Heapq is already part of the standard library in Python. Hence no need to install it.

Let's find out the 2 largest or smallest numbers from the list using heapq.

For that purpose, we can use the `nlargest` and the `nsmallest` functions respectively.

```python3
import heapq

x = [1, 3, 7, 21, -90, 67, 42, 12]

print(heapq.nlargest(2, x))
>>> [67, 42]

print(heapq.nsmallest(2, x))
>>> [-90, 1]
```

We can also use heapq with a python dictionary. In order to do that, we have to pass in a `key` parameter inside our heapq methods.

```python3
import heapq

laptop_costs = {
    'Compaq':499,
    'Dell':530,
    'Apple':999,
    'HP':750,
    'ASUS':650
}

# The 2 cheapest laptops
key_values = zip(laptop_costs.values(), laptop_costs.keys())
print(heapq.nsmallest(2, key_values))
>>> [(499, 'Compaq'), (530, 'Dell')]

# The 2 expensive laptops
key_values = zip(laptop_costs.values(), laptop_costs.keys())
print(heapq.nlargest(2, key_values))
>>> [(999, 'Apple'), (750, 'HP')]
```

_**Recommended articles**_

1. [Power of zip() in Python](https://www.pylenin.com/blogs/python-zip-function/)
2. [Comparison Operators in Python](https://www.pylenin.com/blogs/python-comparison-operators/)
3. [5 reasons to learn Python in 2019](https://www.pylenin.com/blogs/5-reasons-to-learn-python/)

