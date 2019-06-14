---
title: "10 benefits of using Python 3 over 2 "
description: "This article provides an overview of the benefits of switching from Python 2 to Python 3. The various advantages have been explained with practical examples for your better understanding."
date: 2019-06-11T20:29:28+02:00
draft: false
image: /img/byepython2.png
categories: ['python 3 vs python 2']
---

<a href="https://twitter.com/pylenin?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large" data-show-screen-name="false" data-show-count="false">Follow @pylenin</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

![good-bye-python-2](/img/byepython2.png)


Tick Tock, Tick Tock!

The clock is ticking. We are nearing the end of Python 2. At the time of writing this blog, approximately 6 months 20 days and 2 hours are left for Python 2.7 to retire. Don't believe me? Check out the [Python Clock](https://pythonclock.org/). Python2.7 is not going to be supported anymore after **January 1, 2020**.

The buzz has already been there for a while now. If you are an active python programmer (no matter which level), you probably already know that Python 2 is soon going to become obsolete. Probably a lot of your friends, colleagues and people in the Python community have already suggested you to move on to Python 3. If you haven't done it yet, too bad. You should really be listening more keenly to your well wishers. 

Moreover, you have been missing out on a lot of stuff that Python 3 brings to the table. Python 3 has a lot of key attributes that sets it aside from Python 2.
In this blog, I am going to demonstrate the 10 most important differences (In my humble opinion) between Python 2 and 3 and the advantages associated with them.

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

    1 divided by 2 is **not 0**. But that is what happened in Python 2. In order to get the right value, you had to do one of the following.
    ```python  
    float(1)/2
    1.0/2
    1/2.0
    ```

    In Python 3, 1 divided by 2 is **0.5** (which is what it should be). If you need the truncating behavior, use `//` instead of `/`.  

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
    This is a great enhancement as it will drastically improve the robustness of your code.
    
4.  **No more xrange()**

    In Python 2, `xrange` usually had the advantage of being faster than `range` when you are iterating over an iterable once. For example in a for loop.
    However in Python 3, `range` has been implemented as `xrange`. Hence, the `xrange` doesn't exist anymore in Python 3. Returns a **NameError** if you use it.
    
    So no need to switch between `range` and `xrange`. Just use **range**.

5.  **Extended Iterable Unpacking**

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
   
6.  **Unicode support**

    In Python 2, we had 2 text types - `str` and `unicode`. The `str` type was mostly limited to the **ASCII characters**. It also had one byte type called `bytearray`. 
    
    In Python 3, we only have one text type, which is equivalent to `unicode` type in Python 2. We also have 2 byte types - `bytes` and `bytearray`. 
   
    In Python 2, you had to prefix a string with `u` in order to make it unicode. For example,
    ```python2
    print type('Pylenin')
    print type(u'Pylenin')
    ``` 
    will produce the following results.
    ```bash
    <type 'str'>
    <type 'unicode'>
    ```
    However in Python 3, since `str` is the only text type, it handles unicode by default.
   
    In Python 2, you can easily concatenate a `str` type and `byte` type. However, its not possible in Python 3.
    ```python 
   
    x = "Python 2"+b" will remain forever"
   
    # Python 2 
    print x
    print type(x)
    # Python 3
    print(x) 
    print(type(x))
    ```
    The snippet for Python 2 will work and the overall type will be casted to `str`. However for Python 3, it will return a **TypeError**.
    ```bash
    # Python 2
    Python 2 will remain forever 
    <type 'str'>

    # Python 3
    Traceback (most recent call last):
    File <input_name>, line 1, in <module>
      x = "Python 2"+b" will remain forever"
    TypeError: must be str, not bytes
    ```
   
7.  **Fixed syntax for inequality operator**

    In Python 2, both `!=` and `<>` used to work perfectly fine as inequality operators. 
    ```python2
    print 2!=3
    print 2<>3
    ```
    However in python 3, the alternative of `<>` has been completely removed. Basically now there is only one way of doing it. By using the `!=` operator.
   
8.  **raw_input() is gone! Just input()**
    
    In Python 2, we had both `input()` and `raw_input()`. The difference was that, `input()` was able to read and store any data type and store it as the same type. In order to store every input as a string, you had to use `raw_input()`. Let's look at some examples.
    ```python2
    # Python 2
    >>> my_input = input('Enter something: ')

    Enter something: 123
    >>> type(my_input)
    <type 'int'>
   
    >>> my_input = input('Enter something: ')

    Enter something: "Pylenin"
    >>> type(my_input)
    <type 'str'>
   
    >>> my_input = input('Enter something: ')

    Enter something: Pylenin # Without quotation
    Traceback (most recent call last):
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    File "<string>", line 1, in <module>
    NameError: name 'Pylenin' is not defined
    ```
    Watch how it throws an error when we pass `Pylenin` without any quotations. This is really dangerous as you could expect malicious behavior in a lot of situations.
    In Python 3, the `raw_input()` has been removed. There is only the `input()` method and it parses the user input as string for every data type.
    ```python3
    # Python 3
    >>> my_input = input('Enter something: ')

    Enter something: 123
    >>> type(my_input)
    <class 'str'>
   
    >>> my_input = input('Enter something: ')

    Enter something: "Pylenin"
    >>> type(my_input)
    <class 'str'>
   
    >>> my_input = input('Enter something: ')

    Enter something: Pylenin # Without quotation
    >>> type(my_input)
    <class 'str'>
    ```
   
9.  **Iterables instead of list**

    In Python 2, built-in functions like range, zip, map and filter used to return a list. However in Python 3, they return **iterables**. If it is important for you to convert it into list, use the `list()` method.
   
    Now does it make sense? In some way, **Yes!** Usually we iterate only once over them. Hence, it is helpful in saving memory.
   
    Also dictionary methods like `keys()`, `values()` and `items()` do not return lists anymore. They return views. 
    ```python3
    x = {"a":1,"b":2}
   
    print(type(x.keys()))
    print(type(x.values()))
    print(type(x.items()))
    ```
    The above snippet will return the following result.
    ```bash
    <class 'dict_keys'>
    <class 'dict_values'>
    <class 'dict_items'>
    ```

10. **Raising and handling exceptions**
    
    One of my favorite improvements in Python 3 is the way it raises and handles exceptions.
    Let's compare the results of executing a small code in Python 2 with Python 3.
    ```python2
    # Python 2
    
    class FirstClass():
      def exc(self):
        raise Exception("Error in first class")
    
    class SecondClass():
      def exc(self):
        foo = FirstClass()
        try:
          foo.exc()
        except:
          raise Exception("Error in second class")
    x = second_class()
    print x.exc() 
    ```
    Now this is certainly not the best implementations of **Classes** in Python. However for this purpose, it will do the job.
    
    When you run the above code, you will only see the exception raised in the second class.
    ```bash
    Traceback (most recent call last):
      File <input>, line 13, in <module>
        print x.exc()
      File <input>, line 11, in exc
        raise Exception("Error in second class")
    Exception: Error in second class
    ```
    Now this is not really convenient for debugging. If you go through the code, you will see that there is a `try` and `except` block in the `SecondClass`. We first try to call the `exc()` method lying within the `FirstClass`. If that block fails, we raise an **exception**. 
    
    Now ideally, we would want both the exceptions to be shown to us. Because the truth is, the `except` block is being executed only after the `try` block fails. Python 2 fails to deliver on this traceback.
    However, Python 3 provides a better overview of the exception.
    ```python3
    Traceback (most recent call last):
      File <input>, line 9, in exc
        foo.exc()
      File <input>, line 3, in exc
        raise Exception("Error in first class")
    Exception: Error in first class
    
    During handling of the above exception, another exception occurred:
    
    Traceback (most recent call last):
      File <input>, line 13, in <module>
        print(x.exc())
      File <input>, line 11, in exc
        raise Exception("Error in second class")
    Exception: Error in second class
    ```
    As you can see, we are warned about both the exceptions in Python 3. This arrangement is therefore much more better for debugging purposes.
    
Like I mentioned earlier, you are missing out on a lot of things if you haven't switched to Python 3 yet. There are more examples where Python 3 performs both syntactically and in terms of performance over Python 3. However these 10 changes were the ones that I thought were more relevant. At least I tend to notice them very easily.

So if you haven't switched yet, I recommend you to make the jump now. Before it is too late!
    


