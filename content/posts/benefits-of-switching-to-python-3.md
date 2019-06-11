+++ 
draft = true
date = 2019-06-11T20:29:28+02:00
title = "Have you switched to Python 3? If not, Do it now"
slug = "benefits-of-switching-to-python-3" 
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

#### Differences you might already know

There are some obvious differences between Python 2 and 3, that most of us already know. Let's talk about them briefly.

1.  **Print is a function, not a statement**

    Print function has replaced print statement with some keyword arguments as additional features.
    Syntax wise, Python 3 requires a parenthesis.
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

3.  **No more xrange()**



