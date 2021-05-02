---
title: "Python Tuples (With Examples)"
description: "Learn to create and use tuple data type in Python 3 with examples."
date: 2021-02-10T08:21:32+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python tuples']
categories_weight: 1
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Tuples are a simple group of objects. 
Similar to lists, Tuples can also store different objects. 
Tuples in Python are written as a series of items/objects in a parenthesis. 

### Characteristics of Tuples

1. Similar to strings and lists, tuples are **ordered collections of objects**. They maintain a left-to-right order of their content.
2. Similar to lists, they can store different kinds of objects.
3. Similar to strings and lists, the object(s) in the tuple can be accessed by their index or slicing.
4. Similar to strings, **Tuples are immutables**. They don't support any in-place change operations.
5. Because tuples are immutable, **you cannot change the size of a tuple without making a copy**.



### How to create a tuple in Python?

Below are various ways to create different types of tuples in Python.

**Code**

```python3
# Empty Tuple
x = ()
print(x)

# One item Tuple
x = (1,) # Notice the trailing comma
print(x)

# Multiple items tuple
x = (1, 2, 3, 4)
print(x)

# Nested Tuples
x = ((1, 2), 3, 4)
print(x)

# Tuple from a list
x = tuple([1, 2, 3, 4])
print(x)

# Tuple from a string
x = tuple('Pylenin')
print(x)

# Tuple from a dictionary
x = tuple({"name":"Pylenin", "language":"Python"})
print(x)
```

**Output**

```bash
()
(1,)
(1, 2, 3, 4)
((1, 2), 3, 4)
(1, 2, 3, 4)
('P', 'y', 'l', 'e', 'n', 'i', 'n')
('name', 'language')
```



You can also create tuples **without using parenthesis**.

**Code**

```python3
x = 1, 2, 3, 4

print(x)
```

**Output**

```bash
(1, 2, 3, 4)
```

In the context of the above assignment statement, 
Python recognizes this as a tuple, even though it doesn't have parentheses.

#### Syntax peculiarity of Tuples

To create a single element tuple, make sure **to add a trailing comma**. Otherwise, Python will treat it as an individual data type.

**Code**

```python3
x = ("Pylenin")
print(type(x))

x = ("Pylenin",)
print(type(x))
```

**Output**

```bash
<class 'str'>
<class 'tuple'>
```



### Concatenating Tuples

Similar to strings and lists, you can use the `+` or `*` operator to concatenate lists.

**Code**

```python3
# Using + operator
x = (1, 2, 3)
y = (4,)
x += y
print("x is now ", x)

# Using * operator
x = (1, 2, 3)
x *= 2
print("x is now ", x)
```

**Output**

```bash
x is now  (1, 2, 3, 4)

x is now  (1, 2, 3, 1, 2, 3)
```

Notice how the ids have changed after both concatenation operations.



### Access elements of a tuple

The process of accessing elements from a tuple, 
works similar to strings and lists.

You can access individual elements of a tuple using **indexing** 
and a range of elements using **slicing**. 
In Python tuples, index starts from 0 and keeps increasing by 1 
with every element in the tuple. 
This is called Positive Indexing(or indexing from the beginning). 
If there are __**n**__ elements in a tuple, the 1st element will have 
index of **0** and the last element will have index **n-1**.

**Python also allows negative indexing of tuples(indexing from the end).** 
If there are __**n**__ elements in a list, the last element will have index 
of **-1** and the first element will have index __**-n**__.

Let's look at the image below for better understanding.

![Indexing of Tuples in Python](/img/python-tuples/indexing-tuples.png)

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

# first character
print('my_tuple[0] =', my_tuple[0])

# last character
print('my_tuple[-1] =', my_tuple[-1])

# second character
print('my_tuple[1] =', my_tuple[1])

# second last character
print('my_tuple[-2] =', my_tuple[-2])
```

**Output**

```bash
my_tuple[0] = 1
my_tuple[-1] = 5
my_tuple[1] = 2
my_tuple[-2] = 4
```



If you try to access an element out of range, it will raise an `IndexError`. 

Also, the index must be an **integer**. You can't use floats or other types for indexing. This will result in `TypeError`.

**Code/Output**

```python3
my_tuple = (1, 2, 3, 4, 5)

print(my_tuple[10])
>>> IndexError: list index out of range

print(my_tuple[3.5])
>>> TypeError: tuple indices must be integers or slices, not float
```



### Slicing of Tuples

Similar to strings and lists, you can access a range of elements 
from a tuple using **slicing**. 

Basically, you have to specify the starting index and the end index, 
separated by a colon(`:`), to return a range of elements from the tuple.

#### Slicing Tuples with Positive Index

![Slicing Tuples with positive index in Python](/img/python-tuples/slicing-tuples-with-positive-index.png)

**Remember** - The last index is not included.




Let's say you want to access the 1st and the 2nd index from a tuple.
In that case, **your end index will be 3**.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

print(my_tuple[1:3])
```

**Output**

```bash
(2, 3)
```

If you leave out the start index, the range will start at the first element.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

# leave out the first index
print(my_tuple[:3])
```

**Output**

```bash
(1, 2, 3)
```

If you leave out the end index, the range will go to the end.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

# leave out the end index
print(my_tuple[1:])
```

**Output**

```bash
(2, 3, 4, 5)
```

So, if you leave out both the start and end index, 
**you will get a replica of the original tuple**.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

# leave out the start and end index
print(my_tuple[:])
```

**Output**

```bash
(1, 2, 3, 4, 5)
```



#### Slicing Tuple with Negative Index

You can also use negative index for slicing. 
Just use the negative index counterpart of your 
positive index to slice a tuple.

![Slicing Tuples with negative index in Python](/img/python-tuples/slicing-tuples-with-negative-index.png)

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

# Slicing with Positive Index
print(my_tuple[1:3])
# Slicing with Negative Index
print(my_tuple[-4:-2])
```

**Output**

```bash
(2, 3)
(2, 3)
```




#### Mixing positive and negative indices for slicing tuples

You can also mix positive and negative indices 
while slicing a tuple.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

print(my_tuple[1:-1])
print(my_tuple[-3:5])
```

**Output**

```bash
(2, 3, 4)
(3, 4, 5)
```

Let's understand the above example using the below image.

![Mixing positive and negative indices for slicing tuples in Python](/img/python-tuples/slicing-tuple-with-positive-negative-index.png)




#### Using steps in slicing

You can also include **steps** while slicing a tuple. 
The step allows you to take every `nth` element while slicing.

**Syntax**

```bash
tuple[start:stop:step]
```

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

# Get every second element
# from beginning to end
print(my_tuple[::2])

# Get every second element
# starting at index 1 till end
print(my_tuple[1::2])

# Get every second element
# starting at index 1 upto -2 index
print(my_tuple[1:-2:2])
```

**Output**

```bash
(1, 3, 5)
(2, 4)
(2,)
```




#### Reversing a tuple

Negative step changes the slice **to be built from the tail of the tuple**. 
So, it goes from the last element to the first element. 
This way, we get a **reversed tuple**.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

print(my_tuple[::-1])
```

**Output**

```bash
(5, 4, 3, 2, 1)
```

When using a negative step, the start and stop values have to be 
provided from right to left (usually it is from left to right).

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

# Reverse the list
# without the last element
print(my_tuple[-2::-1])

# Reverse the list
# without the first and last element
print(my_tuple[-2:0:-1])
```

**Output**

```bash
(4, 3, 2, 1)
(4, 3, 2)
```



### Deleting a tuple

Because tuples are immutable, you cannot delete specific elements of a tuple

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

del my_tuple[0]
```

**Output**

```bash
TypeError: 'tuple' object doesn't support item deletion
```

However, it is possible to delete the entire tuple object.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

del my_tuple
print(my_tuple)
```

**Output**

```bash
NameError: name 'my_tuple' is not defined
```

### Commonly used methods with tuples

#### How to sort tuples?

Python doesn't provide all the methods that come with lists, strings or dictionaries.
For example, if you want to sort a tuple in increasing or decreasing order, you have to first convert it into a mutable object like list to get access to sorting methods.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

my_list = list(my_tuple)

# sort in ascending order
my_list.sort()
print(tuple(my_list))

# sort in descending order
my_list.sort(reverse=True)
print(tuple(my_list))
```

**Output**

```bash
(1, 2, 3, 4, 5)
(5, 4, 3, 2, 1)
```

#### count() and index()

Similar to lists, you can also count the index and number of occurences of an element in tuple.

**Code**

```python3
my_tuple = (1, 2, 3, 4, 5)

print(my_tuple.count(1))
print(my_tuple.index(1))
```

**Output**

```bash
1
0
```

### Tuple Swap

Let's say you want to interchange the values of two variables.

Ideally, you would need a 3rd temporary variable to achieve the objective.

**Code**

```python3
x = 10
y = 20
# Create a temp variable z
z = x
x = y
y = z

print(x, y)
```

**Output**

```bash
20 10
```

However, you can easily do this with Python without creating a 3rd temporary variable. The underlying concept is called a Tuple Swap.

**Code**

```python3
x = 10
y = 20

x, y = y, x
print(x, y)
```

**Output**

```bash
20 10
```

#### How Tuple Swap works?

Let's understand the mechanism behind Tuple Swap.

We know from the [section on creating tuples](https://www.pylenin.com/blogs/python-tuples/#how-to-create-a-tuple-in-python) that, Python can create a tuple without parenthesis.

**Code**

```python3
x = 1, 2, 3
print(x)
```

**Output**

```bash
(1, 2, 3)
```

Now notice the below code.

```python3
LHS    RHS
x, y = y, x
```

Python considers the `y, x` part as a tuple. It sees it as `(20, 10)`.

So the above assignment changes to `x, y = (20, 10)`

Now, Python unpacks the iterable into values of x and y.

So the values become interchanged. Check out this article on [unpacking iterables in Python](https://www.pylenin.com/blogs/unpacking-iterables-in-python/) to see how unpacking works.

### Lists vs Tuples

The major difference between lists and tuples is that tuples are immutable. 
So a tuple can't be changed through another reference elsewhere in the program. However, lists can be altered at any stage of the program.

There are also other noticeable differences like:-

1. Tuples can't be copied. `tuple(my_tuple)` returns you the same tuple. Lists can be copied.
2. Tuples occupy a smaller memory compared to lists as they are immutable. **This makes tuples a bit faster.**
3. Tuples are of fixed lengths. So you can't add or remove elements from a tuple.
4. You can't apply a lot of methods on Tuples. For example - To sort, you first have to convert a tuple to list.

If you're defining a constant set of values on which you are only going to iterate through, use a tuple instead of a list. **You can always convert it to a list later, when you need to.**