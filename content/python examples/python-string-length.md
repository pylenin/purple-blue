---
title: "Python program to calculate length of a string"
description: "Learn to calculate the length of a string in Python 3"
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
length = 0
for char in user_input:
    length += 1
print(f"Length of '{user_input}' is {length}")
```

**Output**

```bash
Provide a string ==> Joe Biden
Length of 'Joe Biden' is 9
```

#### Method 2 - Using `len()` built-in function

**Code**

```python3
user_input = input("Provide a string ==> ")
print(f"Length of '{user_input}' is {len(user_input)}")
```

**Output**

```bash
Provide a string ==> Pylenin
Length of 'Pylenin' is 7
```

##### Related Articles

1. [f-strings in Python](https://www.pylenin.com/blogs/f-strings-python/)
2. [How input() function works in Python](https://www.pylenin.com/blogs/how-input-works-python/)
3. [Common Python String Methods](https://www.pylenin.com/blogs/common-python-string-methods/)
