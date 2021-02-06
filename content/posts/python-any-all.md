---
title: "Python any() vs all() functions"
description: "Learn to perform AND/OR operations using any() and all() built-in function in Python."
date: 2021-02-05T09:50:26+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

In this article, you will learn about the `any()` and `all()` built-in functions in Python.
These built-in functions perform the `OR` and `AND` operation respectively.

### Understanding and/or operator

Before jumping into `any()` and `all()` functions, let's understand how the **and/or** operator works in Python.

#### and operator in Python

The `and` operator returns `True`, if **all the conditions are True**.

**Code/Output**

```python3
print((2==2) and ("Pylenin" == "Pylenin"))
>>> True

print((2==2) and ("Pylenin" == "Python"))
>>> False
```

In the second print statement, since `Pylenin` and `Python` are not the same, the `and` operator returns **False**.

You can also compare booleans.

**Code/Output**

```python3
print(True and True)
>>> True

print(True and False)
>>> False

print(False and False)
>>> False
```

It is also possible to chain multiple `and`s in a single statement.

**Code/Output**

```python3
print(True and True and True)
>>> True

print(True and False and True and True)
>>> False
```

#### or operator in Python

The `or` operator returns `True`, if **any of the conditions is True**.

**Code/Output**

```python3
print((2==2) or ("Pylenin" == "Pylenin"))
>>> True

print((2==2) or ("Pylenin" == "Python"))
>>> True
```

In the second print statement, even though `Pylenin` and `Python` 
are not the same, the `or` operator returns **True**, because the previous comparison holds True.

You can also compare booleans.

**Code/Output**

```python3
print(True or True)
>>> True

print(True or False)
>>> True

print(False or False)
>>> False
```

It is also possible to chain multiple `or`s in a single statement.

**Code/Output**

```python3
print(True or True or True)
>>> True

print(True or False or True or True)
>>> True
```

### Python all()

The `all(iterable)` built-in function takes in an iterable and returns True, 
if **all the elements of the iterable evaluate to True**.

It is similar to the `and` operator.

**Code/Output**

```python3
print(all([True, True, True]))
>>> True

print(all([True, True, False]))
>>> False

print(all([1992==1992, type(1992) is int]))
>>> True
```

#### Check if multiple variables are of single data type in Python

You can use `all()` function along with [isinstance()](https://www.pylenin.com/blogs/python-isinstance/) 
to check if multiple variables belong to the same type.

**Code**

```python3
x = "Pylenin"
y = 10
z = 3.5

# Check if all variables are integer
if not all(isinstance(i, int) for i in list((x, y, z))):
    print("All variables are not integer")
else:
    print("All variables are integer")
```

**Output**

```bash
All variables are not integer
```

### Python any()

The `all(iterable)` built-in function takes in an iterable and returns True, 
if **any of the elements of the iterable evaluate to True**.

It is similar to the `or` operator.

**Code/Output**

```python3
print(any([True, True, True]))
>>> True

print(any([True, True, False]))
>>> True

print(any([1992==1992, type(1992) is str]))
>>> True
```

#### Check if any variables are of particular data type in Python

You can use `any()` function along with [isinstance()](https://www.pylenin.com/blogs/python-isinstance/) 
to check if any variables belongs to a particular data type.

**Code**

```python3
x = "Pylenin"
y = 10
z = 3.5

# Check if any variable is integer
if not any(isinstance(i, int) for i in list((x, y, z))):
    print("There are no integers")
else:
    print("There are integers")
```

**Output**

```bash
There are integers
```

**Note** - Use `any()` and `all()` only when they make the code shorter and maintain  readability.