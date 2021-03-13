---
title: "Python List Comprehension (With Examples)"
description: "Learn to create and use lists comprehensions in Python 3 with examples."
date: 2021-03-06T07:54:43+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python lists']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Pre-requisites**

[Python Lists](https://www.pylenin.com/blogs/python-lists/) and Understanding Manual Iteration - __iter__ and __next__

1. [Sequence vs Iterable vs Iterator](https://www.pylenin.com/blogs/python-iterators/#difference-between-sequence-and-an-iterable)
2. [next() in Python](https://www.pylenin.com/blogs/python-iterators/#next-in-python)
3. [for loop - Behind the scenes](https://www.pylenin.com/blogs/python-iterators/#for-loop-behind-the-scenes)
4. [A file object is an iterator](https://www.pylenin.com/blogs/python-iterators/#is-a-file-object-an-iterator)
5. [Unpacking an iterable in Python](https://www.pylenin.com/blogs/unpacking-iterables-in-python/)

## Youtube Video

<br>
{{< youtube id="40S9e5Rf384" >}}
<br>

## List Comprehensions

Along with [for loops](https://www.pylenin.com/blogs/python-iterators/#for-loop-behind-the-scenes), 
list comprehensions are one of the most useful contexts in which the iteration protocol is applied.

With the help of list comprehensions, you can write code that is shorter 
and more efficient.

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

### Example 1

**Code**

```python3
# using for loop
my_list = [10, 20, 30, 40]
for i in range(len(my_list)):
    my_list[i] *= 2
print(my_list)

# using list comprehension
my_list = [10, 20, 30, 40]
new_list = [x*2 for x in my_list]
print(new_list)
```

**Output**

```bash
[20, 40, 60, 80]
[20, 40, 60, 80]
```

As you can see, you are able to replace the loop with a 
single expression that produces the desired result list.

**Note:-** List comprehensions aren't exactly same as 
the for loop statement version because it makes a new list object.

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

### Example 2

**Code**

```python3
# using for loop
squares_list = []
for i in range(10):
    squares_list.append(i**2)
print(squares_list)

# using list comprehensions
squares_list = []
new_squares_list = [i**2 for i in range(10)]
print(new_squares_list)
```

**Output**

```bash
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
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

## Understanding list comprehensions syntax

Usual syntax of a list comprehension is 

```bash
[expression for item in iterable]
```

Let's dissect the previous example to understand the syntax of list comprehensions.

**Code**

```python3
squares_list = []
new_squares_list = [i**2 for i in range(10)]
print(new_squares_list)
```

As you can see, list comprehensions are written in square 
brackets as they are used to create a new list. They begin 
with an expression which uses a loop variable `i**2`(`i` is the loop variable and `i**2` is the expression). 
This is followed by the header of a `for loop`, which names the 
loop variable and an iterable object `for i in range(10)`.

If you notice carefully, **the syntax of list comprehension looks like
a backwards for loop**.

## Using conditions in List comprehensions

Similar to using `if-elif-else` conditions in for loops, 
list comprehensions can also use conditionals.

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

### Example 3

Let's write a Python program to add even numbers to a list from `range(10)`.

**Code**

```python3
# using for loops
my_list = []
for i in range(10):
    if i%2 ==0:
        my_list.append(i)
print(my_list)

#using list comprehensions
my_list = [i for i in range(10) if i%2==0]
print(my_list)
```

**Output**

```bash
[0, 2, 4, 6, 8]
[0, 2, 4, 6, 8]
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

### Example 4 - if else in a list comprehension

Notice how the `if` clause in the previous example comes after the iterable(`range(10)`). 
If you want to include both `if else` conditions in list comprehensions, you have to move the 
conditionals **before the iterable**.

Let's look at this below example.

**Code**

```python3
# using for loop
my_list = [2, 5, 8, 11, 15]
for i in range(len(my_list)):
    if my_list[i] < 10:
        my_list[i] *=2
    else:
        my_list[i] += 1
print(my_list)

# using list comprehension
my_list = [2, 5, 8, 11, 15]
new_list = [x*2 if x < 10 else x+1 for x in my_list]
print(new_list)
```

**Output**

```bash
[4, 10, 16, 12, 16]
[4, 10, 16, 12, 16]
```

Notice how `if x < 10 else x+1` comes before `for x in my_list`.

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

### Example 5 - Nested if with List comprehension

Let's write a Python program to append numbers that are 
**divisible by both 2 and 5** between 2 sets of integers.

**Code**

```python3
# using for loops
my_list = []
for i in range(1, 30):
    if i%2 ==0:
        if i%5==0:
           my_list.append(i)
print(my_list)

# using list comprehension
my_list = [i for i in range(1, 30) if i%2==0 if i%5==0]
print(my_list)
```

**Output**

```bash
[10, 20]
[10, 20]
```

Here list comprehension checks 
1. if `i` is divisible by 2, and then,
2. if `i` is divisible by 5.

If `i` is divisible by both, it is appended to the `my_list` variable.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).

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