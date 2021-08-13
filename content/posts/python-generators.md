---
title: "Beauty of Python Generators (With Examples)"
description: "Learn to benefits and usage of generators in Python 3 with examples."
date: 2021-03-12T06:16:46+05:30
draft: false
image: /img/pylenin_logo.png
categories: []
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Pre-requisites**

1. [Python Iterators - iter() and next()](https://www.pylenin.com/blogs/python-iterators/)
2. [Build a simple iterator class in Python](https://www.pylenin.com/python-examples/build-iterator-class/)

## Youtube video

<br>
{{< youtube id="nvaIaz3F3K8" >}}
<br>

## Generators in Python

Generators are simple ways of creating **iterators**. It is a function 
that returns an iterator, that we can iterate over 
(one value at a time).

## Why use a generator?

Check out this article on [building a simple iterator class](https://www.pylenin.com/python-examples/build-iterator-class/). 
You have to implement a class with an `__iter__()` and `__next__()` 
method, keep track of all the states, and raise `StopIteration` error 
when there are no values need to be returned.

Generators in Python make this work easy by directly returning an iterator object.

## How to create a generator in Python?

To create a generator function, you need to use the `yield` keyword 
instead of the `return` keyword, as you would use in a function. 

The difference between a normal function and a generator function 
is that while a `return` statement terminates a function, 
`yield` statement will pause the function, save its current state 
and later continue from there in the next call.

### Example 1

**Code**

```python3
def try_generator(y):
    n = y
    n += 1
    print("Performed addition")
    yield n

    n *= 2
    print("Performed multiplication")
    yield n

result = try_generator(5)

print(next(result))
print(next(result))
```

**Solution**

```bash
Performed addition
6
Performed multiplication
12
```

You can see how the `yield` keyword works. When the `yield` 
statement runs, the function of the program is suspended and 
Python saves the state of the function and returns the 
**current value of the state**. This allows you to resume function 
execution whenever you call `yield` keyword again. 
Experiment this by using multiple Python yield statements.

If you use `return`, execution stops completely. 

### Example 2

**Code**

```python3
def return_squared(min, max):
    for i in range(min, max):
        yield i**2

result = return_squared(1, 5)

print(next(result))
print(next(result))
print(next(result))
print(next(result))
print(next(result))
```

**Output**

```bash
1
4
9
16
Traceback (most recent call last):
  File "some_file_name", line 11, in <module>
    print(next(result))
StopIteration
```

As you can see, it is exactly how an iterator works. 
After all the items have been iterated over, Python will return 
a `StopIteration` error.

## Using loops with Python generators

To iterate over all the items of an iterator, you can use iterators 
in a loop.

**Code**

```python3
def return_squared(min, max):
    for i in range(min, max):
        yield i**2

result = return_squared(1, 5)

for item in result:
    print(item)
```

**Output**

```bash
1
4
9
16
```

## Python Generator Expression

Similar to a lambda function, which creates anonymous functions, 
generator expressions create **anonymous generator functions**.

The syntax for generator expression is similar to that of a 
list comprehension in Python, except you use round parenthesis `()` 
instead of squared brackets `[]`. 

**Code**

```python3
my_list_com = [num for num in range(5)]
print(my_list_com)

my_generator = (num for num in range(5))
print(my_generator)
for i in my_generator:
    print(i)
```

**Output**

```bash
[0, 1, 2, 3, 4]

<generator object <genexpr> at 0x000001EC0092FDD0>
0
1
2
3
4
```

While the list comprehension produces the entire list all at once, 
the generator returns every number one at a time. This is called **lazy execution**. 
This makes generator highly **memory efficient** than a list comprehension.

## Advantages of Python generators

1. Easier to build iterators using generators.
2. They are memory efficient

    Generators are memory friendly since it only produces one item at a time.

3. They can represent an infinite stream of data

    **Code**

    ```python3
    def infinte():
        i = 0
        while True:
            i+=1
            yield i
    ```
    
    The above code will keep returning whole numbers starting with 1 infinitely.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).



