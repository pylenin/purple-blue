---
title: "Python Bootcamp 2021"
date: 2021-01-30T20:01:48+05:30
draft: false
image: /img/pylenin_logo.png
---

## Welcome to the self paced Python Bootcamp 2021. 

This course has been designed, keeping in mind the current requirements of Python in the Job world and the minimum effort required to master Python as a choice of programming language.

In this Bootcamp, you will have the access to the best resources for every topic that should help you begin your journey in Python. Along with daily tutorials that include articles and videos, you will also be asked to test your learnings through a series of problems related to the topic.

**Why should you learn Python?**

Whether you are aiming to join a Fortune 500 corporation 
or desire to pursue a freelancing career in programming, 
it is important to know **what is hot in the industry**.

Python continues to be the language that is pretty much used in every company around the world for various purposes.
This also means that there is a huge potential for **you to land a job as a Python developer**.

**[Check out this article](https://www.pylenin.com/blogs/5-reasons-to-learn-python/) demonstrating 5 key reasons to learn Python in 2021**.

## Who is this Bootcamp for?

1. Beginners who have never programmed.
2. Programmers coming in from another language to learn Python.
3. Programmers who know the basics and want to level up their skills.

## How to follow along this Bootcamp?

**This bootcamp will begin on 1st of February and end on 28th of February, 2021.**

1. Every day, this page will be updated with the course materials for the topic you will be learning.
2. You will be provided with questions that you need to solve every day after you have gone through the course material.
3. The solutions to the asked questions shall be provided the next day.
4. **If you are joining late to the Bootcamp**, be sure to first try out the questions yourself before checking the solution. **DON'T CHEAT YOURSELF!**

## How to get notified when course materials are uploaded?

Every day, the course materials should be uploaded by **10 AM UTC**. 
A daily notification will be sent to all member of the [Official Pylenin Group](https://t.me/pythonwithpylenin) on Telegram 
when the course materials are uploaded. To receive the notification, **join the above Telegram group**.

## Where to ask doubts?

Asking doubts on Telegram could make the group **really SPAMMY!**.
To ensure that people are able to ask their doubts without being disturbed by others all day, we have created a [Facebook Group](https://www.facebook.com/groups/programmingcareerguidance).

**When you have a doubt:-**

1. Go to the above mentioned Facebook Group.
2. Create a Post specifying your doubt, **mentioning the Day of Bootcamp you are stuck on**.
3. Our admins will carefully go though the posts and approve them, if they are felt genuine.
4. **SPAM messages won't be allowed.**

##### Our average response time is 2 hours.

## Getting Started

### Day 1 - Installing Python and Hello World!

1. [Check out this installation guide](https://www.pylenin.com/blogs/installing-python-for-windows/) to install Python on your machine. The article demonstrates installing **Python 3.9 on Windows 10**, but you can use the instructions for any OS.
2. Next you will need an IDE. We suggest you to choose either **VS Code or Pycharm Community Edition**. [Check out their installation guide here](https://www.pylenin.com/tags/python-ide/).
3. Every programmer's first code - **Hello World!**. [Check out this article](https://www.pylenin.com/blogs/python-print/) to learn about printing anything in Python.

**Daily Exercise**

**Qns 1**
   
Print `My Name Is Pylenin` as `My|Name|Is|Pylenin` using output formatting of a `print()` function.

[Solution](https://www.pylenin.com/blogs/python-print/#printing-multiple-elements)

**Qns 2**

Improve the following code so that **it prints over the same line**.

```python3
print("Welcome")
print("to")
print("Python")
print("Bootcamp")
print("2021")
```

**What is the expected outcome?**

[Solution](https://www.pylenin.com/python-examples/print-over-same-line/)

**Qns 3**

Use print statement to print to a file instead of `stdout`.
   
[Solution](https://www.pylenin.com/blogs/python-print/#printing-to-a-file)

### Day 2 - Passing comments, Keywords and Identifiers

The best time to learn the best practices in anything is when you are a beginner. The habits you develop in that phase, stay with you forever.

1. [Check out this article](https://www.pylenin.com/blogs/python-comments/) to learn about **using Comments and its importance** in Python Programming

Before you learn to write code in Python, **learn, what you should not use in your code**.

2. Learn about Keywords and Identifiers used in Python [in this article](https://www.pylenin.com/blogs/keywords-identifiers/).

**Daily Exercise**

**Qns 1**

Check if the following list of terms are keywords in Python.

```bash
check, i, Exception, flush, nonlocal, async, await
```

[Solution](https://www.pylenin.com/blogs/keywords-identifiers/#how-to-check-if-a-string-is-a-keyword)

**Qns 2**

Which of the following identifiers are valid?

```bash
1. @x = 10
2. y = type("Lenin")
3. 1_integer = 10
4. else = "Apple"
5. _ = 23
```

[Solution](https://www.pylenin.com/blogs/keywords-identifiers/#rules-to-remember-while-writing-identifiers)

**Qns 3**

Check out the following code. Add comments where you deem fit.

```python3
a = 10
b = 12
c = 13

s = (a + b + c) / 2

area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
print('The area of our triangle is %0.2f' %area)
```

[Solution](https://www.pylenin.com/python-examples/python-area-of-triangle/)

### Day 3 - Python Variables and String Formatting

1. [Youtube Video on Variable and String Formatting](https://youtu.be/qBO9Cfs4UEs)

2. **Further Reading on Variables** - [Understanding Variables in Python 3](https://www.pylenin.com/blogs/python-variables/)

3. **Further Reading on String Formatting** - [Learn 4 ways to format strings in Python](https://www.pylenin.com/tags/python-string-formatting/)

**Daily Exercise**

**Qns 1**

Format the following line of code to contain only 2 decimal places.

```python3
print("4 divided by 3 is %f"%(4/3))
```

_*Solution*_

```python3
print("4 divided by 3 is %.2f"%(4/3))
```

**Qns 2**

Format the following line of code to contain only 2 decimal places.

```python3
print(f"4 divided by 3 is {4/3}")
```

_*Solution*_

```python3
print(f"4 divided by 3 is {4/3:.2f}")
```

**Qns 3**

Run the following lines of code in your editor and check the output.

Figure out, why are they being printed that way.

```python3
print(f"4 divided by 3 is {4/3:0.2f}")
print(f"4 divided by 3 is {4/3:1.2f}")
print(f"4 divided by 3 is {4/3:2.2f}")
print(f"4 divided by 3 is {4/3:3.2f}")
print(f"4 divided by 3 is {4/3:4.2f}")
print(f"4 divided by 3 is {4/3:5.2f}")
print(f"4 divided by 3 is {4/3:6.2f}")
print(f"4 divided by 3 is {4/3:7.2f}")
print(f"4 divided by 3 is {4/3:8.2f}")
print(f"4 divided by 3 is {4/3:9.2f}")
print(f"4 divided by 3 is {4/3:10.2f}")
```

[Solution](https://www.pylenin.com/blogs/python-width-precision/)

**Qns 4**

Write a Python program which accepts the user's 
first and last name and print them in reverse 
order with a space between them.

Reference Material - [How input() works in Python](https://www.pylenin.com/blogs/how-input-works-python/)

### Day 4 - Python Booleans and Operators

1. [Arithmetic Operators and Booleans](https://youtu.be/pOUp-qCQg64)
2. [Comparison and Assignment Operators](https://youtu.be/mPrcM1WHmdA)

**Further Reading**

3. [Detailed Examples of using Booleans](https://www.pylenin.com/blogs/booleans-in-python/)
4. [Fun with Numbers and Arithmetic Operators](https://www.pylenin.com/blogs/python-arithmetic-operators/)
5. [Comparison Operators and understanding ASCII values](https://www.pylenin.com/blogs/python-comparison-operators/)
6. [Assignment Operators and Bitwise Operation](https://www.pylenin.com/blogs/python-assignment-operators/)
7. [Walrus Operator - Cool new feature since Python 3.8](https://www.pylenin.com/blogs/python-assignment-operators/#walrus-operator)

**Daily Exercise**

**Qns 1** 

Write a Python program to convert Degrees to Radians.

[Solution](https://www.pylenin.com/python-examples/degree-to-radian/)

**Qns 2**

Write a Python program to ask user for an integer and calculate its square.
Reference Material - [How input() works in Python](https://www.pylenin.com/blogs/how-input-works-python/)

[Solution to a similar problem](https://www.pylenin.com/python-examples/python-find-squareroot/)

**Qns 3**

What is the value of the expression `1 + 2.0 + 3` in Python?

[Solution](https://www.pylenin.com/blogs/python-arithmetic-operators/#combining-two-numbers-of-different-types)

**Qns 4**

Write a Python program to ask user for an integer and convert it **into floating point**.
Reference Material - [How input() works in Python](https://www.pylenin.com/blogs/how-input-works-python/)

[Solution](https://www.pylenin.com/blogs/python-arithmetic-operators/#number-type-conversion)

**Qns 5**

Calculate the results of the following Bitwise operations **by hand** and then verify your answers by running it in Python interpretor.

```bash
1. 10&=4
2. 10^=4
3. 12|=3
4. 10<<=3
```

[Solution](https://www.pylenin.com/blogs/python-assignment-operators/)

**Qns 6**

Simplify the below operation to show the numerator and denominator and calculate the result.

```python3
print((a:=3)/(10+(y:=4)))
```

[Solution](https://www.pylenin.com/blogs/python-assignment-operators/#walrus-operator)

**Qns 7**

Run the following code and figure out **why Python is returning False?**

```python3
print(0.1 + 0.2 == 0.3)
```

[Solution](https://www.pylenin.com/blogs/python-float-arithmetics/)

## Python Data Types

### Day 5 - Python Numbers

1. [Python Numbers, Arithmetic Operators and Mathematics](https://www.pylenin.com/blogs/python-arithmetic-operators/)
2. [Python isinstance() function - Figuring out the types](https://www.pylenin.com/blogs/python-isinstance/)
3. [Difference between type() and isinstance()](https://www.pylenin.com/blogs/type-vs-isinstance/)

**Daily Exercise**

**Qns 1**

Write a Python Program to check if a number is odd or even.

[Solution](https://www.pylenin.com/python-examples/odd-even/)

**Qns 2**

Write a Python program to check if **any** of the variables below are 
**Integer types**.

```python3
x = "Pylenin"
y = 7
z = abs(-22)
```

[Reference Material](https://www.pylenin.com/blogs/python-any-all/)

[Solution](https://www.pylenin.com/blogs/python-any-all/#check-if-any-variables-are-of-particular-data-type-in-python)

**Qns 3**

Convert the following decimals to Binary format by hand.

```bash
1. 4.25
2. 0.0625
3. 9.8
```

[Solution](https://www.instagram.com/p/CK8B9p0g9XO/?utm_source=ig_web_copy_link)

### Day 6 - Python String

1. [Video on Python Strings](https://youtu.be/MXdNMo_f95I)

**Reading Materials**

1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
4. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
5. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
6. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
7. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
8. [Python String Formatting - The Definitive Guide](https://www.pylenin.com/blogs/python-string-formatting/)
9. [Common Python String Methods](https://www.pylenin.com/blogs/common-python-string-methods/)

**Daily Exercise**

1. Write a Python program to replace all occurences of the first character in a string. [Solution](https://www.pylenin.com/python-examples/python-replace-chars/) 
2. Write a Python program to calculate length of a string. [Solution](https://www.pylenin.com/python-examples/python-string-length/)
3. Write a Python program to calculate character frequency in a string. [Solution](https://www.pylenin.com/python-examples/python-character-freq/)
4. Write a Python program to add first and last n characters in a string. [Solution](https://www.pylenin.com/python-examples/first-last-n-chars/)
5. Write a Python program to draw the below Pyramid. [Solution](https://www.pylenin.com/blogs/python-string-center/#example-3-printing-pyramid-patterns-in-python)

```bash
    *     
   ***    
  *****   
 *******  
********* 
```

### Day 7 - Python Lists

1. [Extensive discussion on Python lists](https://youtu.be/r6lJVWMR9e4)

**Further Reading**

1. [Characteristics of Python Lists](https://www.pylenin.com/blogs/python-lists/#characteristics-of-python-lists)
2. [How to create a list in Python?](https://www.pylenin.com/blogs/python-lists/#how-to-create-a-list-in-python)
3. [Access elements of a list](https://www.pylenin.com/blogs/python-lists/#access-elements-of-a-list)
4. [Slicing of Lists](https://www.pylenin.com/blogs/python-lists/#slicing-of-lists)
5. [Mixing positive and negative indices for slicing](https://www.pylenin.com/blogs/python-lists/#mixing-positive-and-negative-indices-for-slicing)
6. [Using steps in slicing](https://www.pylenin.com/blogs/python-lists/#using-steps-in-slicing)
7. [Reversing a list](https://www.pylenin.com/blogs/python-lists/#reversing-a-list)
8. [Changing elements of a list](https://www.pylenin.com/blogs/python-lists/#changing-elements-of-a-list)
9. [Adding elements to a list](https://www.pylenin.com/blogs/python-lists/#adding-elements-to-a-list)
10. [Deleting elements from a list](https://www.pylenin.com/blogs/python-lists/#deleting-elements-from-a-list)
11. [Common Python list Methods](https://www.pylenin.com/blogs/python-lists/#common-python-list-methods)

**Daily Exercise**

**Qns 1**

Write a Python program to get the largest number from a list.

**Qns 2**

Write a Python program to remove duplicates from a list.

**Qns 3**

Write a Python program to build a list containing 5 integer zeros.

### Day 8 - Python Tuples

### Day 9 - Python Dictionary

### Day 10 - Python Sets

## Control FLows in Python

### Day 11 - If else operation

### Day 12 - For loops

### Day 13 - While Loops

### Day 14 - Understanding use of break, continue and pass

## Iterators and Comprehensions

### Day 15 - Understanding Manual Iteration - __iter__ and __next__

### Day 16 - List Comprehensions

### Day 17 - Map, Filter, Zip and Reduce

## Functional Programming with Python

### Day 18 - Python Functions

### Day 19 - Understanding Variable Scope and Namespace

### Day 20 - *args vs **kwargs in Python Functions

### Day 21 - Python Closures

### Day 22 - Recursive Functions

### Day 23 - Lambda Functions

### Day 24 - Python Generators

### Day 25 - Python Decorators

## File Operations

### Day 26 - Basic File Operations with Python

### Day 27 - Understanding Python Modules

### Day 28 - Understanding file locations with `os` module

## Final Project - Building Sales Report with Excel and Python




