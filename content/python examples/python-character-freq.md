---
title: "Python program to calculate character frequency in a string"
description: "Learn to calculate the frequency of every character in Python 3"
date: 2021-01-21T06:57:35+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Method 1 - Simple `for` loop

**Code**

```python3
user_input = input("Provide a string ==> ")
counter_dict = dict()

for char in user_input:
    if char in counter_dict.keys():
        counter_dict[char] += 1
    else:
        counter_dict[char] = 1

print(counter_dict)
```

**Output**

```bash
Provide a string ==> Pylenin
{'P': 1, 'y': 1, 'l': 1, 'e': 1, 'n': 2, 'i': 1}
```

#### Method 2 - Using `count()` method and `set`

**Code**

```python3
user_input = input("Provide a string ==> ")
counter_dict = dict()

char_set = set(user_input)

for char in char_set:
    counter_dict[char] = user_input.count(char)
print(counter_dict)
```

**Output**

```bash
Provide a string ==> Pylenin
{'l': 1, 'P': 1, 'y': 1, 'e': 1, 'i': 1, 'n': 2}
```

#### Method 3 - Using collections library

**Code**

```python3
from collections import Counter

user_input = input("Provide a string ==> ")
counter_dict = Counter(user_input)
print(counter_dict)
```

**Output**

```bash
Provide a string ==> Pylenin
Counter({'n': 2, 'P': 1, 'y': 1, 'l': 1, 'e': 1, 'i': 1})
```

#### Method 4 - Using dict.get() method

**Code**

```python3
user_input = input("Provide a string ==> ")
counter_dict = dict()

for char in user_input:
    counter_dict[char] = counter_dict.get(char, 0) + 1
print(counter_dict)
```

**Output**

```bash
Provide a string ==> pylenin
{'p': 1, 'y': 1, 'l': 1, 'e': 1, 'n': 2, 'i': 1}
```


#### Related Articles

1. [f-strings in Python](https://www.pylenin.com/blogs/f-strings-python/)
2. [How input() function works in Python](https://www.pylenin.com/blogs/how-input-works-python/)
3. [Common Python String Methods](https://www.pylenin.com/blogs/common-python-string-methods/)
4. [Python Dictionary](https://www.pylenin.com/blogs/python-dictionary/)