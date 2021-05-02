---
title: "Python for loops (With Examples)"
description: "Learn to perform iterations on Python sequences using for loops with examples."
date: 2021-02-15T18:48:13+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python control flows']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

The `for` statement is used to iterate generic sequences in Python like lists, strings, dictionaries etc. 
In Python, the `for` statement iterates over the items in the order that they appear.

By using `for` loops you can automate the execution of a block of code 
for each item in the sequence.

### Syntax of for loop

```bash
for [iterating_variable] in [sequence]:
    [Do something with iterating_variable]
```



#### Example 1

**Code**

```python3
x = ["Pylenin", "loves", "Python"]

for word in x:
    print(word)
```

**Output**

```bash
Pylenin
loves
Python
```



### Python range() function

Let's say you want to create a sequence of numbers from 0 to 5 in Python. 
You can use the `range()` function to achieve this objective.

`range()` returns a sequence of numbers, starting with **0 by default**, 
increments each number by 1 (by default) 
and stops before the specified number.

**Syntax**

```bash
range(start, stop, step)

start - An integer number specifying the position to start. 
        Default is 0.(Optional)
stop - An integer number specifying the position to stop. 
       (Required)
step - An integer number specifying the incrementing value.
       Default is 1.(Optional)
```



#### Example 1

**Code**

```python3
x = range(0,5)

print(type(x))

for i in x:
    print(i)
```

**Output**

```bash
<class 'range'>
0
1
2
3
4
```

So a `range(0,5)` returns a `<class 'range'>` type object. 
When you iterate on it, it returns you a sequence of number from 0 to 4. 
The end number in `range()` is exclusive.

As per the syntax shown above, `range(0,5)` is same as `range(5)`. 
If you don't mention any starting number, it starts by default at 0.



#### Example 2 - Using a step with range()

Using steps in `range()` function, works similar to using steps in slicing strings.

**Code**

```python3
for i in range(0,5,2):
    print(i)
```

**Output**

```bash
0
2
4
```

With the **step** specified as 2, the range() function returns a sequence of numbers from 0(inclusive) to 5(exclusive), **containing every 2nd number**.

**You can also use a negative step**

**Code**

```python3
for i in range(10,5,-2):
    print(i)
```

**Output**

```bash
10
8
6
```


### Iterating over data types using for loop

Like discussed above, a `for` loop can step across any kind of sequence object.

You can easily iterate on every element of a list, tuple, string or dictionary using `for` loop. 
For e.g., the code below loops over te list and prints out the square of each number.

**Code - Iterating on list**

```python3
x = [1, 2, 3, 4]

for i in x:
    print(i**2)
```

**Output**

```bash
1
4
9
16
```



You can also add the squares of each number to another list.

**Code - Iterating on list**

```python3
x = [1, 2, 3, 4]
new_list = []

for i in x:
    new_list.append(i**2)

print(new_list)
```

**Output**

```bash
[1, 4, 9, 16]
```

You can also iterate on other data types like strings, tuples and sets in a similar fashion.

**Code**

```python3
# for loop on strings
str1 = "Pylenin"

for s in str1:
    print(s, end =" ")
print()

# for loop on tuples
my_tuple = ("Pylenin", "loves", "Python")

for elem in my_tuple:
    print(elem, end=" ")
print()

# for loops on sets
my_set = {1, 2, 3, 4, 5, 6, 7, 8}

for elem in my_set:
    print(elem, end = " ")
```

**Output**

```bash
P y l e n i n 
Pylenin loves Python 
1 2 3 4 5 6 7 8 
```



### Iterating over a dictionary

You can also iterate over a [dictionary](https://www.pylenin.com/blogs/python-dictionary/) using for loops.

You can iterate through dictionaries in 4 different ways.

1. Iterate over the dictionary itself.
2. Iterate over the keys - `dict.keys()`
3. Iterate over the values - `dict.values()`
4. Iterate over both keys and values - `dict.items()`

#### Iterating over the dictionary 

Iterating over a dictionary using `for` loop returns you the 
keys of a dictionary.

**Code**

```python3
my_dict = {
    "name" : "Pylenin",
    "language" : "Python",
    "DOB" : 1992
}

for item in my_dict:
    print(item)
```

**Output**

```bash
name
language
DOB
```



#### Iterate over the dictionary keys - `dict.keys()`

Another way to iterate over the keys in a dictionary, is by using 
the `dict.keys()` method.

**Code**

```python3
my_dict = {
    "name" : "Pylenin",
    "language" : "Python",
    "DOB" : 1992
}

for item in my_dict.keys():
    print(item)
```

**Output**

```bash
name
language
DOB
```



#### Iterate over the dictionary values - `dict.values()`

To iterate over the values in a dictionary, you can use `dict.values()` methods.

**Code**

```python3
my_dict = {
    "name" : "Pylenin",
    "language" : "Python",
    "DOB" : 1992
}

for item in my_dict.values():
    print(item)
```

**Output**

```bash
Pylenin
Python
1992
```



#### Iterate over the dictionary keys and values - `dict.items()`

To iterate over both the dictionary keys and values, use the `dict.items()` method.

**Code**

```python3
my_dict = {
    "name" : "Pylenin",
    "language" : "Python",
    "DOB" : 1992
}

print(my_dict.items())

for key, value in my_dict.items():
    print(key, value)
```

**Output**

```bash
dict_items([('name', 'Pylenin'), ('language', 'Python'), ('DOB', 1992)])

name Pylenin
language Python
DOB 1992
```



### Nested for loops

You can also have a `for` loop within another `for` loop in Python. This is called a **Nested for loop**.

Let's try to find the common elements of 2 lists. One way to achieve this objective would be to do it using [sets](https://www.pylenin.com/blogs/python-sets/).

We could also do it using `for` loops.

**Code**

```python3
list1 = [1, 2, 3, 4]
list2 = [4, 5, 6, 7]

for i in list1:
    for j in list2:
        if i == j:
            print(f"{i} exists in both lists")
```

**Output**

```bash
4 exists in both lists
```

Now, the above code is not the most efficient way of achieving the objective.
You should use a `break` keyword in there to stop iteration, once the element has been found.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).

