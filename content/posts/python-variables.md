---
title: "Understanding Variables in Python 3"
description: "Learn about declaring and using variables in Python 3."
date: 2021-01-23T19:36:36+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Getting Started with Python']
categories_weight: 6
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### What is a Variable in Python?

A variable in Python is a reserved memory location that stores values.

**Python is a dynamically typed language**. 
Unlike statically typed languages like C and C++, 
the **data type of a variable in Python is defined at runtime**. 

Also, in Python, a variable can store different data types during 
its lifetime. 
This is different for statically typed languages, 
where you have to declare a variable with a specific data type, 
and values assigned to it during its lifetime must always have the same type.

**Code**

```python3
# Store a string
x = "Pylenin"
print(x)

# Store an integer
x = 10
print(x)

# Store a float
x = 3.5
print(x)

# Store a list
x = [1, 2, 3]
print(x)
```

You can run the above code and the output will look like the below.

**Output**

```bash
Pylenin
10
3.5
[1, 2, 3]
```

Basically, you can change the content and data type of variable during the course of a program.

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

#### Chained Assignment of Variables

In Python, you can also perform chained assignments, 
which makes it possible to assign the same value to 
several variables simultaneously:

**Code**

```python3
x = y = z = 100
print(x, y, z)
```

**Output**

```bash
100, 100, 100
```

#### Variable Assignment - What happens behind the scenes?

```python3
x = "Pylenin"
```

When you make the above assignment, Python creates a [string object](https://www.pylenin.com/categories/python-strings/) and **assigns the variable `x` to point to the string object**.

**Code**

```python3
x = "Pylenin"
print(type(x))
```

**Output**

```bash
<class 'str'>
```

**Now what happens, if you run the following code?**

**Code**

```python3
x = "Pylenin"
print(type(x))

y = x
```

Now there is another variable `y` in our code and that is set equal to `x`.
When you run the code, **Python won't create a new variable**. 
It will create a symbolic reference `y` that points to the same string object.

You can confirm this by **finding the id** of both the variables. Whenever an object is created in Python, it is assigned an unique identity.
You can find the id of variables, by using the `id()` built-in function.
**Code**

```python3
x = "Pylenin"
print(type(x))

y = x
print(id(y), id(x))
```

**Output**

```bash
<class 'str'>
1957481302640 1957481302640
```

As you can see, both `x` and `y` have the same id.