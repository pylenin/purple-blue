---
title: "Python program to print Pyramid patterns"
description: "Learn how to print various pyramid patterns in Python."
date: 2021-02-19T08:39:38+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*


## Pyramid Pattern #1

```bash
Objective:-

* 
* * 
* * * 
* * * * 
* * * * * 
* * * * 
* * * 
* * 
*
```

You can build this pattern by simply using [for loops](https://www.pylenin.com/blogs/python-for-loop/) and [range](https://www.pylenin.com/blogs/python-for-loop/#python-range-function).

**Code**

```python3
n = 5

for i in range(1, n+1):
    print(i*'* ')
for i in range(n-1, 0, -1):
    print(i*'* ')
```

**Output**

```bash
* 
* * 
* * * 
* * * * 
* * * * * 
* * * * 
* * * 
* * 
*
```


## Pyramid Pattern #2

```bash
Objective:-

    *     
   ***    
  *****   
 *******  
********* 
```

You can build a pyramid like this by using [center() built-in method](https://www.pylenin.com/blogs/python-string-center/) and [for loops](https://www.pylenin.com/blogs/python-for-loop/).

**Code**

```python3
for i in range(1, 10, 2):
    x = i*'*'
    print(x.center(10))
```

**Output**

```bash
    *     
   ***    
  *****   
 *******  
********* 
```

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).
