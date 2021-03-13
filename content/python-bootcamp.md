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

[Solution](https://www.pylenin.com/python-examples/largest-number-in-list/)

**Qns 2**

Write a Python program to remove duplicates from a list.

[Solution](https://www.pylenin.com/python-examples/remove-duplicates-from-list/)

**Qns 3**

Write a Python program to build a list containing 5 integer zeros.

**Solution**

[Solution](https://www.pylenin.com/blogs/python-lists/#adding-elements-to-a-list)

### Day 8 - Python Dictionary

1. [Working with a Python Dictionary](https://youtu.be/FvD0Zum8L3s)

**Further Reading**

2. [Dictionaries in Python](https://www.pylenin.com/blogs/python-dictionary/)

**Daily Exercises**

1. Write a Python code to merge 2 dictionaries as shown below.

   
        capital_dict_1 = {"India": "New Delhi",
		          "Pakistan": "Islamabad",
		          "Nigeria": "Abuja",
		          "Zambia": "Lusaka"}

        capital_dict_2 = {"Peru": "Lim", 
                  "Ghana": "Accra"}


[Solution - Use the asterisk operator](https://www.pylenin.com/blogs/python-dictionary/#adding-new-key-values-to-a-dictionary)

2. Write a Python program to sort a dictionary by value.

[Solution](https://www.pylenin.com/blogs/python-dictionary/#sorting-a-dictionary)

3. Write a Python script to check whether a given key already exists in a dictionary.

[Solution - Use the get() method](https://www.pylenin.com/blogs/python-dictionary/#accessing-keys)

4. Write a Python program to sum all the items in a dictionary.

**Solution**

```python3
GDP_2017 = {"India": 6.6, 
            "Zambia": 4.1, 
            "Nigeria": 0.8,
            "Peru":2.5, 
            "Ghana": 8.5
           }
print(sum(GDP_2017.values()))

>>> 22.5
```

### Day 9 - Python Tuples

1. [Understanding usage of Python Tuples](https://youtu.be/0lojav6fSjE)

**Further Reading**

2. [Characteristics of Tuples](https://www.pylenin.com/blogs/python-tuples/#characteristics-of-tuples)
3. [How to create a tuple in Python?](https://www.pylenin.com/blogs/python-tuples/#how-to-create-a-tuple-in-python)
4. [Concatenating Tuples](https://www.pylenin.com/blogs/python-tuples/#concatenating-tuples)
5. [Access elements of a tuple](https://www.pylenin.com/blogs/python-tuples/#access-elements-of-a-tuple)
6. [Slicing of Tuples](https://www.pylenin.com/blogs/python-tuples/#slicing-of-tuples)
7. [Using steps in slicing Tuples](https://www.pylenin.com/blogs/python-tuples/#using-steps-in-slicing)
8. [Deleting a tuple](https://www.pylenin.com/blogs/python-tuples/#deleting-a-tuple)
9. [Commonly used methods with tuples](https://www.pylenin.com/blogs/python-tuples/#commonly-used-methods-with-tuples)
10. [Tuple Swap](https://www.pylenin.com/blogs/python-tuples/#tuple-swap)
11. [When to choose Tuples over lists?](https://www.pylenin.com/blogs/python-tuples/#lists-vs-tuples)

**Daily Exercise**

**Qns 1**

Change the values of the below variables without using a 3rd variable.

```python3
x = "Apple"
y = "Banana"
```

[Solution](https://www.pylenin.com/blogs/python-tuples/#tuple-swap)

**Qns 2**

Sort the below tuple in increasing order of the length of each element.

```python3
my_tuple = ("Pylenin", "loves", "Python")
```

**Solution**

```python3
my_tuple = ("Pylenin", "loves", "Python")

my_list = list(my_tuple)
my_list.sort(key=len)

print(tuple(my_list))
```

**Qns 3**

Convert the keys and values of the dictionary to tuple.

```bash
my_dict = {"name" : "Pylenin",
            "verb" : "loves",
            "object": "Python"}

Result ==> (("name", "Pylenin"), ("verb", "loves"), ("object", "Python"))
```

**Solution**

```python3
my_dict = {"name" : "Pylenin",
            "verb" : "loves",
            "object": "Python"}

my_tuple = []

for key, value in my_dict.items():
    my_tuple.append(tuple([key, value]))
print(tuple(my_tuple))
```

### Day 10 - Python Sets

1. [An overview of Python sets](https://www.pylenin.com/blogs/python-sets/)
2. [Mathematical Operations with Python Sets](https://www.pylenin.com/blogs/python-sets/#mathematical-operations-with-sets)
3. [Methods to use with Sets](https://www.pylenin.com/blogs/python-sets/#using-methods-with-sets)

**Daily Exercises**

**Qns 1**

Write a Python program to check if a set contains one or more items that are False.

**Solution - Use [any() method](https://www.pylenin.com/blogs/python-any-all/)**

```python3
x = {1, 0, True, False}

print(any(x))
```

**Qns 2**

Write a Python program to return all the unique elements of a list.

**Solution - Convert the list to a set**

```python3
x = [1, 2, 3, 4, 1, 2, 3, 4]
print(set(x))

>>> {1, 2, 3, 4}
```

**Qns 3**

Write a Python program to return the common elements between 2 sets.

```python3
x = {1, 2, 3}
y = {7, 5, 3}
```

[Solution](https://www.pylenin.com/blogs/python-sets/#intersection-of-2-sets)

**Qns 4**

Write a Python program to check if there are any common elements between 2 lists.

[Solution - Convert lists to sets](https://www.pylenin.com/blogs/python-sets/#intersection-of-2-sets)

```python3
x = [1, 2, 3]
y = [2, 3, 4]

set_x = set(x)
set_y = set(y)

print(set_x & set_y)
```

## Control FLows in Python

### Day 11 - If else operation

1. [Python Decision Making with if, elif and else](https://youtu.be/LEQNrCdV_Cg)

**Further Reading**

1. [Python If, elif and else (With Examples)](https://www.pylenin.com/blogs/if-else-python/)

**Daily Exercises**

**Qns 1**

Write a Python program to take values of length and breadth of 
a rectangle from user and check if it is square or not.

**Solution**

```python3
length = int(input("Enter length (only positive numbers)==>"))
breadth = int(input("Enter breadth (only positive numbers)==>"))

if length == breadth:
    print("It is a square")
else:
    print("Its not a square")
```

**Qns 2**

Write a Python program to take two int values from user 
and print greatest among them.

**Solution**

```python3
first = int(input("Enter first number ==> "))
second = int(input("Enter second number ==> "))
if first>second:
  print("Greatest is",first)
elif second>first:
  print("Greatest is",second)
else:
  print("Both are equal")
```

**Qns 3**

A company decided to give bonus of 5% to employee if his/her year of service is more than 5 years.
Write a Python program, asking user for their salary and year of service and print the net bonus amount.

**Solution**

```python3
salary = float(input("Enter your salary ==> "))
experience = float(input("Enter your experience in years ==> "))

bonus_amount = None

if experience > 5:
    bonus_amount = salary*.05
else:
    bonus_amount = 0

print(bonus_amount)
```

**Qns 4**

A school follows the following grading system:

* Below 25 - F
* 25 to 45 - E
* 45 to 50 - D
* 50 to 60 - C
* 60 to 80 - B
* Above 80 - A

Ask user to enter marks and print the corresponding grade.

[Similar Solution](https://www.pylenin.com/blogs/if-else-python/#example-3)

### Day 12 - For loops

1. [Youtube video on For loops](https://youtu.be/m-mdlS4ynis)

**Further Readings**

1. [Python for loops(With Examples)](https://www.pylenin.com/blogs/python-for-loop/)
2. [Using range() function in Python](https://www.pylenin.com/blogs/python-for-loop/#python-range-function)
3. [Nested for loops](https://www.pylenin.com/blogs/python-for-loop/#nested-for-loops)
4. [Usage of zip()](https://www.pylenin.com/blogs/python-zip-function/)

**Daily Exercise**

**Qns1**

Write a Python program to find the largest number in a list.

[Solution](https://www.pylenin.com/python-examples/largest-number-in-list/)

**Qns 2**

Write a Python program to remove duplicates from a list.

[Solution](https://www.pylenin.com/python-examples/remove-duplicates-from-list/)

**Qns 3**

From a list containing ints, strings and floats, make three lists to store them separately. [Reference Article](https://www.pylenin.com/blogs/type-vs-isinstance/)

**Solution**

```python3
my_list = [1, "Pylenin", 5.6]

int_list = []
str_list = []
float_list = []

for elem in my_list:
    if isinstance(elem, int):
        int_list.append(elem)
    elif isinstance(elem, str):
        str_list.append(elem)
    elif isinstance(elem, float):
        float_list.append(elem)
    else:
        print("Ignoring other data types")

print(int_list, str_list, float_list, sep="\n")
```

**Qns 4**

Using `range(1,50)`, make two lists, one containing all even numbers and other containing all odd numbers.

**Solution - Similar to above problem.** [Refer here](https://www.pylenin.com/blogs/python-for-loop/#python-range-function) to learn more about `range()`.

### Day 13 - While Loops

1. [Youtube video on While loops](https://youtu.be/rWVtBYYIbz0)

**Further readings**

1. [While loops in Python (With Examples)]

**Daily Exercise**

**Qns 1**

Write a Python program to convert the `input_list` to `output_list`.

```python3
input_lst = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

output_lst = [[1, 4, 7], [2, 5, 8], [3, 6, 9]]
```

[Solution](https://www.pylenin.com/blogs/python-zip-function/#solve-a-competitive-interview-question)

**Qns 2**

Write a Python program to solve the [Fizbuzz problem](https://youtu.be/t4I_WOfQn70)

[Solution](https://youtu.be/1khdzmUHhC4)

**Qns 3**

Write a program to find the greatest common divisor (GCD) or highest common factor (HCF) of two numbers.

[Solution](https://www.pylenin.com/python-examples/find-hcf-or-gcd/)

**Qns 4**

Solve this [Goldman Sachs Coding Interview Question](https://youtu.be/kKWV8T6SAvU)

### Day 14 - Understanding use of break, continue and pass

1. [Use of break, continue and pass in for loops - Youtube video starts at 4:32](https://youtu.be/m-mdlS4ynis)
2. [Use of break, continue and pass in for loops - Youtube video starts at 4:02](https://youtu.be/rWVtBYYIbz0)

**Further Readings**

1. [Use of break statement in Python](https://www.pylenin.com/blogs/break-continue-pass/#break-statement-in-python)
2. [Use of continue statement in Python](https://www.pylenin.com/blogs/break-continue-pass/#continue-statement-in-python)
3. [Use of pass statements in Python](https://www.pylenin.com/blogs/break-continue-pass/#pass-statement-in-python)

**Daily Exercises**

**Qns 1**

Place a break statement in the for loop so that it prints from 
0 to 7 only (including 7)

```python3
for i in range(100):
    print(i)
```

**Solution**

```python3
for i in range(100):
    print(i)
    if i == 7:
        break
```

**Qns 2**

Write a Python program that prints all the numbers from 0 to 10 
except multiples of 3 (use continue).

**Solution**

```python3
for i in range(11):
    if i%3==0:
        continue
    print(i)
```

**Qns 3**

Write a Python program to construct the following pattern.

```python3
* 
* * 
* * * 
* * * * 
* * * * * 
* * * * 
* * * 
* * 
*
```

[Solution](https://www.pylenin.com/python-examples/printing-pyramid-patterns/)

## Iterators and Comprehensions

### Day 15 - Understanding Manual Iteration - __iter__ and __next__

1. [Sequence vs Iterable vs Iterator](https://www.pylenin.com/blogs/python-iterators/#difference-between-sequence-and-an-iterable)
2. [next() in Python](https://www.pylenin.com/blogs/python-iterators/#next-in-python)
3. [for loop - Behind the scenes](https://www.pylenin.com/blogs/python-iterators/#for-loop-behind-the-scenes)
4. [A file object is an iterator](https://www.pylenin.com/blogs/python-iterators/#is-a-file-object-an-iterator)
5. [Unpacking an iterable in Python](https://www.pylenin.com/blogs/unpacking-iterables-in-python/)

**Daily Exercise**

**Qns 1**

Write a Python program to convert `range(7)` into an iterator 
and use the `next()` method to print all its content.

**Solution**

```python3
n = 7
my_iter = iter(range(n))
i = 0
while i < 7:
    print(next(my_iter))
    i+=1
```

**Qns 2**

What will the following code return?

```python3
my_info = ["Lenin", "Mishra", 28, "Amsterdam"]

_, value = my_info

print(value)
```

**Solution**

It will return an error. The correct way of unpacing would be to use `*value`.

```python3
my_info = ["Lenin", "Mishra", 28, "Amsterdam"]

_, *value = my_info

print(value)
>>> ['Mishra', 28, 'Amsterdam']
```

**Qns 3**

What will the following code return?

```python3
numbers = [1, 2, 3, 4, 5]
first, *middle, last = numbers

print(middle)
```

[Solution](https://www.pylenin.com/blogs/unpacking-iterables-in-python/#unpacking-arbitrary-length-iterables)

### Day 16 - Python Functions

1. [Youtube video on Python Functions](https://youtu.be/IjsjcJ_5R-g)

**Further Readings**

1. [Functions in Python](https://www.pylenin.com/blogs/python-functions/)
2. [Understand the use of Parameters and Arguments](https://www.pylenin.com/blogs/python-functions/#parameters-in-functions)
    1. [Positional vs Keyword Arguments](https://www.pylenin.com/blogs/python-functions/#positional-arguments-vs-keyword-arguments)
    2. [Default Arguments](https://www.pylenin.com/blogs/python-functions/#default-arguments)
    3. [Variable Length Arguments](https://www.pylenin.com/blogs/python-functions/#variable-length-argument)
    
3. [Advantages of Functions](https://www.pylenin.com/blogs/python-functions/#advantages-of-functions)
    
**Daily Exercises**

**Qns 1**

Write a function to convert minutes into seconds.

**Solution**

```python3
def mins_to_secs(min):
    return min*60
```

**Qns 2**

Write a Python function to return the remainder of 2 numbers 
passed as argument. **Note** - You should divide the bigger with smaller number.

**Solution**

```python3
def remainder(x, y):
    if x > y:
        return x%y
    return y%x
```

**Qns 3**

Write a function such that it can accept a variable length of 
argument and print all arguments value on different lines

[Solution](https://www.pylenin.com/blogs/python-functions/#variable-length-argument)

**Qns 4**

Create a function in such a way that it should accept 
an employee's name, and it’s salary and display both. 
If the salary is missing in function call, it should show 
it as 9000.

**Solution**

```python3
def employee_salary(employee, salary=9000):
    print(employee, salary)

employee_salary("Pylenin", 1800000)
employee_salary("Lenin")
```

### Day 17 - Understanding Variable Scope and Namespace

1. [Youtube Video on Variable Scope and Namespace](https://www.pylenin.com/blogs/variable-scope-namespace-python/#youtube-video)

**Further Reading**

1. [What is Namespace?](https://www.pylenin.com/blogs/variable-scope-namespace-python/#python-namespace/)
2. [Global vs Local vs Nonlocal](https://www.pylenin.com/blogs/variable-scope-namespace-python/#global-vs-local-vs-nonlocal-scope)
3. [global keyword](https://www.pylenin.com/blogs/variable-scope-namespace-python/#global-statement)
4. [nonlocal keyword](https://www.pylenin.com/blogs/variable-scope-namespace-python/#nonlocal-scope)
5. [Use of globals() and locals() built-in function](https://www.pylenin.com/blogs/variable-scope-namespace-python/#built-in-functions---globals-and-locals)

**Daily Exercise**

**Qns 1**

What is the output of the following code and why?

```python3
X = 'Spam'
def func():
    X = 'NI!'

func()
print(X)
```

**Solution**

```bash
Spam
```
Python will refer to `X` in the global namespace.

**Qns 2**

What is the output of the following code and why?

```python3
X = 'Spam'
def func():
    global X
    X = 'NI!'

func()
print(X)
```

**Solution**

```bash
NI!
```
By using the `global` keyword, 
Python now uses the `X` in the global namespace.

### Day 18 - *args vs **kwargs in Python Functions

1. [Youtube video on *args vs **kwargs](https://www.pylenin.com/blogs/args-vs-kwargs-python/#youtube-video)

**Further Readings**

1. [*args vs **kwargs](https://www.pylenin.com/blogs/args-vs-kwargs-python/)

**Daily Exercise**

**Qns 1**

What is the output of the below code?

```python3
def pretty_printing(x, *args, **kwargs):
        print(x)
        print(args)
        print(kwargs)

    pretty_printing("Lenin", "Mishra", "Pylenin", "Python", country="India")
```

**Qns 2**

Print all the keys and values passed to the below function

```python3
def random_person(**kwargs):
    <write your code here>

random_person(name="Lenin", age=28, sex="Male")
```

### Day 19 - Python Closures

1. [Youtube video on Python CLosures](https://www.pylenin.com/blogs/python-closures/#youtube-video)

**Further Reading**

1. [Python Closures - Explanation](https://www.pylenin.com/blogs/python-closures/)

**Daily Exercises**

**Qns 1**

What is the output of the below code?

```python3
def outerFunction(msg):  
    text = msg  
  
    def innerFunction():  
        print(text)  

    return innerFunction   
  
if __name__ == '__main__':  
    myFunction = outerFunction('Pylenin')  
    myFunction() 
```

**Solution**

```bash
Pylenin
```

### Day 20 - Recursive Functions

1. [Youtube video on Recursion](https://www.pylenin.com/blogs/recursive-function-python/#youtube-video)

**Further Reading**

1. [What is Recursion?](https://www.pylenin.com/blogs/recursive-function-python/#what-is-recursion)
2. [Advantages and Disadvantages of Recursion](https://www.pylenin.com/blogs/recursive-function-python/#advantages-of-recursion)

**Daily Exercises**

**Qns 1**

Find the sum of the below list using Recursion.

```python3
x = [1, 2, 3, 4, 5, 6]
```

**Solution**

```bash
def addition(lst):
    if len(lst) > 1:
        return lst[0] + addition(lst[1:])
    else:
        return lst[0]

print(addition([1, 2, 3, 4, 5]))
```

**Qns 2**

Find the sum of the below arbitrarily structured list.

```python3
x = [[1, 2], [[3], 4, [5, 6], 7, [8,9]]]
```

**Solution**

```python3
def addition(lst):
    total = 0
    for num in lst:
        if type(num) != list:
            total += num
        else:
            total += addition(num)

    return total

print(addition([[1, 2], [[3], 4, [5, 6], 7, [8,9]]]))
```

### Day 21 - Lambda Functions

1. [Youtube video on Lambda Functions](https://www.pylenin.com/blogs/lambda-function-python/#youtube-video)

**Further Readings**

1. [Syntax of Lambda Function](https://www.pylenin.com/blogs/lambda-function-python/#syntax-of-lambda-functions)
2. [Multiple arguments with lambda function](https://www.pylenin.com/blogs/lambda-function-python/#multiple-arguments-with-lambda-function)

**Daily Exercises**

1. Write a lambda function that adds 15 to a given number passed in as an argument.
   
    **Solution**
    ```python3
    my_func = lambda x: x+15
    print(my_func(15))
    ```

2. Write a lambda function that takes one argument multiplied with an unknown given number.
   
    **Solution**
    ```python3
    def my_func(n):
        return lambda x: x*n

    print(my_func(5)(8))
    ```   


3. Sort the below list of tuples using lambda.
    
    ```python3
    subject_marks = [('English', 88), ('Science', 90), ('Maths', 97), ('Social sciences', 82)]
    ```
   
    **Solution**
    ```python3
    subject_marks = [('English', 88),
                 ('Science', 90),
                 ('Maths', 97),
                 ('Social sciences', 82)]

    subject_marks.sort(key=lambda x:x[1]) # Sort based on 2nd element
    print(subject_marks)
    ```

### Day 22 - List Comprehensions

1. [Youtube Video on List Comprehensions](https://www.pylenin.com/blogs/python-list-comprehension/#youtube-video)

**Further Reading**

1. [Using List Comprehensions in Python](https://www.pylenin.com/blogs/python-list-comprehension/)
2. [Using conditions in List comprehension](https://www.pylenin.com/blogs/python-list-comprehension/#using-conditions-in-list-comprehensions)
3. [Nested if condition in List Comprehensions](https://www.pylenin.com/blogs/python-list-comprehension/#example-5---nested-if-with-list-comprehension)

**Daily Exercises**

1. Using list comprehensions, create a list containing tuples of every 
   word and its length from this given sentence - `Pylenin writes blogs on Python`
2. Using list comprehensions, create a new list `newlist` from the given list `numbers`, which contains only the positive numbers.
    ```python3
    numbers = [-9, 10.2, 11, 14, -5, -0.00001]
    ```


### Day 23 - Map, Filter, Zip and Reduce

### Day 24 - Python Generators

### Day 25 - Python Decorators

## File Operations

### Day 26 - Basic File Operations with Python

### Day 27 - Understanding Python Modules

### Day 28 - Understanding file locations with `os` module

## Final Project - Building Sales Report with Excel and Python




