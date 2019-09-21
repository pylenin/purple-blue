---
title: "Python list - Remove consecutive duplicates (3 Ways)"
description: "3 different ways to remove consecutive duplicates in a Python list"
date: 2019-09-21T12:08:52+02:00
draft: false
image: /img/zipmeta.png
---

<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

In this article, we will discuss 3 different ways of **removing consecutive duplicate elements** from a python list.
This is what we want to achieve.
```angular2
input - [1, 2, 4, 7, 3, 7, 8, 4, 4, 9]
output - [1, 2, 4, 7, 3, 7, 8, 4, 9]
```

So we are not removing all duplicated elements. We are only eliminating consecutive duplicate elements.

Let's check out the 3 different ways.

**Method 1 - For loops will never go out of fashion**

```python3
x = [1,2,4,7,3,7,8,4,4,9]

previous_value = None
new_lst = []

for elem in x:
   if elem != previous_value:
       new_lst.append(elem)
       previous_value = elem

print(new_lst)
>>> [1, 2, 4, 7, 3, 7, 8, 4, 9]
```

**Method 2 - Let's be more Pythonic! Use Enumerate**

Here is a one-liner solution to the problem.

```python3
x = [1,2,4,7,3,7,8,4,4,9]

print([v for i, v in enumerate(x) if i == 0 or v != x[i-1]])
>>> [1, 2, 4, 7, 3, 7, 8, 4, 9]
```
Tell me that wasn't pretty !!
   
**Method 3 - It's Python! There must be a library**

Here is the 3rd way using the `itertools` library.

```python3
from itertools import groupby

x = [1,2,4,7,3,7,8,4,4,9]
print([i[0] for i in groupby(x)])
>>> [1, 2, 4, 7, 3, 7, 8, 4, 9]
```

Now the question is, **which one of the above methods is the fastest?**

Using the `time` and `matplotlib` library, I plotted the time taken for each of those methods.

![Time recorded for each method](/img/remove-consecutive-elements-python/time.png)

You can see that the **3rd approach (using the itertools library)** is the fastest of all the 3 ways discussed in this article.

Hope you enjoyed this article. Let me know if you have a better way of doing this, through the comments.

<div align="center"><b>Don't forget to subscribe to the Pydrools Newsletter</b></div>
<div align="center"><iframe width="480" height="320" src="https://pydrools.substack.com/embed" frameborder="0" scrolling="no"></iframe></div>




