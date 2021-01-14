---
title: "Find Duplicate Characters in a Python String (2 ways)"
description: "This article provides an interesting approach to finding duplicate characters in a string by using the collections library."
date: 2019-08-30T16:08:56+02:00
draft: false
image: /img/duplicate-characters-in-a-string/coding-1.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

If you prefer videos over text, [click here](https://youtu.be/9-4BcIoEE1o).

**Problem**

> Given a string with length > 0, write a function `find_duplicates()` to find all the duplicate characters in a string.

Example - 

1. **find_duplicates('Hello') - ['l']**
2. **find_duplicates('Hippopotamus') - ['p', 'o']**
2. **find_duplicates('Python') - [] (An empty list)**

We are going to discuss 2 ways of solving this question.

The first way is a very generic python code that loops over all the elements in the string and stores the number of times each element occurs. **It's simple, but effective.**

```python3
# Method 1

def find_duplicates(s):
    elements = {}
    for char in s:
        if elements.get(char,None) != None:
            elements[char]+=1
        else:
            elements[char] = 1
    return [k for k,v in elements.items() if v>1]

print(find_duplicates("Hello"))
>>> ['l']
print(find_duplicates("Hippopotamus"))
>>> ['p', 'o']
print(find_duplicates("Python"))
>>> []
```

The second way is by using the `collections` library. Specifically, the `Counter` method. This method reduces the above code to merely a few lines.

Watch how !!

```python3
# Method 2

from collections import Counter

def find_duplicates(s):
    elements = Counter(s)
    return [k for k,v in elements.items() if v>1]

print(find_duplicates("Hello"))
>>> ['l']
print(find_duplicates("Hippopotamus"))
>>> ['p', 'o']
print(find_duplicates("Python"))
>>> []
```

With just 2 lines of code, we were easily able to achieve our objective. 

Let me know if you have a better way of doing this, through the comments.

<div align="center"><b>Don't forget to subscribe to the Pydrools Newsletter</b></div>
<div align="center"><iframe width="480" height="320" src="https://pydrools.substack.com/embed" frameborder="0" scrolling="no"></iframe></div>

