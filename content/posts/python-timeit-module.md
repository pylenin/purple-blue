---
title: "Python Timeit Module (With Examples)"
description: "Learn how to use the python timeit module to measure the execution time of your Python code."
date: 2019-09-22T14:37:05+02:00
draft: false
image: /img/timeit/timeit.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

##### Sections Covered
1. [Python timeit vs time module](#python-timeit-vs-time-module)
1. [Using timeit in your Python script](#using-timeit-in-your-python-script)
2. [Using timeit with Python functions](#using-timeit-with-python-functions-with-arguments)
3. [Using timeit on commandline](#using-timeit-on-commandline)

#### Python timeit vs time module
Let's assume you want to return all the characters in a string as a python list.

You can follow 2 different approach.

1. **Use a for loop**
                
        name = "Pylenin"
        result_list = []
        for char in name:
            result_list.append(char)
   
        #Result
        >>> ['P', 'y', 'l', 'e', 'n', 'i', 'n']


2. **Use a list comprehension**
   
        name = "Pylenin"
        result_list = [char for char in name]
   
        #Result
        >>> ['P', 'y', 'l', 'e', 'n', 'i', 'n']
   

Both these approaches give you the same result. But which one is **fastest**?

The `timeit` module in python helps you to measure execution time of your Python code. This module provides you with much precise measurements compared to the `time` module as it ignores the background processes running on your system, which might have an impact on your code execution.

Another advantage of using the `timeit` module vs `time` is that, by default it performs **1 million** executions before providing you with an estimate. This allows you to have statistically relevant measurements for your python code.

#### Using timeit in your Python script

Let's use the `timeit` module to get some insights.

1. **Step 1 - Import the timeit module**

        import timeit

2. **Step 2 - Write the setup code**
    
    The setup code is the part of code that is essential for you to run the main code that does all the computing.
   
    Think of all the libraries you are importing and the variables you are declaring. These multiple lines of code qualify as a **setup code**. 
        
        #Step 2 
        setup_code = """
        name = "Pylenin"
        result_list = []
        """
        
3. **Step 3 - Write your main code**

    The main code is basically the snippet of code, whose execution time you want to measure. 
       
    In our case, we want to compare the execution times of a **for loop** vs **list comprehension**. Those snippets will go in our main code.
        
        #Step 3
        main_code = """
        for char in name:
            result_list.append(char)
        """
        
4. **Step 4 - Call the `timeit` function**

    With both the `main_code` and `setup_code` statements defined, we can pass those as parameters into our `timeit` function.
    
    The `stmt` parameter takes in the `main_code` statement. The `setup` parameter takes in the `setup_code` statement. The `number` parameter takes in the number of executions(by default it is 1 million). You can pass in multiple lines of code as part of your `main_code` and `setup_code` in your `timeit` function.
    
        #Step 4
        print(timeit.timeit(stmt=main_code,
                    setup=setup_code,
                    number=10000))
    
    **The execution time of the setup code is excluded from the results.**   


Overall, this is what our code will look like.

```python3
# Python timeit Example
import timeit

setup_code = """
name = "Pylenin"
result_list = []
"""

main_code = """
for char in name:
    result_list.append(char)
"""

print(timeit.timeit(stmt=main_code,
                    setup=setup_code,
                    number=10000))

#Result
>>> 0.00629170099273324
```

The output of the above program is the execution time(in seconds) for 10000 executions. To get the time per execution, divide the result with the number of executions.

Coming back to **comparing the execution time of a for loop with list comprehension**, we can write something like this.

```python3
import timeit

setup_code_1 ="""
name = "Pylenin"
result_list = []
"""

main_code_1 ="""
for char in name:
    result_list.append(char)
"""

t1 = timeit.timeit(stmt=main_code_1,
                    setup=setup_code_1,
                    number=10000)

setup_code_2 ="""
name = "Pylenin"
"""

main_code_2 ="""
result_list = [char for char in name] 
"""

t2 = timeit.timeit(stmt=main_code_2,
                    setup=setup_code_2,
                    number=10000)

print(f"10000 runs of For Loop is {t1}")
>>> 10000 runs of For Loop is 0.005563209997490048

print(f"10000 runs of List Comprehension is {t2}")
>>> 10000 runs of List Comprehension is 0.0036344139953143895
```

It is obvious from the result that a list comprehension is much more efficient than using a simple for loop.

**This is how you benchmark different methods to solve a problem.**

You could also **repeat** your calls to the `timeit` function.

Let's say you are unsure of the results provided by timeit. You can pass in an additional parameter called `repeat` to the `timeit.repeat` function.

```python3
import timeit

setup_code = """
name = "Pylenin"
result_list = []
"""

main_code = """
for char in name:
    result_list.append(char)
"""

print(timeit.repeat(stmt=main_code,
                    setup=setup_code,
                    number=10000,
                    repeat=3))

#Result
>>> [0.005725524999434128, 0.00546123698586598, 0.005446395982289687]
```

This returns you all the execution times of calling the `timeit` function. **But which of the 3 results is correct?**

The [Python 3 documentation](https://docs.python.org/3.7/library/timeit.html#timeit.Timer.repeat) suggests that the `min()` of the result list is what you should take into account. The higher values could be noise interfering with your timing accuracy.

#### Using timeit with Python functions(with arguments)

We can also use the `timeit` module with functions.

Let us perform the above benchmarking experiment in a different way. We will **write functions** for each of the approach.

```python3
import timeit

def for_loop(seq, result_list=[]):
    for char in seq:
        result_list.append(char)
    return result_list

def list_comprehension(seq):
    return [char for char in seq]

print(timeit.timeit(stmt = "for_loop(seq)",
                    setup="seq='Pylenin'",
                    number=10000))

print(timeit.timeit(stmt = "list_comprehension(seq)",
                    setup="seq='Pylenin'",
                    number=10000))
```

When you run the above code, it will throw you a **NameError**.
```bash
Traceback (most recent call last):
.....
NameError: name 'for_loop' is not defined
```

**Now, Why is that?**

This is because with `timeit` module, your code runs in a different namespace. So it doesn't recognize the functions you have defined in your global namespace. In order for `timeit` to recognize your functions, you need to import it to the same namespace. You can achieve this by passing `from __main__ import func_name` to the setup argument.

```python3
import timeit

def for_loop(seq, result_list=[]):
    for char in seq:
        result_list.append(char)
    return result_list

def list_comprehension(seq):
    return [char for char in seq]

setup_code_1="""
from __main__ import for_loop
seq = 'Pylenin'
"""

setup_code_2="""
from __main__ import list_comprehension
seq = 'Pylenin'
"""

print(timeit.timeit(stmt = "for_loop(seq)",
                    setup=setup_code_1,
                    number=10000))
>>> 0.006762586999684572

print(timeit.timeit(stmt = "list_comprehension(seq)",
                    setup=setup_code_2,
                    number=10000))
>>> 0.004485986020881683
```

Now your code is going to work properly and return the execution time(in seconds) for 10000 runs of each function.

The above way however, might seem exhaustive. If you don't want that, you could use the `globals()` built-in function inside the `globals` parameter in the `timeit` class.

```python3
import timeit

def for_loop(seq, result_list=[]):
    for char in seq:
        result_list.append(char)
    return result_list

def list_comprehension(seq):
    return [char for char in seq]


print(timeit.timeit(stmt = "for_loop(seq)",
                    setup="seq='Pylenin'",
                    number=10000,
                    globals=globals()))
>>> 0.006524929020088166

print(timeit.timeit(stmt = "list_comprehension(seq)",
                    setup="seq='Pylenin'",
                    number=10000,
                    globals=globals()))
>>> 0.004345747991465032
```
This way, you don't have to write that giant import statement every time.

#### Using timeit on commandline

Now the above examples were suitable for measuring execution times of multiple lines of code with `timeit`. If you want to test out very small, single-line snippets of code, you could also do it from the commandline.

```bash
python3 -m timeit '"-".join(char for char in "Pylenin")'
>>> 1000000 loops, best of 3: 0.851 usec per loop
```

Now the above example is based on the assumption that your system has both Python 2 and Python 3. If you only have one version of Python, you can use `python` in your commandline.

You can also add multiple command line arguments to the above.

1. **-r, --repeat**

    How many times to repeat?
    
2. **-n, --number**

    How many times to execute the statement?
     
3. **-s, --setup** 
    
    The setup code for executing the main statement.
    
4. **-u, --unit**

    Time unit for the timer output. It could be nsec, usec, msec, or sec.
    
Below is an example using the above arguments.

```bash
python3 -m timeit -n 1000 -r 3 -u sec -s "x = 'Pylenin'" '"-".join(char for char in "Pylenin")'
>>> 1000 loops, best of 3: 8.54e-07 sec per loop
```

So the above was an detailed overview on the `timeit` module in Python. If you have some better examples to share, use the comments section.

