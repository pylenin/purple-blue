+++ 
draft = true
date = 2019-06-11T20:29:28+02:00
title = "Have you switched to Python 3? If not, Do it now"
description = "This article provides an overview of the benefits of switching from Python 2 to Python 3. You will also learn about painless migration strategies to port your old code to the new version easily."
tags = []
categories = []
externalLink = ""
series = []
+++

Tick Tock, Tick Tock!

The clock is ticking. We are nearing the end of Python 2. At the time of writing this blog, approximately 6 months 20 days and 2 hours are left for Python 2.7 to retire. Don't believe me? Check out the [Python Clock](https://pythonclock.org/). After January 1 2020, Python2.7 is not going to be supported anymore.

The buzz has already been there for a while now. If you are an active python programmer(no matter which level), you probably already know that Python 2 is soon going to become obsolete. Probably a lot of your friends, colleagues and people in the Python community have already suggested you to move on to Python 3. If you haven't done it yet, too bad. You should really be listening to your well wishers more. 

Moreover, you have been missing out on a lot of stuff that Python 3 brings to the table. In this blog, I am going to demonstrate all the advantages of using Python 3 that you have missed out if you are still stuck with python 2. I am also going to share some strategies to port your code to the latest version without going through a migrain or trouble while sleeping.

#### Advantages of Python 3 over 2

Let's check out the various differences between Python 2 and 3 and what advantages do they bring to the table.

1.  **Print is a function, not a statement**

    Print function has replaced print statement with some keyword arguments as additional features.
    Syntax wise, `print()` in Python 3 requires a parenthesis.
    ```python 
    print "My lucky number is", 7  # Python 2
    print("My lucky number is", 7) # Python 3
    ```

    In order to suppress a newline while printing, you had to use a **trailing comma** in Python 2.
    ```python2
    # Python 2 
    print 2,
    print 4
    ```
    The above snippet produces the following results.
    ```bash 
    2 4
    ```
    In order to reproduce the same results in Python 3, you have to use the `end` keyword argument.
    ```python 
    print(2, end =" ")
    print(4)
    ```
    
    My ultimate favorite addition is the `file` keyword argument to Python 3. The syntax for printing lines to files directly in Python 3 is much more readable than it was in Python 2.

    ```python3
    print >>open('test.txt','w'), "Printing to file" # Python 2
    print("Printing to file", file = open('test.txt','w')) # Python 3
    ```
                             
2.  **More relatable to Mathematics**

    1 divided by 2 is not 0. But that is what Python 2 said. In order to get the right value, you had to do one of the following.
    ```python  
    float(1)/2
    1.0/2
    1/2.0
    ```

    In Python 3, 1 divided by 2 is **0.5**. If you need the truncating behavior, use `//` instead of `/`.  

3.  **Meaningful comparisons**
    
    Unlike Python 2, there is no more comparison of anything to everything. 
    Try running the following in a Python 2 interpreter.
    ```python2
    print "one" > 2
    print None < 2
    print None < len
    ```
    Does it make sense? Amazingly, all of them return **True**.
    
    In Python 3, you cannot perform such operations anymore. When the operands don't have a meaningful natural ordering, the interpreter returns a **TypeError**.
    ```python3
    print("one" > 2)
    ```
    The above snippet returns the following error.
    ```bash
    Traceback (most recent call last):
    File <input_name>, line 1, in <module>
      print("one" > 2)
    TypeError: '>' not supported between instances of 'str' and 'int'
    ```
    This increases robustness of your code.
    
4.  **No more xrange()**

    In Python 2, `xrange` usually had the advantage of being faster than `range` when you are iterating over an iterable once. For example in a for loop.
    However in Python 3, `range` has been implemented as `xrange`. hence, the `xrange` doesn't exist anymore in Python 3. Returns a **NameError** if you use it.

5. **Extended Iterable Unpacking**

   With Python 3, we can perform advanced levels of iterable unpacking.
   
   For e.g.
   ```python3
   x, *y, z = range(5)
   
   print(x)
   print(y)
   print(z)
   ```
   When we run the above code in a Python 3 interpreter, we would get results like this.
   ```bash
   0
   [1, 2, 3]
   4
   ```
   This operation is not possible in Python 2. If you try to execute this with Python 2, you would receive a **SyntaxError**
   ```bash
   File <input_name>, line 1
    x, *y, z = range(5)
       ^
   SyntaxError: invalid syntax
   ```
   
6. 
    




