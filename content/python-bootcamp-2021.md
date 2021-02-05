---
title: "Python Bootcamp 2021"
date: 2021-01-30T20:01:48+05:30
draft: false
image: /img/pylenin_logo.png
---

### Welcome to the self paced Python Bootcamp 2021. 

This course has been designed, keeping in mind the current requirements of Python in the Job world and the minimum effort required to master Python as a choice of programming language.

In this Bootcamp, you will have the access to the best resources for every topic that should help you begin your journey in Python. Along with daily tutorials that include articles and videos, you will also be asked to test your learnings through a series of problems related to the topic.

**Why should you learn Python?**

Whether you are aiming to join a Fortune 500 corporation 
or desire to pursue a freelancing career in programming, 
it is important to know **what is hot in the industry**.

Python continues to be the language that is pretty much used in every company around the world for various purposes.
This also means that there is a huge potential for **you to land a job as a Python developer**.

**[Check out this article](https://www.pylenin.com/blogs/5-reasons-to-learn-python/) demonstrating 5 key reasons to learn Python in 2021**.

### Who is this Bootcamp for?

1. Beginners who have never programmed.
2. Programmers coming in from another language to learn Python.
3. Programmers who know the basics and want to level up their skills.

### How to follow along this Bootcamp?

**This bootcamp will begin on 1st of February and end on 28th of February, 2021.**

1. Every day, this page will be updated with the course materials for the topic you will be learning.
2. You will be provided with questions that you need to solve every day after you have gone through the course material.
3. The solutions to the asked questions shall be provided the next day.
4. **If you are joining late to the Bootcamp**, be sure to first try out the questions yourself before checking the solution. **DON'T CHEAT YOURSELF!**

### How to get notified when course materials are uploaded?

Every day, the course materials should be uploaded by **10 AM UTC**. 
A daily notification will be sent to all member of the [Official Pylenin Group](https://t.me/pythonwithpylenin) on Telegram 
when the course materials are uploaded. To receive the notification, **join the above Telegram group**.

### Where to ask doubts?

Asking doubts on Telegram could make the group **really SPAMMY!**.
To ensure that people are able to ask their doubts without being disturbed by others all day, we have created a [Facebook Group](https://www.facebook.com/groups/programmingcareerguidance).

**When you have a doubt:-**

1. Go to the above mentioned Facebook Group.
2. Create a Post specifying your doubt, **mentioning the Day of Bootcamp you are stuck on**.
3. Our admins will carefully go though the posts and approve them, if they are felt genuine.
4. **SPAM messages won't be allowed.**

##### Our average response time is 2 hours.

### Getting Started

##### Day 1 - Installing Python and Hello World!

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

##### Day 2 - Passing comments, Keywords and Identifiers

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

##### Day 3 - Python Variables and String Formatting

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

##### Day 4 - Python Booleans and Operators

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

### Python Data Types

#### Day 5 - Python Numbers

1. [Python Numbers, Arithmetic Operators and Mathematics](https://www.pylenin.com/blogs/python-arithmetic-operators/)
2. [Python isinstance() function - Figuring out the types](https://www.pylenin.com/blogs/python-isinstance/)

**Daily Exercise**

**Qns 1**

Write a Python Program to check if a number is odd or even.

**Qns 2**

Write a Python program to check if **any** of the variables below are **Integer types**.

```python3
x = "Pylenin"
y = 7
z = abs(-22)
```

[Reference Material](python-isinstance/#how-to-check-if-multiple-variables-are-a-single-type-in-python)

**Qns 3**

Convert the following decimals to Binary format by hand.

```bash
1. 4.25
2. 0.0625
3. 9.8
```

**Qns 4**

Read up the difference between `type()` and `isinstance()` in Python.

#### Day 6 - Python String

#### Day 4 - Python Lists

#### Day 5 - Python Tuples

#### Day 6 - Python Dictionary

#### Day 7 - Python Sets

### Control FLows in Python

#### Day 8 - If else operation

#### Day 9 - For loops

#### Day 10 - While Loops

#### Day 11 - Understanding use of break, continue and pass

### Iterators and Comprehensions

#### Day 12 - Understanding Manual Iteration - __iter__ and __next__

#### Day 13 - List Comprehensions

#### Day 14 - Map, Filter, Zip and Reduce

### Functional Programming with Python

#### Day 15 - Python Functions

#### Day 16 - Understanding Variable Scope and Namespace

#### Day 17 - *args vs **kwargs in Python Functions

#### Day 18 - Python Closures

#### Day 19 - Recursive Functions

#### Day 20 - Lambda Functions

#### Day 21 - Python Generators

#### Day 22 - Python Decorators

### File Operations

#### Day 23 - Basic File Operations with Python

#### Day 24 - Understanding Python Modules

#### Day 25 - Understanding file locations with `os` module

### Final Project - Building Sales Report with Excel and Python




