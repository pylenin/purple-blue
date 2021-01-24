---
title: "Python program to convert degree to radian"
description: "Learn to convert degrees to radians in Python 3"
date: 2021-01-24T06:57:35+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python Number Examples']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Objective

Write a Python program to **convert degrees to radians**.

#### What is a Radian?

![What is Radian?](/img/python-examples/radian.png)

A radian is measure of the central angle of a circle, whose arc length is the same as the radius of the circle.

**1 radian is equal to 57.3 degrees**.

#### Method 1

**Code**

```python3
pi = 22/7
degrees = 5

radians = degrees * pi / 180
print(radians)
```

**Output**

```bash
0.0873015873015873
```

#### Method 2 - Asking user input

**Code**

```python3
pi = 22/7
degrees = float(input("Input degrees ==> "))

radians = degrees * pi / 180
print(radians)
```

**Output**

```bash
Input degrees ==> 23
0.40158730158730155
```

#### Method 3 - Using the `math` module

You can also use the `degrees` and `radians` functions from the `math` module.

1. Use `degrees` function to convert radians to degrees.
2. Use `radians` function to convert degrees to radians.

##### Converting degrees to radians

**Code/Output**

```python3
import math

#0 radians == 0 degrees
math.degrees(0)
>>> 0.0

#pi/2 radians is 90 degrees
math.degrees(math.pi/2)
>>> 90.0

#pi radians is 180 degrees
math.degrees(math.pi)
>>> 180.0      

#pi+pi/2 radians is 270 degrees
math.degrees(math.pi+(math.pi/2))
>>> 270.0 

#2*pi radians is 360 degrees
math.degrees(math.pi+math.pi)
>>> 360.0   
```

##### Converting radians to degrees

**Code/Output**

```python3
#  Converting radians to degrees
import math

#0 degrees == 0 radians
math.radians(0)
>>> 0.0

#90 degrees is pi/2 radians
math.radians(90)
>>> 1.5707963267948966

#180 degrees is pi radians
math.radians(180)
>>> 3.141592653589793

#270 degrees is pi+(pi/2) radians
math.radians(270)
>>> 4.71238898038469

#360 degrees is 2*pi radians
math.radians(360)
>>> 6.283185307179586
```
