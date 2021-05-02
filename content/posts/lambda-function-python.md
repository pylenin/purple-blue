---
title: "Lambda Functions in Python"
description: "Learn to write lamba functions in Python. Learn its syntax and how to use them (with examples)"
date: 2021-03-04T05:53:33+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python functions']
categories_weight: 7
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

## Youtube Video

<br>
{{< youtube id="iMOIGsNHQjM" >}}
<br>

## Lambda functions in Python

Ever heard of something called **Anonymous functions?**
An anonymous function in Python is a function that is defined 
without a name. 

While functions in Python are defined using the `def` keyword, 
anonymous functions are defined using the **lambda** keyword. 
Hence, they are also called **lambda functions**.



## Syntax of Lambda functions

```bash
lambda argument: expression

argument - The argument to pass into
           your lambda function 
```

**Code**

```python3
# Normal Function
def return_squared(x):
    return x**2

# Lambda Function
return_squared = lambda x : x**2
```

Notice, the absence of a function name in the Lambda function. 
Also, the `def` keyword is replaced with a `lambda` keyword.

`lambda x: x**2` is the lambda function. 
Here x is the argument and `x**2` is the expression 
that gets evaluated and returned as a **function object**.



It's also easy to call lambda functions.

```python3
# Normal Function
def return_squared(x):
    return x**2

result = return_squared(5)
print(result)

# Lambda Function
return_squared = lambda x : x**2

result = return_squared(5)
print(result)
```

**Output**

```bash
25
25
```



## Multiple arguments with lambda function

You can provide as many arguments you want with lambda function.

**Code**

```python3
addition = lambda x,y:x+y
print(addition(5,3))
```

**Output**

```bash
8
```



## Advantages of Lambda functions

1. Fewer Lines of Code.
2. Can be easily used with `filter`, `map` and `reduce` methods.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).

