---
title: "Python program to replace all occurences of the first character in a string"
description: "Learn to replace all occurences of the first character in a string in Python 3"
date: 2021-01-21T06:57:35+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Objective

Write a Python program to get a string from a given string where **all occurrences of its first character have been changed to another character**.

```bash
# Example 1
str = "Pylenin"
str_replace = "$"
Output ==> "$ylenin"

# Example 2
str = "Pylenin loves Python"
str_replace = "$"
Output ==> "$ylenin loves $ython"
```

#### Method 1 - Using if else

**Code**

```python3
user_input = input("Provide a string ==> ")
str_replace = input("Provide the replacement character ==> ")

if len(user_input) == 0:
    print("Nothing was passed")
    exit()
    
first_char = user_input[0]
new_string = ""
for char in user_input:
    if char == first_char:
        new_string += str_replace
    else:
        new_string += char
print(new_string)
```

**Output**

```bash
# Example 1
Provide a string ==> Pylenin
Provide the replacement character ==> $
$ylenin

# Example 2
Provide a string ==> Pylenin loves Python
Provide the replacement character ==> $
$ylenin loves $ython
```

#### Method 2 - Using `string.replace()` method

**Code**

```python3
user_input = input("Provide a string ==> ")
str_replace = input("Provide the replacement character ==> ")

if len(user_input) == 0:
    print("Nothing was passed")
    exit()

first_char = user_input[0]
print(user_input.replace(first_char, str_replace))
```

**Output**

```bash
# Example 1
Provide a string ==> Pylenin
Provide the replacement character ==> $
$ylenin

# Example 2
Provide a string ==> Pylenin loves Python
Provide the replacement character ==> $
$ylenin loves $ython
```

In both the above examples, we are checking **if the length of `user_input` is greater than 0**. If not, then we are using the `exit()` built-in function to exit the program. Otherwise, Python will throw us an error(**Try it out**).

But it can be done in a much better way with [Exception Handling](https://www.pylenin.com/categories/python-exceptions/).
**Show me, how you would do the same using `try-except` blocks in the comments.**

#### Related Articles

1. [Python Strings](https://www.pylenin.com/categories/python-strings/)
2. [How input() function works in Python](https://www.pylenin.com/blogs/how-input-works-python/)
3. [Common Python String Methods](https://www.pylenin.com/blogs/common-python-string-methods/)
