---
title: "Python Lists (With Examples)"
description: "Learn to create and use lists data type in Python 3 with examples."
date: 2021-02-07T08:21:32+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python lists']
categories_weight: 1
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Python offers a variety of data types. 
List is one of the most frequently used data types in Python.

### Characteristics of Python Lists

1. Python lists can contain any data type of your choice, e.g., String, Integers, Python objects etc.
2. Lists can also contain lists. They are called **Nested Lists**.
3. **Lists are mutable**. This means, you can alter the contents of a list anytime during the program.
4. The sequence in which data is stored in a list is preserved.

The above characteristics make Python lists very powerful and versatile.

### How to create a list in Python?

To create an empty list, you can directly call the `list()` constructor.
You can also declare an empty list with empty square brackets `[]`.

**Code**

```python3
my_list = list()
print(my_list)

my_second_list = []
print(my_second_list)
```

**Output**

```bash
[]
[]
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


To create a **non-empty list**, you can place all the items 
within the square brackets `[]`.

**Code**

```python3
my_list = [1, 2, 3]
print(my_list)

another_list = ["Pylenin", 1, "loves", "Python"]
print(another_list)

my_nested_list = ["Pylenin", [1, 2, 3]]
print(my_nested_list)
```

**Output**

```bash
[1, 2, 3]
["Pylenin", 1, "loves", "Python"]
["Pylenin", [1, 2, 3]]
```

The nested lists are also called Multi dimensional lists.

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


### Access elements of a list

The process for accessing elements from a list, work similar to strings.

You can access individual elements of a list using **indexing** 
and a range of elements using **slicing**. 
In Python lists, index starts from 0 and keeps increasing by 1 
with every element in the list. 
This is called Positive Indexing(or indexing from the beginning). 
If there are __**n**__ elements in a list, the 1st element will have 
index of **0** and the last element will have index **n-1**.

Let’s look at the image below for better understanding.

![Positive Indexing of Lists in Python](/img/python-lists/positive-indexing-list.png)

**Python also allows negative indexing for lists(indexing from the end).** 
If there are __**n**__ elements in a list, the last element will have index 
of **-1** and the first element will have index __**-n**__.

Let's look at the image below for better understanding.

![Indexing Lists in Python](/img/python-lists/list-indexing.png)

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# first character
print('my_list[0] =', my_list[0])

# last character
print('my_list[-1] =', my_list[-1])

# second character
print('my_list[1] =', my_list[1])

# second last character
print('my_list[-2] =', my_list[-2])
```

**Output**

```bash
my_list[0] = 1
my_list[-1] = 5
my_list[1] = 2
my_list[-2] = 4
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


If you try to access an element out of range, it will raise an `IndexError`. 

Also, the index must be an **integer**. You can't use floats or other types for indexing. This will result in `TypeError`.

**Code/Output**

```python3
my_list = [1, 2, 3, 4, 5]

print(my_list[10])
>>> IndexError: list index out of range

print(my_list[3.5])
>>> TypeError: list indices must be integers or slices, not float
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


### Slicing of Lists

To access a range of elements from a Python list, 
you need to use **slicing**. 

Basically, you have to specify the starting index and the ending index, 
separated by a colon(`:`), to return a range of elements from the list.

#### Slicing Lists with Positive Index

![Slicing Lists in Python](/img/python-lists/list-slicing.png)

**Remember** - The last index is not included.

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


Let's say you want to access the 1st and the 2nd index from a list.
In that case, **your end index will be 3**.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

print(my_list[1:3])
```

**Output**

```bash
[2, 3]
```

If you leave out the start index, the range will start at the first element.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# leave out the first index
print(my_list[:3])
```

**Output**

```bash
[1, 2, 3]
```

If you leave out the end index, the range will go to the end.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# leave out the end index
print(my_list[1:])
```

**Output**

```bash
[2, 3, 4, 5]
```

So, if you leave out both the start and end index, **you will get a replica of the original list**.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# leave out the start and end index
print(my_list[:])
```

**Output**

```bash
[1, 2, 3, 4, 5]
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


#### Slicing Lists with Negative Index

You can also use negative index for slicing. 
Just use the negative index counterpart of your positive index to sice a list.

![Slicing Lists with negative index in Python](/img/python-lists/negative-list-slicing.png)

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# Slicing with Positive Index
print(my_list[1:3])
# Slicing with Negative Index
print(my_list[-4:-2])
```

**Output**

```bash
[2, 3]
[2, 3]
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


#### Mixing positive and negative indices for slicing

You can also mix positive and negative indices while slicing a list.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

print(my_list[1:-1])
print(my_list[-3:5])
```

**Output**

```bash
[2, 3, 4]
[3, 4, 5]
```

Let's understand the above example using the below image.

![Mixing positive and negative indices for slicing in Python](/img/python-lists/positive-negative-slicing.png)

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


#### Using steps in slicing

You can also include **steps** while slicing your list. 
The step allows you to take every `nth` element while slicing.

**Syntax**

```bash
list[start:stop:step]
```

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# Get every second element
# from beginning to end
print(my_list[::2])

# Get every second element
# starting at index 1 till end
print(my_list[1::2])

# Get every second element
# starting at index 1 upto -2 index
print(my_list[1:-2:2])
```

**Output**

```bash
[1, 3, 5]
[2, 4]
[2]
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


#### Reversing a list

Negative step changes the slice **to be built from the tail of the list**. 
So, it goes from the last element to the first element. 
This way, we get a **reversed list**.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

print(my_list[::-1])
```

**Output**

```bash
[5, 4, 3, 2, 1]
```

When using a negative step, the start and stop values have to be provided from right to left (usually it is from left to right).

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# Reverse the list
# without the last element
print(my_list[-2::-1])

# Reverse the list
# without the first and last element
print(my_list[-2:0:-1])
```

**Output**

```bash
[4, 3, 2, 1]
[4, 3, 2]
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


### Changing elements of a list

Since **lists are mutable**, you can easily update or change the contents of a list.
You can either change one element or change a range of elements of the list.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# change the 1st element
my_list[0] = "Pylenin"
print(my_list)

# change 2nd to 5th element
my_list[1:4] = [10, 20, 30]
print(my_list)
```

**Output**

```bash
['Pylenin', 2, 3, 4, 5]
['Pylenin', 10, 20, 30, 5]
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


### Adding elements to a list

You can add elements to list using **concatenation** or 
by using built-in methods like `append()`, `extend()` or `insert()`.

#### Adding elements to a list by concatenation

**Code**

```python3
my_list = [1, 2, 3, 4, 5]
new_list = ["Pylenin", "loves", "Python"]

# Using + operator
print(my_list + new_list)

# Using * operator
print(my_list*2)
```

**Output**

```bash
[1, 2, 3, 4, 5, 'Pylenin', 'loves', 'Python']
[1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
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


#### Python list append

You can add one element to a list by using the `append()` built-in method.

**Code**

``python3
my_list = [1, 2, 3, 4, 5]

my_list.append(10)
print(my_list)

my_list.append([10, 20])
print(my_list)
``

**Output**

```bash
[1, 2, 3, 4, 5, 10]
[1, 2, 3, 4, 5, 10, [10, 20]]
```

f you try to add more than one element with `append()`, it throws a `TypeError`.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

my_list.append(10, 20)
print(my_list)
```

**Output**

```bash
TypeError: list.append() takes exactly one argument (2 given)
```

To add multiple elements to the list, you can use `extend()` method.

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


#### Python list extend

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

my_list.extend([10, 20, 30])
print(my_list)
```

**Output**

```bash
[1, 2, 3, 4, 5, 10, 20, 30]
```

**Note:-** You have to pass in all the elements in the form of a list.

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


#### Python list insert

Both `append()` and `extend()` methods, add elements to the end of a list. **To add elements at a certain position (specific index) in the list**, you can use the `insert()` method.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

# Insert 10 at 2nd index
my_list.insert(2, 10)
print(my_list)

# Insert 10 at 10th index
my_list.insert(10, 10)
print(my_list)
```

**Output**

```bash
[1, 2, 10, 3, 4, 5]
[1, 2, 10, 3, 4, 5, 10]
```

In the 2nd example, you can see that when **trying to insert an element at a non-existing index**, Python just inserts it as the last element of the list.

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


### Deleting elements from a list

#### Python list del statement

You can delete an element of a list or an entire list using the `del` statement.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

del my_list[0]
print(my_list)

del my_list
print(my_list)
```

**Output**

```bash
[2, 3, 4, 5]
Traceback (most recent call last):
  File "C:\Users\91824\PycharmProjects\pythonProject\trial.py", line 7, in <module>
    print(my_list)
NameError: name 'my_list' is not defined
```

Since`my_list` was deleted, Python threw an error `ame 'my_list' is not defined`.

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


#### Python list clear

If you don't want to delete the list, but just **clear the list of its contents**, you can use the `clear()` built-in method.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

my_list.clear()
print(my_list)
```

**Output**

```bash
[]
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


#### Python list pop

To **remove an element from the list and return the removed element**, use the `pop()` method.

**Syntax of pop**

```bash
list.pop(index)

index: index of the element 
       to be removed(Optional)
Returns the removed element
```

If index is not provided, `pop()` removes and returns the last element of the list.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

print(my_list.pop())
print(my_list)
```

**Output**

```bash
5
[1, 2, 3, 4]
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


#### Python list remove

If you are sure of the kind of content existing in the list, you can also use the `remove()` method to remove that particular element.

**Code**

```python3
my_list = [1, 2, 3, 4, 5]

my_list.remove(3)
print(my_list)

# Trying to remove a non existent element
my_list.remove(10)
```

**Output**

```bash
[1, 2, 4, 5]

Traceback (most recent call last):
  File "some_file_location", line 6, in <module>
    my_list.remove(10)
ValueError: list.remove(x): x not in list
```

If the element you are trying to remove doesn't exist in the list, Python throws a `ValueError`.

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

### Common Python list Methods

#### Python list count

The `count()` method in Python returns the number of occurences 
of a particular element in the list.

**Code**

```python3
my_list = [1, 2, 3, 4, 5, 1]

print(my_list.count(1))
```

**Output**

```bash
2
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


#### Python list index

The `index()` method returns the **first matched index** of a particular element in the list.

**Syntax of index()**

```bash
list.index(element, start, stop)

element - the element to be searched
start (optional) - start searching from this index
end (optional) - search the element upto this index (Not included)
```

**Code**

```python3
my_list = [1, 2, 3, 4, 5, 1]

print("Index of 1 from beginning is, ",my_list.index(1))

print("Index of 1 from 1st index is, ",my_list.index(1, 1))

print("Index of 1 between 1st and 5th index is, ",my_list.index(1, 1, 5))
```

**Output**

```bash
Index of 1 from beginning is,  0
Index of 1 from 1st index is,  5

Traceback (most recent call last):
  File "some_file_location", line 7, in <module>
    print("Index of 1 between 1st and 5th index is, ",my_list.index(1, 1, 5))
ValueError: 1 is not in list
```

Your end index is not inclusive of the search result. In the above case, 
**the end index should be 6** to return the index of 1.

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


#### Python list len

The `len()` function calculates the length of any given list.

**Code**

```python3
my_list = [1, 2, 3, 4, 5, 1]

print(f"The length of list is {len(my_list)}")
```

> The above code uses [f-strings](https://www.pylenin.com/blogs/f-strings-python/)

**Output**

```bash
The length of list is 6
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


#### Python list sort

The `sort()` method in Python sorts the list in an ascending or descending order **based on the provided key**.

**Syntax of sort()**

```bash
list.sort(key, reverse)

key(Optional): The key on which sorting will happen.
reverse(Optional): The default value is False.
                   When set to True, it sorts in descending order.
```

**Code**

```python3
my_list = [1, 4, 3, 2, 5]

#Sort in ascending order
my_list.sort()
print(my_list)

#Sort in descending order
my_list.sort(reverse=True)
print(my_list)
```

**Output**

```bash
[1, 2, 3, 4, 5]
[5, 4, 3, 2, 1]
```

It also works on strings.

**Code**

```python3
my_list = ["a", "i", "e", "u", "o"]

#Sort in ascending order
my_list.sort()
print(my_list)

#Sort in descending order
my_list.sort(reverse=True)
print(my_list)
```

**Output**

```bash
['a', 'e', 'i', 'o', 'u']
['u', 'o', 'i', 'e', 'a']
```

Let's say you have a list containing strings and you would like to sort them based on length of each string. You can use the `key` parameter to achieve this objective.

**Code**

```python3
my_list = ["Pylenin", "loves", "Python"]

#Sort in ascending order of length
my_list.sort(key=len)
print(my_list)

#Sort in descending order of length
my_list.sort(key=len, reverse=True)
print(my_list)

```

**Output**

```bash
['loves', 'Python', 'Pylenin']
['Pylenin', 'Python', 'loves']
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


#### Python list reverse

The `reverse()` method in Python reverses the order of the list.

**Code**

```python3
my_list = ["Pylenin", "loves", "Python"]

#Reverse the list
my_list.reverse()
print(my_list)
```

**Output**

```bash
['Python', 'loves', 'Pylenin']
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

#### Python list copy

The `copy()` method in Python returns a shallow copy of the list. 
It is better than using the `=` operator **as any changes to the 
copied list is not reflected in the original list**.


**Code - Copy list using =**

```python3
my_list = ["Pylenin", "loves", "Python"]
new_list = my_list

new_list.append("3")

print(new_list)
print(my_list)
```

**Output**

```bash
['Pylenin', 'loves', 'Python', '3']
['Pylenin', 'loves', 'Python', '3']
```

As you can see, `'3'` was appended to both the `new_list` and `my_list`.

To avoid this, you can use the `copy()` method.

**Code - using copy()**

```python3
my_list = ["Pylenin", "loves", "Python"]
new_list = my_list.copy()

new_list.append("3")

print(new_list)
print(my_list)
```

**Output**

```bash
['Pylenin', 'loves', 'Python', '3']
['Pylenin', 'loves', 'Python'] # old list stayed the same
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

