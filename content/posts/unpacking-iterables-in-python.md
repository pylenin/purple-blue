---
title: "Unpacking Iterables in Python"
description: "Learn different ways to unpack iterables or sequences in Python through useful examples."
date: 2019-06-21T00:07:34+02:00
draft: false
image: /img/python-unpacking/python-unpacking.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

You can easily unpack sequences or iterables into various variables in python.

But first, **what is the difference between sequences and iterables?**

A sequence is an ordered collection of values. Once a list is initialised, the index of the values will not change. Some examples of sequences are **List, Dictionary, Tuples and Strings**.

Iterables are collection of values over which you can loop over. All sequences are iterables, but not all iterables are sequences. For examples, **Sets**.

```python3
x = {12, 6, 9}
print(x)

# Result
>> {6, 9, 12}
```
So the order in which the values in the set are initialized is not the way it appears. Also, **Sets return only unique elements.**
```python3
x = {12, 6, 9, 9}
print(x)

# Result
>> {6, 9, 12}
```

##### Basic Unpacking

You can carry out the unpacking procedure for all kinds of iterables like **lists, tuples, strings, iterators and generators**. There are 2 ways to unpack iterables in Python.

1. **For known length iterables** - Providing the exact number of variables to unpack as the number of elements in the sequence/iterable.
2. **For arbitrary length iterables** - Using `star expressions (*)` to unpack when you are unsure of the number of variables to pass.

Let's look at some examples.

##### Unpacking known length iterables
When the lenth of the data type is very obvious, you can pass in the exact number of variables as the number of values in the data type to unpack the values.

```python3
my_info = ["Lenin", "Mishra", 28, "Amsterdam"]

name, surname, age, place = my_info

# Result
>>> name
'Lenin'
>>> surname
'Mishra'
>>> age
28
>>> place
'Amsterdam'
```
Since I know that there are 4 values inside my list. I am passing in 4 variables to unpack those values. The values are unpacked in the **same order** as the provided variables.

If there is a mismatch of values and variables, Python will throw you an error.

**In case when less variables are provided**
```python3
my_info = ["Lenin", "Mishra", 28, "Amsterdam"]
name, other_info = my_info

# Result
Traceback (most recent call last):
  File <input>, line 2, in <module>
    name, other_info = my_info
ValueError: too many values to unpack (expected 2)
```

**In case when more variables are provided**
```python3
my_info = ["Lenin", "Mishra", 28, "Amsterdam"]
name, surname, age, place, other = my_info

# Result
Traceback (most recent call last):
  File <input>, line 2, in <module>
    name, surname, age, place, other = my_info
ValueError: not enough values to unpack (expected 5, got 4)
```

Let's look at another example. Let's assume you provide the name and surname as a **tuple (or any sequence)**.
```python3
my_info = [("Lenin", "Mishra"), 28, "Amsterdam"]

name, age, place = my_info

# Result
>>> name
('Lenin', 'Mishra')
>>> age
28
>>> place
'Amsterdam'
```

Now the `name` variable stores the tuple as a value with both the first name and surname as information. If we want to extract both parts of the name, we can pass in a **sequence of variables**.
```python3
my_info = [("Lenin", "Mishra"), 28, "Amsterdam"]

(name, surname), age, place = my_info

# Result
>>> name
'Lenin'
>>> surname
'Mishra'
>>> age
28
>>> place
'Amsterdam'
```

It is also possible to **discard certain values** that you may not need.

Let's say you are not interested with the `place` information. You can use a `_` to disregard the unpacked value.
```python3
my_info = ["Lenin", "Mishra", 28, "Amsterdam"]

name, surname, age, _ = my_info

# Result
>>> name
'Lenin'
>>> surname
'Mishra'
>>> age
28
```

**How to unpack a python dictionary?**

The process for unpacking a python dictionary is not the same as unpacking a python tuple or a list. When you apply the above method to a dictionary, you will be unpacking **just the keys**.

```python3
my_info = {"name":"Lenin", "age":28}

x, y = my_info

# Result
>>> x
'name'
>>> y
'age'
```

Now to get the values for the respective dictionary keys, you have to call the dictionary key.

```python3
>>> my_info[x]
'Lenin'
>>> my_info[y]
28
```

##### Unpacking arbitrary length iterables

Let's be honest! Its not always possible to provide all the required variables to unpack the values. Imagine providing a million variables to unpack a list containing 1000 records! That is just sloppy.

Let's look at an example. Suppose you have a list of university scores from the 1st till the 6th semester. While averaging, you decide to **leave out the first and last score**. 

In this case, you need to unpack all the scores between the first and last value.
```python3
scores = [92, 90, 87, 64, 75, 91]
first, *middle, last = scores

>>> middle
[90, 87, 64, 75]
```

Let's look at a log message. To learn more about Logging in Python, check out [this article](https://www.pylenin.com/blogs/python-logging-guide/).

What we want to achieve is get the `logging level` and the `logging message`.

```python3
log_msg = "2019-06-05 17:43:07,889 :: __main__ :: INFO :: I am a separate Logger"
log_msg_comps = [x.strip() for x in log_msg.split('::')] 

t_stamp, file, *req_entities = log_msg_comps

>>> req_entities
['INFO', 'I am a separate Logger']
```

The use of `star expression (*)` makes unpacking very convenient for arbitrary length iterables. Imagine reading a file in Python and you want to ignore the headers. You can apply the similar technique as above. 

Feel like doing a small exercise? 
</br>**Write the code for ignoring the header of a file using the above unpacking method in the comments section below.**

We can also **discard irrelevant values** through this process. In order to disregard certain values, use `_` with the `star expression (*)`.

```python3
log_msg = "2019-06-05 17:43:07,889 :: __main__ :: INFO :: I am a separate Logger"
log_msg_comps = [x.strip() for x in log_msg.split('::')] 

# Ignore all values except the message
*_, log_message = log_msg_comps

>>> log_message
I am a separate Logger
```

Hope this blog was insightful in terms of providing you information about unpacking. The more you practice it, the more you will become comfortable with it.

_**Recommended articles**_

1. [Mastering Python Datetime](https://www.pylenin.com/blogs/mastering-python-datetime/)
2. [Power of zip() in Python](https://www.pylenin.com/blogs/python-zip-function/)
3. [10 benefits of switching to Python 3 from 2](https://www.pylenin.com/blogs/10-benefits-of-switching-to-python-3/)

