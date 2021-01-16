---
title: "Python String rfind() Method"
description: "Learn to use rfind() method on Python strings"
date: 2021-01-14T11:33:30+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String rfind() method

The `rfind()` method in Python finds the last occurrence of the specified substring. It returns `-1` if the value is not found.

Its the opposite of [find() method](https://www.pylenin.com/blogs/python-string-find) as `find()` finds the first occurence of a substring.

##### Syntax of `rfind()` method

```bash
string.rfind(value, start, end)

value: The substring to find(required)
start:	The integer position to start the search. Default is 0.(Optional)
end:	The integer position to end the search. Default is the end of the string.(Optional)
```

##### Example

**Code/Output**

```python3
str1 = "Pylenin loves Python and Python loves Pylenin."

# first occurence of "Python"
print(str1.find("Python"))
>>> 14

# last occurence of "Python"
print(str1.rfind("Python"))
>>> 25
```

##### Example 2 - A substring that doesn't exist

**Code/Output**

```python3
str1 = "Pylenin loves Python and Python loves Pylenin."

print(str1.rfind("Apples"))
>>> -1
```

##### Example 3 - Last occurence of substring between specified positions

**Code/Output**

```python3
str1 = "Pylenin loves Python and Python loves Pylenin."

# occurence of "Python" between 
# position 20 and 40
print(str1.rfind("Python", 20, 40))
>>> 25
```

Check out other [commonly used Python string methods](https://www.pylenin.com/blogs/common-python-string-methods).

#### Related Articles

1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
4. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
5. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
6. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
7. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
8. [Python String Formatting - The Definitive Guide](https://www.pylenin.com/blogs/python-string-formatting/)

