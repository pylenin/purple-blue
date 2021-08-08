---
title: "Python Map, Filter and Reduce (With Examples)"
description: "Learn to use map, filter and reduce functions in Python 3 with examples."
date: 2021-03-08T06:16:46+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python functions']
categories_weight: 8
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Pre-requisites**

1. [Python Functions](https://www.pylenin.com/blogs/python-functions/)
2. [Anonymous or Lambda Functions](https://www.pylenin.com/blogs/lambda-function-python/)

## Youtube Video

<br>
{{< youtube id="8roRLynIYMM" >}}
<br>

## Introduction

Map, filter and reduce functions are the pillars of 
**functional programming**. While Python isn't a purely 
functional programming language, it boasts many features that 
allow it to be used as such. This article covers the usage of 
Python's map, filter and reduce functions and how they conform to 
the ideas of functional programming.

## map()

The `map()` function will iterate through all items 
in the given iterable and will execute the function passed as an argument 
on each of the items. Let's go through the below mentioned code.

### Example 1

**Code**

```python3
counter = 0

for i in range(10):
    counter += 1
    print(counter)
```

Within every iteration, you are performing an addition operation 
with the `counter` variable. The results should look like the following. 

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
10
```

Now, another way of achieving the above result is by using the `map()` 
function in Python.

**Code**

```python3
def add_one(num):
    return num+1

counter_list = map(add_one, range(10))
print(counter_list)
```

As you can see above, the addition operation has now moved inside the 
`add_one()` function. The function returns the parameter passed after 
adding 1 to it.

Now if you try to print `counter_list`, you will get an output similar 
to this.

```bash
<map object at 0x000001FED1D4FE80>
```

Basically, it is the **address of the generator object** created by 
the `map()` function. Python employs a concept called 
**lazy evaluation**, which means that it doesn't evaluate objects 
until the moment we need to use them.

In order to get the output, you need to convert it 
into an iterable. For that you can enclose the `map()` function within 
an iterable of your choice like **list, sets, tuples etc.**.

**Code**

```python3
def add_one(num):
    return num+1

counter_list = list(map(add_one, range(10)))
print(counter_list)
```

**Output**

```bash
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

You could also replace the above function using a [Lambda function](https://www.pylenin.com/blogs/lambda-function-python/). 

### Example 2 - Using Lambda Function

**Code**

```python3
add_one = lambda x: x+1
counter_list = list(map(add_one, range(10)))
print(counter_list)
```

**Output**

```bash
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

**To learn more about Lambda functions in Python, 
check out [this article](https://www.pylenin.com/blogs/lambda-function-python/).**

## filter()

The `filter()` function works similar to `map()` function, except, 
it validates `True` if a condition is met and validates `False` otherwise. 
It only returns the items of a sequence that validate to `True`.

### Example 1

**Code**

```python3
check_boolean = filter(bool, ["Pylenin", "", None])
print(list(check_boolean))
```

The above code checks the **boolean** status of the items in the list. 
If it is `True`, it returns the item and if it is `False`, it doesn't include 
it in the results.

**Output**

```bash
['Pylenin']
```

As you can see, only `"Pylenin"` is being returned in the result list. 
This means that the other 2 items are being validated as `False` by the 
`bool` function. To learn more about **Booleans**, check out this [article here](https://www.pylenin.com/blogs/booleans-in-python/).

Similar to `map()` function, `filter()` also engages a lazy evaluation.

## reduce()

Unlike `map()` and `filter()`, `reduce()` function doesn't 
return a new sequence. Instead, **it returns a single value**.

In Python 3, `reduce()` has been moved to the `functools` library. 
You can read Guido van Rossum's (the creator of Python) reasoning behind moving 
`reduce` [here](https://www.artima.com/weblogs/viewpost.jsp?thread=98196).

### Example 1

**Code**

```python3
from functools import reduce

def addition(x, y):
    return x + y

list = [1, 2, 3, 4]
print(reduce(addition, list))
```

The above code tries to add the elements of a list and return the final output.
Now you might think that **this is unnecessarily over doing simple addition**. This is true. 
Also, it can have bad performance because it calls a function multiple times.

So, be careful with using `reduce()` function in your code.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).


