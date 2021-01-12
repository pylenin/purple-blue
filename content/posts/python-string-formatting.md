---
title: "String Formatting in Python - The Definite Guide"
description: "Learn multiple ways to format strings in Python"
date: 2021-01-12T12:20:04+05:30
draft: true
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

According to **Zen of Python**, there should be "one obvious way of doing something".
However, there are 4 major ways to perform string formatting in Python. They are:-

1. [String Formatting using % operator](#string-formatting-using--operator)
2. [Python string format() method](#python-string-format-method)
3. [Python String Template Class](#python-string-template-class)
4. [f-strings](#python-string-formatting-using-f-strings)

## String Formatting using % operator

The `%` operator allows you to do simple positional formatting very easily.

**Code**

```python3
name = "Pylenin"
print("I am on %s website"%name)
```

**Output**

```bash
I am on Pylenin website
```

By using the `%s` format specifier, you are telling Python where to substitute the value of **name**.

You can also use other format specifiers that produce a different output format.

**Code**

```python3
name = "Pylenin"
num = 50
print("I am on %s website. It has %d blogs"% (name, num))
```

**Output**

```bash
I am on Pylenin website. It has 50 blogs
```

**The order in which you pass the values is very important.**

Let's look at the example.

**Code**

```python3
print("My name is %s. I love %s"%("Pylenin", "Python"))
print("My name is %s. I love %s"%("Python", "Pylenin"))
``` 

**Output**

```bash
My name is Pylenin. I love Python
My name is Python. I love Pylenin
```

This feature of the `%` operator can make your code unmaintainable.

You can avoid this by using **variable substitution** in your strings.

**Code**

```python3
name = "Pylenin"
language = "Python"

print("My name is %(name)s. I love %(language)s"\
      %{"name":"Pylenin", "language":"Python"})
```

**Output**

```bash
My name is Pylenin. I love Python
```

Apart from `%s` and `%d`, you can also use other format specifiers.

```bash
%s - string representation

%d - Integer representation

%f - Floating point representation

%.<number of digits>f - Floating point representation
                        with a fixed amount of digits 
                        to the right of the decimal.

%e - Exponential representation

%x/%X - Integers in hex representation (lowercase/uppercase)
```

Let's look at a few examples.

**Code**

```python3
str1 = "Pylenin"
num = 100

# String representation
print("My name is %s"%str1)

# Integer Representation
print("The number is %d"%num)

# Floating Point representation
print("Floating point representation of %s is %f"%(num, num))
print("Floating point representation of %s with precision 2 is %.2f"%(num, num))

# Exponential Representation
print("Exponential representation of %s is %e"%(num, num))
print("Exponential representation of %s with precision 2 is %.2e"%(num, num))

# Hex representation
print("Hex representation of %s is 0x%X"%(num, num))
```

**Output**

```bash
My name is Pylenin
The number is 100
Floating point representation of 100 is 100.000000
Floating point representation of 100 with precision 2 is 100.00
Exponential representation of 100 is 1.000000e+02
Exponential representation of 100 with precision 2 is 1.00e+02
Hex representation of 100 is 0x64
```

## Python string format() method

The `format()` method in Python, formats the specified value(s) and inserts them inside the string's replacement fields and returns the formatted string.

The replacement fields for the values is defined using curly braces `{}`.

**Code**

```python3
print("My name is {}. I love {}".format("Pylenin", "Python"))
```

**Output**

```bash
My name is Pylenin. I love Python
```

##### How does it work?

When placeholders `{}` in the string are empty, 
Python will replace the values passed through `str.format()` **in order**.

Check out the following example.

**Code**

```python3
# Method 1
print("My name is {}. I love {}".format("Pylenin", "Python"))
print("My name is {}. I love {}".format("Python", "Pylenin"))

```

**Output**

```bash
My name is Pylenin. I love Python
My name is Python. I love Pylenin
```

#### Formatters with Positional Arguments

Similar to [indexing in strings](https://www.pylenin.com/blogs/access-characters-in-string/), the values present inside `string.format()` method also start with index 0 and increments by 1 with every value.
These index numbers can be passed into the curly braces(replacement fields) serving as the placeholders in the original string. 

Let's look at the following example.

**Code**

```python3
print("My name is {0}. I love {1}".format("Pylenin", "Python"))
print("My name is {1}. I love {0}".format("Pylenin", "Python"))
```

**Output**

```bash
My name is Pylenin. I love Python
My name is Python. I love Pylenin
```

**Beware** - If you try to escape the index 0 or start with a different number, Python will throw you an `IndexError`.

**Code**

```python3
print("My name is {1}. I love {2}".format("Pylenin", "Python"))
```

**Output**

```bash
Traceback (most recent call last):
  File "some_file_location", line 2, in <module>
    print("My name is {1}. I love {2}".format("Pylenin", "Python"))
IndexError: Replacement index 2 out of range for positional args tuple
```

It basically means, you are trying to access the **2nd index** from the values within the `string.format()` method and it doesn't exist.

However, the following example will work.

**Code**

```python3
print("My name is {1}. I love {2}".format("Pylenin", "Python", "Programming"))```

**Output**

```bash
My name is Python. I love Programming
```

In this case, you have values inside the `string.format()` method with index from 0 to 2. You are just not using the 0th index in your string.

#### Formatters with Keyword Arguments

Instead of empty curly braces or curly braces with index, you can also use keyword arguments.

**Code**

```python3
print("My name is {name}. I love {language}"\
      .format(name="Pylenin", language="Python"))
```

**Output**

```bash
My name is Pylenin. I love Python
```

Keyword arguments are like keys in a dictionary. Their order doesn't matter, as they are matched against a name.

#### Specifying Formatting Type

You can also use a specific format in string formatting in Python.

Let's look at the below example.

**Code**

```python3
# integer
print("Integer representation of 99 is {:d}".format(99))

# float
print("Float representation of 99 is {:.2f}".format(99))

# binary
print("Binary representation of 99 is {:b}".format(99))

# exponent
print("Exponential representation of 99 is {:.2e}".format(99))
```

**Output**

```bash
Integer representation of 99 is 99
Float representation of 99 is 99.00
Binary representation of 99 is 1100011
Exponential representation of 99 is 9.90e+01
```

You can find a list of available formatters [here](https://docs.python.org/3/library/string.html#format-specification-mini-language).

## Python String Template Class

The String Template class in Python is used to create a **template string** using a `$` sign. These fields can be replaced later on to create a string object.

This class has 2 key methods:

```bash
===============================
1. substitute(mapping, **kwds):
=============================== 
This method performs substitutions using a 
"dictionary like" key-value based mapping objects.
If keys are missing, it returns a KeyError.

====================================
2. safe_substitute(mapping, **kwds):
==================================== 
Similar behavior as above, but it doesn’t throw a 
KeyError if a key is missing. It just returns the 
placeholder in the result string.
```

Let's look at a few examples.

##### String Template substitute() method

##### Example 1

**Code**

```python3
from string import Template

t = Template('$name writes blogs on $language')
s = t.substitute(name='Pylenin', language='Python')
print(s)

# dictionary as substitute argument
d = {'name': 'Pylenin', 'language': 'Python'}
s = t.substitute(**d)
print(s)
```

**Output**

```bash
Pylenin writes blogs on Python
Pylenin writes blogs on Python
```

##### Example 2

**Code**

```python3
from string import Template

# Students and their respective heights
Student = [('Lenin', 190), ('Darshana', 180), ('Chinmayee', 150)]

# Create a basic structure
# to print the name and height
t = Template('Hi $name, your height is $height cm')

for i in Student:
    print(t.substitute(name=i[0], height=i[1]))
```

**Output**

```bash
Hi Lenin, your height is 190 cm
Hi Darshana, your height is 180 cm
Hi Chinmayee, your height is 150 cm
```

Let's look at the possible errors in String Template substitute() method.

1. If a key is missing from your **dictionary like** object, it will throw a `KeyError`.
2. Any other appearance of `$` in the string will result in a `ValueError`.

**Code - Example 1**

```python3
from string import Template

t = Template('$name writes blogs on $language')

d = {'name': 'Pylenin'}
s = t.substitute(**d)
print(s)
```

**Output - Example 1**

```bash
KeyError: 'language'
```

**Code - Example 2**

```python3
from string import Template

t = Template('Give $name $100')

s=t.substitute({"name":"Pylenin"})
print(s)
```

**Output - Example 2**

```bash
ValueError: Invalid placeholder in string: line 1, col 12
```

You can get rid of the above 2 errors using the following:-

1. `KeyError` - Use safe_substitute() method
2. `ValueError` - Use safe_substitute() method **or** Escape the `$` sign using `$$`.

#### String Template safe_substitute() method

If placeholders are missing from mapping and kwds, instead of raising a KeyError exception, the original placeholder will appear in the resulting string.

**Code**

```python3
from string import Template

t = Template('$name writes blogs on $language')

d = {'name': 'Pylenin'}
s = t.safe_substitute(**d)
print(s)
```

**Output**

```bash
Pylenin writes blogs on $language
```

It can also escape any other appearances of the `$` sign.

**Code**

```python3
from string import Template

t = Template('Give $name $100')

s=t.safe_substitute({"name":"Pylenin"})
print(s)
```

**Output**

```bash
Give Pylenin $100
```

#### Escaping `$` sign with `$$`

Another way to escape any other appearances of the `$` sign, is to use `$$` sign.

If you use `$$`, you can safely use the `substitute()` method.

**Code**

```python3
from string import Template

t = Template('Give $name $$100')

s=t.substitute({"name":"Pylenin"})
print(s)
```

**Output**

```bash
Give Pylenin $100
```

## Python String Formatting using f-strings

**F-strings** is a string formatting mechanism introduced by [PEP 498](https://www.python.org/dev/peps/pep-0498/) for Python versions 3.6 and above.

Each of the methods suggested above have their advantages, but in addition have disadvantages that make them cumbersome to use in practice. This PEP proposed to add a new string formatting mechanism: Literal String Interpolation, also called `f-strings`(because of the leading f character preceding the string literal).

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

#### Related Articles

1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
4. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
5. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
6. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
7. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
