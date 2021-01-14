---
title: "f-strings in Python"
description: "Learn to use f-strings in Python"
date: 2021-01-08T20:51:35+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string formatting']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**F-strings** is a string formatting mechanism introduced by [PEP 498](https://www.python.org/dev/peps/pep-0498/) for Python versions 3.6 and above.

Python supports multiple ways to format text strings.

* % formatting 
* .format()
* string.Template

Each of these methods have their advantages, but in addition have disadvantages that make them cumbersome to use in practice. This PEP proposed to add a new string formatting mechanism: Literal String Interpolation, also called `f-strings`(because of the leading f character preceding the string literal).

#### Create an f-string

To create an f-string, prefix a string with the letter `f`. It works similarly to `str.format()`.

**Code**

```python3
num1 = 10
num2 = 5
  
# Adding both numbers 
sum = num1 + num2 
  
# printing values 
print(f"Sum of {num1} and {num2} is {sum}") 
```

**Output**

```bash
Sum of 10 and 5 is 15
```

#### Embed Python expressions in f-string

f-strings provide a convenient way to embed python expressions inside string literals for formatting.

**Code**

```python3
num1 = 10
num2 = 5
  
# printing values 
print(f"Sum of {num1} and {num2} is {num1+num2}") 
```

**Output**

```bash
Sum of 10 and 5 is 15
```

You can also call Python functions within a f-string.

**Code**

```python3
x = "Pylenin"

print(f"{x.lower()}")
```

**Output**

```bash
pylenin
```

You could also work with objects created from [classes](https://www.youtube.com/watch?v=fe9h17PYn0M&list=PLqEbL1vopgvsVCEk_aEnsLH-3qyn0Z6Wn) with f-strings.

**Code**

```python3
class Programmer:
    def __init__(self, name, language):
        self.name = name
        self.language = language

    def __str__(self):
        return f"{self.name} like {self.language}"

new_programmer = Programmer('Pylenin', 'Python')

print(f"{new_programmer}")
```

**Output**

```bash
Pylenin like Python
```

#### Multiline f-strings

You can use multiple lines with f-strings. **Just remember to put `f` in fron of every line.**

**Code**

```python3
name = "Pylenin"
language="Python"
age = 29

str1 = f"Hello, I am {name}. \n"\
       f"I love {language}. \n"\
       f"I am {age} years old."

print(str1)
```

**Output**

```bash
Hello, I am Pylenin. 
I love Python. 
I am 29 years old.
```

#### f-strings are fast

Since f-strings are evaluated at runtime, they are faster than both [%-formatting](https://www.pylenin.com/blogs/string-formatting-percentage-operator/), [String Template formatting](https://www.pylenin.com/blogs/python-string-template-class/) and [string.format() method](https://www.pylenin.com/blogs/format-method-python-string/).

You can confirm it by using the [timeit module in Python](https://www.pylenin.com/blogs/python-timeit-module/).

**Example 1 - Timer with % operator**

```python3
from timeit import timeit

str1 = """
name = "Pylenin"
language="Python"
age = 29

str1 = "Hello, I am %s. "\
       "I love %s. "\
       "I am %d years old."%(name, language, age)

print(str1)
"""
print(timeit(str1, number=10000))
```

The above code took **0.2817505 secs**.

**Example 2 - timeit for string.format() method**

```python3
from timeit import timeit

str1 = """
name = "Pylenin"
language="Python"
age = 29

str1 = "Hello, I am {0}. "\
       "I love {1}. "\
       "I am {2} years old.".format(name, language, age)

print(str1)
"""
print(timeit(str1, number=10000))
```

The above code took **0.3652804 secs**.

**Example 3 - timeit for String Template Class**

```python3
from timeit import timeit

str1 = """
from string import Template

name = "Pylenin"
language="Python"
age = 29

str1 = Template("Hello, I am $name. "\
                "I love $language. "\
                "I am $age years old.")

print(str1.substitute(name=name, language=language, age=age))
"""
print(timeit(str1, number=10000))
```

The above code took **0.1888825 secs**.

**Example 4 - timeit for f-strings**

```python3
from timeit import timeit

str1 = """
name = "Pylenin"
language="Python"
age = 29

str1 = f"Hello, I am {name}. "\
       f"I love {language}. "\
       f"I am {age} years old."

print(str1)
"""
print(timeit(str1, number=10000))
```

With f-strings, the code only took **0.1565294 secs**, considerably lesser than any other method.

![Comparison of Execution time for all String Formatting Methods in Python](/img/python-strings/string-formatting/python-string-formatting-execution-time.png)

**Python offers 3 other ways of String Formatting. Check out [the definite guide to Python String Formatting](https://www.pylenin.com/blogs/python-string-formatting/)** 

#### Related Articles

1. [Python String format() method](https://www.pylenin.com/blogs/format-method-python-string/)
2. [Python String Template Class](https://www.pylenin.com/blogs/python-string-template-class/)
3. [% operator - Python String formatting](https://www.pylenin.com/blogs/string-formatting-percentage-operator/)
4. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
5. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
6. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
7. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
8. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
9. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
10. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)