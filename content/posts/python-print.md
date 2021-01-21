---
title: "Diving deeper into Python print"
description: "Learn how to print relevant messages to screen or other outputs using Python. Examples for both Python 2 and Python 3 are provided to show the differences in a clear way."
date: 2019-07-08T21:16:02+02:00
draft: false
image: /img/python-print/python-print.png
categories: ['Getting Started with Python']
categories_weight: 4
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

I write this blog with an intention of providing a more deeper context and importance to print that it rarely gets. If you prefer videos over text, check out our video [here](https://youtu.be/swrVUxJ17eQ).

Pretty much every programmer learns programming by printing `Hello World` message to their screen. However, rarely any blog or video on the internet takes a deep dive into the mysteries of print in Python.

In order to help the Python 2 programmers in transitioning to Python 3, I will provide examples for both the versions. That way you are aware of the history of `print()` and how it has changed in Python 3.

**Sections Covered**

1. [Writing a Hello World program](#writing-a-hello-world-program)
2. [General Syntax of Print](#general-syntax-of-print)
3. [Printing multiple elements](#printing-multiple-elements)
4. [Printing to a newline](#printing-to-a-newline)
5. [Printing to a file](#printing-to-a-file)
6. [Flushing](#flushing)

##### Writing a Hello World program

Let's start with a `Hello World` program.
```python3
#Python 2
print 'Hello World'
>>> Hello World

# Python 3
print('Hello World')
>>> Hello World
```
**YES**. It is that easy. 

You can notice that you need to pass in your messages inside a bracket in Python 3 compared to Python 2. It's because print is a **function** in Python 3. It was a **statement** in Python 2.

Now the above example is required when you are within an IDE. If you are running your Python code on the command line, you don't even need to use print.

```bash
# Python 2
$ my-folder: python
Python 2.7.10 (default, Aug 17 2018, 19:45:58)
[GCC 4.2.1 Compatible Apple LLVM 10.0.0 (clang-1000.0.42)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 'Hello World'
'Hello World'

# Python 3
$ my-folder: python3
Python 3.6.5 (v3.6.5:f59c0932b4, Mar 28 2018, 03:03:55)
[GCC 4.2.1 (Apple Inc. build 5666) (dot 3)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 'Hello World'
'Hello World'
```

Print by default provides an interface to the standard output(`sys.stdout`) object. When you use print, you are asking your Python interpreter to echo your message to standard output. For example, you can also print a message, **without using print**.

```python3
# Python 2 and Python 3
import sys

sys.stdout.write('Hello World')
>>> Hello World
```
You use the `write()` method in **sys.stdout** to output your message to the standard output stream. **Print is just easier to use and comprehend**.

##### General Syntax of Print

Let's look at the general syntax of print in Python.
```bash
# Python 2
"print" ([expression ("," expression)* [","]]
        | ">>" expression [("," expression)+ [","]])

# Python 3
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```
In both the versions, Python converts the objects into strings(if they are not strings) and then writes to the standard output stream. 

##### Printing multiple elements

We can use print to write multiple elements in a single line.
```python3
# Python 2
print 'Python', 2, 'Rocks'
>>> Python 2 Rocks

# Python 3
print('Python', 3, 'Rocks')
>>> Python 3 Rocks
```
Print adds a space between each object before writing it to the standard output. In the format for Python 3, you can see a `sep` parameter. it has been set to `' '` as default. 

Same thing happens with Python 2. However, there is no such `sep` parameter in Python 2. Spaces are added in between objects by default.

That being said, you can easily pass in a different value to the `sep` argument in Python 3. For e.g.
```python3
print('Python', 3, 'Rocks', sep='|')
>>> Python|3|Rocks
```
The above can't be achieved with Python 2 using a print statement. However, you can using the `__future__` built-in method in Python 2 to emulate the print function in Python 3.
```python
# Python 2
from __future__ import print_function

print("Python","Rocks", sep="|")
```

##### Printing to a newline

Check out this example code.
```python3
# Python 2
print 'Python', 2, 'Rocks'
print 'I love Python'
>>> Python 2 Rocks
>>> I love Python

# Python 3
print('Python', 3, 'Rocks')
print('I love Python')
>>> Python 3 Rocks
>>> I love Python
```
When you have multiple print statements, Python by default prints it to a newline. In Python 2, a `\n` character is added to the end whereas in Python 3, there is an argument `end` that is set to `\n` by default.

However, you can change this default behavior. 

**To print multiple expressions to the same line**, you can end the print statement in Python 2 with a comma (`,`). In Python 3, you can set the `end` parameter to a **whitespace character string**.

```python3
# Python 2
print 'Python', 2, 'Rocks',
print 'I love Python'
>>> Python 2 Rocks I love Python

# Python 3
print('Python', 3, 'Rocks', end=' ')
print('I love Python')
>>> Python 3 Rocks I love Python
```

With Python 3, you do have the added flexibility of changing the `end` paramter to anything you want. For e.g.
```python3
# Python 3
print('Python', 3, 'Rocks', end='*')
print('I love Python')
>>> Python 3 Rocks*I love Python
```
Watch how I use an asterisk(`*`) value for my `end` parameter. There is no clean way to do that in Python 2. In order to achieve the above with Python 2, you would have to add the `*` to the end of every line.
```python3
print 'Python', 2, 'Rocks', '*',
print 'I love Python'
```

##### Printing to a file

You can also write your message to a **file** using print in Python. For this purpose, we can use the `file` argument.
```python3
# Python 2
print >> open('hello.txt', 'w'), 'Hello World'

# Python 3
print('Hello World', file=open('hello.txt', 'w'))
```
In the above example, the message is written to a file called `hello.txt`. Notice the use of `open` in order to save the messages to the file. 

So if you want to send your messages to any other place other than the standard output, make sure to provide a file object that has a **write** method to it.

##### Flushing

This is probably one of the most ignored concepts. Probably because we don't see any direct impact while we are printing. But it is an important concept.

Usually Python buffers the messages that you want to print until it gets a newline(`\n`). 

Let's see this through an example. Instead of the the default value for the `end` parameter (`\n`), we are going to leave it empty.

```python3
from time import sleep

print('Will it get printed immediately?', end='')
sleep(5)
```

When you run the above snippet, the print message will only show up after the 5 seconds of sleep is over. **Why?** because print expects a `\n` or a newline at the end of every print statement. Hence, your message is in buffer.

Using the `flush` argument in Python 3, you can directly print the message to the standard output stream without having to wait for the sleep time to finish. 

Try this out.
```python3
from time import sleep

print('Will it get printed immediately?', end='', flush=True)
sleep(5)
```

I have tried to dive deep into every aspect of print for both Python 2 and Python 3. If you have any questions or comments, do put them down in the comments section.

*Do you feel the article misses out on some important information? Or may be some information has been misrepresented?* 

Submit your changes by creating a Pull Request [here](https://github.com/pylenin/pylenin-blogs).
