---
title: "Python program to find area of a triangle"
description: "Learn to find square roots of numbers in Python3"
date: 2021-01-08T19:49:42+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python Number Examples']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

According to [Heron's formula](https://en.wikipedia.org/wiki/Heron%27s_formula),
if `a`, `b` and `c` are the three sides of a triangle, the area of the triangle is:-

![Area of a triangle using Heron's formula](/img/python-examples/Area-of-Triangle.png)

where `s` is the semi-perimeter of the triangle.

#### Method 1

**Code**

```python3
a = 10
b = 12
c = 13

# calculate the semi-perimeter
s = (a + b + c) / 2

# calculate the area
area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
print('The area of our triangle is %0.2f' %area)
```

**Output**

```bash
The area of our triangle is 57.00
```

#### Method 2 - User Input

**Code**

```python3
a = float(input('Enter 1st side: '))
b = float(input('Enter 2nd side: '))
c = float(input('Enter 3rd side: '))

# calculate the semi-perimeter
s = (a + b + c) / 2

# calculate the area
area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
print('The area of our triangle is %0.2f' %area)
```

**Output**

```bash
Enter 1st side: 10
Enter 2nd side: 12
Enter 3rd side: 13
The area of our triangle is 57.00
```