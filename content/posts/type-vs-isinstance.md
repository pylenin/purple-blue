---
title: "type() vs isinstance() in Python"
description: "Learn to check the data type of single and multiple objects with a tuple of possible data types in Python"
date: 2021-02-05T09:50:26+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

### Importance of type checking in Python

Python is a dynamically typed language. 
A variable can be assigned multiple values during the code lifetime.

```python3
x = "Pylenin" #string
x = 1992 #integer
x = [1, 2, 3] #list
```

So it is necessary to keep track of the data type that your variable is holding at a certain stage of the code.

That's where built-in functions like `type()` and `isinstance()` come into play.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

### Example 1 - Checking data type of a variable

**Code**

```python3
x = "Pylenin"

# Check type of x
print(type(x))

# Perform boolean comparison
# Using is operator
print(type(x) is str)
```

**Output**

```bash
<class 'str'>
True
True
```

The `isinstance()` function allows you to perform the above boolean comparison.

**Code**

```python3
x = "Pylenin"

# Using isinstance
print(isinstance(x, str))
```

**Output**

```bash
True
```

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

### Difference between `isinstance` and `type`

#### Difference 1 - Speed

The `isinstance()` function is faster than the `type` function. We can compare both their performance by using the [timeit library](https://www.pylenin.com/blogs/python-timeit-module/).

```bash
>>> python -m timeit -s "x = 'Pylenin'" "type(x) is str"
5000000 loops, best of 5: 60.4 nsec per loop

>>> python -m timeit -s "x = 'Pylenin'" "isinstance(x, str)"
5000000 loops, best of 5: 42.7 nsec per loop
```

As you can see, the **`isinstance()` function is 30 times faster than `type()` function**.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

#### Difference 2 - `isinstance` can check for subclass, `type` cannot

The `isinstance()` method can check if an object belongs to either a class or a **subclass**. `type` cannot check this.

**Code**
```python3
class Person:
    def __init__(self):
       self.type = "human"

class Pylenin(Person):
    
    name = "Pylenin"

myself = Pylenin()

print(type(myself) is Pylenin)
print(isinstance(myself, Pylenin))
```

**Output**

```bash
True
True
```

Since `myself` is an object of `Pylenin` class, both `type()` and `isinstance()` return **True**.

However, `Pylenin` inherits from `Person` class. It's the subclass of `Person` class.

So ideally, `myself` should also belong to `Person` class.

**Code**
```python3
class Person:
    def __init__(self):
       self.type = "human"

class Pylenin(Person):

    name = "Pylenin"

myself = Pylenin()

print(type(myself) is Person)
print(isinstance(myself, Person))
```

**Output**

```bash
False # type() returned False
True
```

As you can see, the `type()` function is unable to link `myself` object to the `Person` class. 

**So `type()` doesn't work with inheritance.**

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

### Why should you choose `isinstance` over `type`?

There are 2 reasons to choose `isinstance()` function over `type()`.

1. `isinstance()` is faster than `type()`.
2. `isinstance()` can deal with inheritance and `type()` cannot.

Learn more about the applications of [isinstance() function](https://www.pylenin.com/blogs/python-isinstance/) in Python.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>


