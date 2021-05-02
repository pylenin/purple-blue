---
title: "Closures in Python"
description: "Learn about Python closure, how to define a closure, and the reasons you should use it."
date: 2021-02-26T12:55:21+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python functions']
categories_weight: 5
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Pre-requisite knowledge**

1.[Python Functions](https://www.pylenin.com/blogs/python-functions/)
2. [Variable Scope and Namespace](https://www.pylenin.com/blogs/variable-scope-namespace-python/)

**Also remember, everything in Python is an object.**

## Youtube Video

<br>
{{< youtube id="CHo-orWR8PI" >}}
<br>

## LEGB Rule in Python

![LEGB Rule in Python](/img/closures/local.png)

When you reference a variable, Python will for it in the following order:-

1. **First** in the local scope 
2. **Second** in any enclosing functions’ local scopes
3. **Thirdly** in the global scope, and finally
4. **Finally** in the built-in scope. 
   
**The first occurrence of the variable wins.**



## Defining a Closure Function

Let's look at an example.

**Code**

```python3
def numbers():
    x = 100
    
    def print_it():
        print(x)
    
    print_it()

numbers()
```

**Solution**

```bash
100
```



In the example above, what would you expect if the last line of 
the function `numbers()` returned the `print_it()` function 
instead of calling it? This means the function would be defined 
as follows.

**Code**

```python3
def numbers():
    x = 100

    def print_it():
        print(x)

    return print_it

result = numbers()
result()
```

**Output**

```bash
100
```

**What actually happened there?**



## Explanation of Python Closures

The `numbers()` function was called inside which a variable `x` 
has been defined. 
The returned function is assigned to the variable `result`. 
On calling `result()`, the value of variable `x` was 
still remembered although we had already finished executing 
the `print_it()` function.

This way of being able to remember the variable in an 
enclosing scope of the `print_it()` function even though 
it is still not active, is called **Closure** in Python.



## Criteria for using Python Closures

1. There must be a nested function.
2. The nested function must refer to a variable defined in the enclosing function.
3. The enclosing function must return the nested function.

## Advantages of using CLosures

1. Avoid use of global variables.
2. Allows data hiding.
3. Also provides an object oriented solution.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).

