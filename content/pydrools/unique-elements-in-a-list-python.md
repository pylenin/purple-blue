---
title: "Drool 3: Fastest way to uniquify a list"
date: 2019-09-21T00:10:52+02:00
draft: false
image: /img/Pydrools.png
---

<div class="sharethis-inline-follow-buttons"></div>

With Python 3.6 and above, **the order is preserved while inserting keys to a dictionary**.

Hence, if you want to find unique elements in a list, here are 2 approaches that are not just fascinating, **but are also the fastest**.

**Approach 1 - Preserving order of sequence**

```python3
x = [1, 2, 3, 2, 3, 4, 5, 7, 6, 5]
print(list(dict.fromkeys(x)))
>>> [1, 2, 3, 4, 5, 7, 6]
```

**Approach 2 - Without preserving the order of sequence**

```python3
x = [1, 2, 3, 2, 3, 4, 5, 7, 6, 5]
print(list(set(x)))
>>> [1, 2, 3, 4, 5, 6, 7]
```

Other topics that might interest you.

1. [Find duplicate characters in a string](https://www.pylenin.com/blogs/find-duplicate-characters-in-string/)
2. [An example based guide to working with Python Dictionaries](https://www.pylenin.com/blogs/python-dictionary/)

[Follow @pydrools on Twitter](https://twitter.com/pydrools)

<div align="center"><b>Don't forget to subscribe to the Pydrools Newsletter</b></div>
<div align="center"><iframe width="480" height="320" src="https://pydrools.substack.com/embed" frameborder="0" scrolling="no"></iframe></div>

