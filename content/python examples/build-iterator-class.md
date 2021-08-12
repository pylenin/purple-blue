---
title: "Python program to build a simple Iterator class"
description: "Learn to build a simple Iterator class in Python 3"
date: 2021-08-10T06:57:35+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python Generator Examples']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Pre-requisites**

1. [Python Iterators - iter() and next()](https://www.pylenin.com/blogs/python-iterators/)

Iterator objects in Python programming confirm to the iterator 
protocol. They provide two methods: `__iter__()` and `__next__()` 
to iterate over all the elements of the iterator.

* `__iter__` is called at the start of a loop. It returns the iterator object.

* `__next__()` method returns the next value in the iterator and is implicitly called at each loop increment. When there are no more value to return, it raises a `StopIteration` example.

For more information on Python iterators, check out the **pre-requisite article mentioned [above](https://www.pylenin.com/blogs/python-iterators/)**.

Let's build a simple **Counter class** to understand the concept.

**Code**

```python3
class Counter:
    def __init__(self, low, high):
        self.current = low - 1
        self.high = high

    def __iter__(self):
        return self

    def __next__(self):
        self.current += 1
        if self.current < self.high:
            return self.current
        raise StopIteration

for elem in Counter(1, 10):
    print(elem)
```

**Output**

```bash
1
2
3
4
5
6
7
8
9
```

The above is a **basic iterator** class built with Python Object Oriented Programming.

This is where **generators come to rescue**.

**Code**

```python3
def counter(low, high):
    current = low
    while current < high:
        yield current
        current += 1

for elem in Counter(1, 10):
    print(elem)
```

**Output**

```bash
1
2
3
4
5
6
7
8
9
```

As you can see, the printed output will be the same. 

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).