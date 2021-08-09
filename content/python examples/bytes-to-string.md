---
title: "Python program to convert bytes to string"
description: "Learn to convert bytes to string in Python 3"
date: 2021-08-08T06:57:35+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python Input/Output Examples']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Difference between bytes and strings in Python

In Python 3, a string is a sequence of characters, 
i.e. unicode codepoints. **A string can't be directly stored on disk.** 

A byte string is a sequence of  "bytes" - things that can be 
stored on disk. So to store strings, they need to be converted to a 
byte string. 

The process of converting a string to a sequence of bytes is called **Encoding**.


#### How to convert bytes to a string?

If encoding is the process of converting string to bytes, 
**decoding** is the process to convert bytes back to strings. Luckily, 
Python 3 has a `decode()` function that you can use directly to convert bytes to strings.

**Code**

```python3
byte_string = b'Good job Pylenin \xE2\x9C\x85'.decode("utf-8")
```

**Output**

```bash
>>> Good job Pylenin ?
```

As you can see, we are using `utf-8` encoding format. This could be 
a difficult task as there are quite a lot of such encoding formats 
and you need to know which applies in the particular case in order 
to make the conversion, since a different encoding might map the 
same bytes to a different string.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).
