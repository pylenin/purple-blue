---
title: "How to access characters in a Python string?"
description: "Learn to access characters in Python strings"
date: 2021-01-09T12:58:09+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

#### String Indexing

You can access individual characters of a string using **indexing** and a range of characters using **slicing**. In Python, index starts from 0 and keeps increasing by 1 with every character.

This is called **Positive Indexing**(or indexing from the beginning). If there are __**n**__ characters in a string, the 1st character will be index 0 and the last character will have index __**n-1**__.

Let's look at the image below for better understanding.

![Positive Indexing in Python](/img/python-strings/positive-indexing.png)

**Python also allows negative indexing(indexing from the end).** If there are __**n**__ characters in a string, the last character will be index **-1** and the first character will have index __**-n**__.

Let's look at the image below for better understanding.

![Indexing in Python](/img/python-strings/positive-negative-indexing-strings.png)

**Code**

```python3
str = 'PYLENIN'

# first character
print('str[0] =', str[0])

# last character
print('str[-1] =', str[-1])

# second character
print('str[1] =', str[1])

# second last character
print('str[-2] =', str[-2])

```

**Output**

```bash
str[0] = P
str[-1] = N
str[1] = Y
str[-2] = I
```

If you try to access a character out of range, it will raise an `IndexError`. 

Also, the index must be an **integer**. You can't use floats or other types for indexing. This will result into `TypeError`.

**Code/Output**

```python3
str = 'PYLENIN'

print(str[10])
>>> IndexError: string index out of range

print(str[1.5])
>>> TypeError: string indices must be integers
```

#### String Slicing

To access a range of characters, you need to use **slicing**. Basically, you have to specify the start index and the end index, separated by a colon, to return a part of the string.

![Slicing Strings in Python](/img/python-strings/string-slicing.png)

**Remember** - The last index is not included.

Let's say you want to access all the elements from 2nd index to 4th index of `PYLENIN` string. In that case, **your end index will be 5**.

**Code**

```python3
str = 'PYLENIN'

# 2nd to 4th index
print('str[2:5] =', str[2:5])
```

**Output**

```bash
str[2:5] = LEN
```

If you leave out the start index, the range will start at the first character.

**Code**

```python3
str = 'PYLENIN'

# 2nd to 4th index
print('str[:5] =', str[:5])
```

**Output**

```bash
str[:5] = PYLEN
```

If you leave out the end index, the range will go to the end.

**Code**

```python3
str = 'PYLENIN'

# 2nd to 4th index
print('str[2:] =', str[2:])
```

**Output**

```bash
str[2:] = LENIN
```

You can also use negative index for slicing. Just use the negative index counterpart of your positive index.

```python3
str = 'PYLENIN'

# Both produce the same result

print('str[2:5] =', str[2:5])
print('str[-5:-2] =', str[-5:-2])
```

**Output**

```bash
str[2:5] = LEN
str[-5:-2] = LEN
```

#### Related Articles

1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
3. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
4. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
5. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
6. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
7. [Python String Formatting - The Definitive Guide](https://www.pylenin.com/blogs/python-string-formatting/)