---
title: "Python Sets (With Examples)"
description: "Learn to create and use sets data type in Python 3 with examples."
date: 2021-02-10T16:21:32+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python sets']
categories_weight: 1
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Sets are an **unordered collection of unique and immutable objects**. 
It supports mathematical operations from the set theory.

An item appears only once in a set, no matter how many times it is added.

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

### How to create a set?

You can use the `set()` construct with iterables or 
use curly braces `{}` to create a set in Python.

**Code**

```python3
# EMpty set
x = set()
print(x)

# Using iterables
x = set("Pylenin")
print(x)

x = set([1, 2, 3, 4])
print(x)

# Using curly braces
x = {1, 2, 3, 4}
print(x)
```

**Output**

```bash
set()
{'l', 'y', 'e', 'P', 'i', 'n'}
{1, 2, 3, 4}
{1, 2, 3, 4}
```

You cannot declare a set by using empty curly braces. Python will assume its a **dictionary**.

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

### Mathematical operations with sets

#### Set membership test

You can use the `in` operator to check if an element exists in a set.

**Code**

```python3
x = {1, 2, 3, 4}

if 1 in x:
    print("Element exists")
else:
    print("Element doesn't exist")
```

**Output**

```bash
Element exists
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

#### Difference between 2 sets

![Python Sets - Difference](/img/python-sets/set-difference.png)

In mathematical set theory, the difference of two sets(A & B) is 
`A - B`. It is the set of all elements of A that are not 
elements of B. You can perform the same operation in Python

**Code**

```python3
x = {1, 2, 3, 4}
y = {2, 3, 4, 5}

print(x - y)
print(y - x)
```

**Output**

```bash
{1}
{5}
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

#### Union of 2 sets

![Python Sets - Union](/img/python-sets/set-union.png)

The union of two sets A and B is the set of elements 
which are in A, B or in both A and B.

**Code**

```python3
x = {1, 2, 3, 4}
y = {2, 3, 4, 5}

print(x | y)
```

**Output**

```bash
{1, 2, 3, 4, 5}
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

#### Intersection of 2 sets

![Python Sets - Intersection](/img/python-sets/set-intersection.png)

The intersection of two sets A and B are the set of elements 
which are in both A and B.

**Code**

```python3
x = {1, 2, 3, 4}
y = {2, 3, 4, 5}

print(x & y)
```

**Output**

```bash
{2, 3, 4}
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

#### Symmetric difference of sets

![Python Sets - Symmetric Difference](/img/python-sets/set-symmetric-difference.png)

The symmetric difference of two sets A and B are the set of elements 
which are in A and B, but not common to A and B.

**Code**

```python3
x = {1, 2, 3, 4}
y = {2, 3, 4, 5}

print(x ^ y)
```

**Output**

```bash
{1, 5}
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

### Using methods with sets

#### Adding elements to sets

To add elements to a set, you can use the `add()` method.

**Code**

```python3
x = {1, 2, 3, 4}

x.add(10)
print(x)
```

**Output**

```bash
{1, 2, 3, 4, 10}
```

With `add()` method, you can add only a single element. 
To add multiple elements, use the `update()` method.

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

#### Adding multiple elements to sets with update()

**Code**

```python3
x = {1, 2, 3, 4}

x.update([4, 5, 6, 7])
print(x)

x.update(["Pylenin", "Python"], {"greeting"})
print(x)
```

**Output**

```bash
{1, 2, 3, 4, 5, 6, 7}
{1, 2, 3, 4, 5, 6, 7, 'Python', 'Pylenin', 'greeting'}
```

Duplications are always avoided with sets.

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

#### Remove an element from a set

To remove an element from a set, use `remove()` method.

**Code**

```python3
x = {1, 2, 3, 4}

x.remove(2)
print(x)
```

**Output**

```bash
{1, 3, 4}
```

If the element you are trying to remove doesn't exist, 
Python will throw a `KeyError`.

To avoid getting such errors, use the `discard()` method with sets.

**Code/Output**

```python3
x = {1, 2, 3, 4}

x.discard(20)
print(x)
>>> {1, 2, 3, 4}

x.remove(20)
print(x)
>>> KeyError: 20
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

#### Remove multiple elements from a set

To remove multiple elements from a set, use the `clear()` method.

**Code**

```python3
x = {1, 2, 3, 4}

x.clear()
print(x)
```

**Output**

```bash
set()
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