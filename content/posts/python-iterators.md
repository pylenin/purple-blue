---
title: "Python Iterators - iter() and next()"
description: "Learn the usage of Python iterators by visualizing how a for loop works in Python with examples."
date: 2021-02-19T07:21:21+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['iterators and comprehensions']
categories_weight: 1
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

## Difference between sequence and an iterable

A sequence is an ordered collection of values. 
Once a list is initialised, the index of the values will not change. 
Some examples of sequences are List, Dictionary, Tuples and Strings.

Iterables are collection of values over which you can loop over. 
**All sequences are iterables, but not all iterables are sequences.** 
For examples, Sets.

```python3
x = {12, 6, 9}
print(x)

# Result
>> {6, 9, 12}
```

So the order in which the values in the set are initialized 
is not the way it appears. Also, Sets return only unique elements. 
Learn more about Python Sets [here](https://www.pylenin.com/blogs/python-sets/).



## What are iterators?

Iterators are objects that manage iteration over an iterable. 
**An iterator has an iteration set** - it knows the current element and also the next element in the iterable.

To create an iterator from an iterable, you can pass it through  
the `iter()` method. 

**Code**

```python3
my_list = [1, 2, 3]
my_list_iter = iter(my_list)

print(type(my_list))
print(type(my_list_iter))
```

**Output**

```bash
<class 'list'>
<class 'list_iterator'>
```



## next() in Python

An iterator uses `next()` method for iteration. 
It returns a `StopIteration` Exception when it runs 
out of elements.

**Code**

```python3
my_list = [1, 2, 3]
my_list_iter = iter(my_list)

print(next(my_list_iter))
print(next(my_list_iter))
print(next(my_list_iter))
print(next(my_list_iter))
```

**Output**

```bash
1
2
3
Traceback (most recent call last):
  File "some_file_location", line 7, in <module>
    print(next(my_list_iter))
StopIteration
```



## for loop - Behind the scenes

When you use a [for loop](https://www.pylenin.com/blogs/python-for-loop/) 
to iterate through an iterable, it internally **converts the iterable to an iterator** 
and then uses the `next()` method to return the next element.

You can visualize the internal working of a `for` loop, similar to the code below.

**Code**

```python3
my_list = [1, 2, 3]
my_list_iter = iter(my_list)

while True:
    try:
        print(next(my_list_iter))
    except StopIteration:
        break
```

**Output**

```bash
1
2
3
```

To understand the above code, you need to know that `try and except` 
statements run an action and catch exceptions that might occur during its execution. 
You can learn more about it [here](https://www.pylenin.com/blogs/python-try-except-else-finally/).



Similar operation happens for other data types too.

**Code**

```python3
# Strings
name = "Pylenin"
for char in name:
    print(char, end=" ")
print() # Empty print for better readability

# Tuples
my_tuple = (1, 2, 3)
for elem in my_tuple:
    print(elem, end=" ")
print() # Empty print for better readability

# Dictionary
my_dict = {"name":"Pylenin",
           "age": 28}
for key, value in my_dict.items():
    print(key, value)

# Even sets
some_set = {1, 2, 3, 4, 3, 4}
for elem in some_set:
    print(elem, end = " ")
```

**Output**

```bash
P y l e n i n 
1 2 3 
name Pylenin
age 28
1 2 3 4 
```




## Is a file object an iterator?

**Yes!** When you are working with file objects, you don't have 
to pass it through the `iter()` function. A file object is its own iterator.




The example below tries to read a csv file and use the `next()` method 
directly on the file handler object.

**Code**

```python3
f = open(file="world_cyclones.csv")

print(next(f))
print(next(f))
```

**Output**

```bash
Storm name,Dates active,Max windkm/h (mph),Pressure(hPa),Areas affected,Damage(USD),Deaths,Refs

Damien,February 2 – 11,165 (105),955,"Northern Australia, Kimberley",$4.3 million,None,
```

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).



