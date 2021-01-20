---
title: "Catching Multiple Exception in Python"
description: "Learn to catch multiple exceptions in Python using try and except."
date: 2021-01-20T08:21:32+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
categories_weight: 3
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

**Pre-requisite knowledge**
1. [Python Exception Handling with Try, Except, Else and Finally](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [Built-in Exception Classes in Python](https://www.pylenin.com/tags/built-in-exception-class/)

Let's say, you are trying to print an element of a list through [user input](https://www.pylenin.com/blogs/how-input-works-python/). 
You are using `IndexError` exception in your except block to make sure, the program doesn't crash if user inputs an index that doesn't exist.

**Code**

```python3
x = [1, 2, 3, 4]

while True:
    user_input = input("Guess a position ==> ")
    try:
        print(x[int(user_input)])
        break
    except IndexError as e:
        print(f"Guess a number between {-1*len(x)} and {len(x)-1}")
```

Now, try to run the above code in your [Python IDE](https://www.pylenin.com/tags/python-ide/).
As long as user enters an integer, the code will run fine.

**Output - 1**

```bash
Guess a position ==> 5
Guess a number between -4 and 3
Guess a position ==> -1
4
```

**However, what happens if user enters a float?**

**Output - 2**

```bash
Guess a position ==> 3.5
Traceback (most recent call last):
  File "some_file_location", line 6, in <module>
    print(x[int(user_input)])
ValueError: invalid literal for int() with base 10: '3.5'
```

Now your program has crashed due to a `ValueError` exception. You hadn't taken this exception into account.

There are multiple solutions to this problem.

##### Solution 1 - Multiple `except` blocks for multiple exceptions

**Code**

```python3
x = [1, 2, 3, 4]

while True:
    user_input = input("Guess a position ==> ")
    try:
        print(x[int(user_input)])
        break
    except IndexError as e:
        print(f"Guess a number between {-1*len(x)} and {len(x)-1}")
    except ValueError as e:
        print("You are only allowed integers")
```

**Output**

```bash
Guess a position ==> 3.5
You are only allowed integers
Guess a position ==> 10
Guess a number between -4 and 3
Guess a position ==> 1
2
```

##### Solution 2 - Catch Multiple Exceptions in a single except block

**Code**

```python3
x = [1, 2, 3, 4]

while True:
    user_input = input("Guess a position ==> ")
    try:
        print(x[int(user_input)])
        break
    except (IndexError, ValueError) as e:
        if e.__class__.__name__ == 'IndexError':
            print(f"Guess a number between {-1 * len(x)} and {len(x) - 1}")
        elif e.__class__.__name__ == 'ValueError':
            print("You are only allowed integers")
        else:
            print(f"Error occured - {e}")
```

**Output**

```bash
Guess a position ==> 10
Guess a number between -4 and 3
Guess a position ==> 1.5
You are only allowed integers
Guess a position ==> 2
3
```

Solution 3 - Use the base `Exception` class

**Code**

```python3
x = [1, 2, 3, 4]

while True:
    user_input = input("Guess a position ==> ")
    try:
        print(x[int(user_input)])
        break
    except Exception as e:
        if e.__class__.__name__ == 'IndexError':
            print(f"Guess a number between {-1 * len(x)} and {len(x) - 1}")
        elif e.__class__.__name__ == 'ValueError':
            print("You are only allowed integers")
        else:
            print(f"Error occured - {e}")
```

**Output**

```bash
Guess a position ==> 10
Guess a number between -4 and 3
Guess a position ==> 3.5
You are only allowed integers
Guess a position ==> "1"
You are only allowed integers
Guess a position ==> 2
3
```

Check out how to work with [Python Built-in Exception classes in Python](https://www.pylenin.com/tags/built-in-exception-class/).

#### Related Articles

1. [Try, Except, Else and Finally in Python](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [ZeroDivisionError Exception in Python](https://www.pylenin.com/blogs/zero-division-error-python/)
3. [OverflowError Exception in Python](https://www.pylenin.com/blogs/overflow-error-python/)
4. [ArithmeticError Exception in Python](https://www.pylenin.com/blogs/arithmetic-error-python/)
5. [KeyError Exception in Python](https://www.pylenin.com/blogs/key-error-python/)
6. [IndexError Exception in Python](https://www.pylenin.com/blogs/index-error-python/)
7. [LookupError Exception in Python](https://www.pylenin.com/blogs/lookup-error-python/)
8. [StopIteration Exception in Python](https://www.pylenin.com/blogs/stop-iteration-error-python/)
9. [NameError Exception in Python](https://www.pylenin.com/blogs/name-error-python/)
10. [FileNotFoundError Exception in Python](https://www.pylenin.com/blogs/file-not-found-error-python/)
11. [TypeError Exception in Python](https://www.pylenin.com/blogs/type-error-python/)