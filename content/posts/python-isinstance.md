---
title: "Python isinstance() function"
description: "Learn to check the data type of single and multiple objects with a tuple of possible data types in Python"
date: 2021-02-05T09:50:26+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

The `isinstance()` function in Python 
checks if the object (first argument) 
is a subclass of the second argument.

### Syntax of isinstance()

```bash
isinstance(object, classinfo)

Returns True or False
```


### Example 1 - Check for integers with isinstance()

**Code/Output**

```python3
print(isinstance(1992, int))
>> True
```

### Example 2 - Check for floats with isinstance()

**Code/Output**

```python3
print(isinstance(2.0, float))
>> True
```

### Example 3 - Check for complex numbers with isinstance()

**Code/Output**

```python3
print(isinstance(2 + 3j, complex))
>> True
```

### Example 4 - Check for lists with isinstance()

**Code/Output**

```python3
print(isinstance([1, 2, 3], list))
>> True
```

### Example 4 - Check for dictionary with isinstance()

**Code/Output**

```python3
print(isinstance({"name":"Pylenin"}, dict))
>> True
```

### Example 5 - Check for tuples with isinstance()

**Code/Output**

```python3
print(isinstance((1, 2, 3), tuple))
>> True
```

### Example 6 - Check for sets with isinstance()

**Code/Output**

```python3
print(isinstance({1, 2, 3}, set))
>> True
```

### Example 7 - Check for strings with isinstance()

**Code/Output**

```python3
print(isinstance("Pylenin", str))
>> True
```

### Example 7 - Check for User defined Class with isinstance()

**Code/Output**

```python3
class Pylenin:
    
    def __init__(self):
        self.name = "Pylenin"

myself = Pylenin()
print(isinstance(myself, Pylenin))
>> True
```

### Example 9 - Python isinstance with multiple types

If you are unsure, you can also check your object with multiple class types. 
To do this, you need to mention all types in a tuple and 
pass it as the `classinfo` argument of `isinstance()`.

**Code/Output**

```python3
print(isinstance("Pylenin", (str, int)))
>> True

# When the object doesn't belong
# to any class in the tuple
print(isinstance("Pylenin", (list, int)))
>>> False
```

### How to check if multiple variables are a single type in Python?

You can use `all()` function along with `isinstance()` to check if multiple variables 
belong to the same type.

**Code**

```python3
x = "Pylenin"
y = 10
z = 3.5

if not all(isinstance(i, int) for i in list((x, y, z))):
    print("All variables are not integer")
else:
    print("All variables are integer")
```

**Output**

```bash
All variables are not integer
```
