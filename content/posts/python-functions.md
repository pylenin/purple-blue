---
title: "Functions in Python"
description: "Learn to define functions in Python and their use with examples."
date: 2021-02-20T11:56:11+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python functions']
categories_weight: 1
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

## What are Python functions?

Functions in Python are a group of statements that are meant 
to be run multiple times in a program. Functions allow you to pass 
parameters into them and based on that return you a result.

A function in Python is enclosed within a `def` block. The statements that 
go inside a function body are **indented by 4 spaces or 1 tab**.

**Function Syntax**

```bash
def function_name(params):
    """
    Docstring
    """
    <body>
    return <something>
```

1. `def` marks the start of a function.
2. It is followed by a `function_name` to uniquely identify the function. The rules for writing function names are same as [writing identifiers](https://www.pylenin.com/blogs/keywords-identifiers/#rules-to-remember-while-writing-identifiers).
3. Within paranthesis, `params` or parameters are used to pass values to a function. **They are optional.**
4. Colon (:) marks the end of the function header.
5. Documentation string (docstring) to describe what the function does. **It is optional.**
6. One or more valid python statements that make up the function body. Indented by 4 spaces.
7. A return statement to return a value from the function. **It is optional.**

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Example of a function

Below is a simple example of a function that adds 2 numbers.

**Code**

```python3
def addition(x, y):
    total = x+y
    return total
```

In this example, the function is taking in 2 parameters - `x` and `y`. 
It is storing the sum of `x` and `y` in a variable called `total`. 
It is then returning the `total` variable.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Calling a function

Once your function is defined, You can call the function by typing the function name and providing arguments to the parameters(if any). 
The value returned through the `return` statement becomes the result 
of the function call.

**Code**

```python3
def addition(x, y):
    total = x+y
    return total

result = addition(x=10, y=5)
print(result)
```

**Output**

```bash
15
```

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Parameters in Functions

Let's take a closer look at the parameters. Based on the above example, 
you can see that parameters `x` and `y` are receiving their respective arguments while calling 
the function. **Arguments are the values you pass in to the parameters of your function.**

The above example demonstrates the case of **required arguments**. If you try to call the `addition` function  without those parameters, it will throw you a `TypeError`.

**Code**

```python3
def addition(x, y):
    total = x+y
    return total

result = addition()
print(result)
```

**Output**

```bash
TypeError: addition() missing 
2 required positional arguments: 'x' and 'y'
```

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Positional arguments vs Keyword arguments

Read the above error message again.

```bash
TypeError: addition() missing 
2 required positional arguments: 'x' and 'y'
```

You might wonder, **what are positional arguments?**

Positional arguments are arguments that are called by their position in the function. 
**Keyword arguments** on the other hand are called by the name or the **keyword** of the parameter in your function.

Look at the below example.

**Code**

```python3
def addition(x, y):
    print("Value of x is:", x)
    print("Value of y is:", y)
    total = x+y
    return total

# Positional argument
result1 = addition(10, 5)

# Keyword argument
result2 = addition(x=10, y=5)
```

**Output**

```bash
Value of x is: 10
Value of y is: 5

Value of x is: 10
Value of y is: 5
```

The function `addition` has been called twice. In the first functional call, arguments are being passed as it is, without mentioning the keyword of the parameters. 
Python will **automatically assume** that argument `10` refers to parameter `x` and argument `5` refers to parameter `y`. 
This is an example of **Positional argument**.

In the second function call, the arguments are passed along 
with the keywords of the specific parameter. 
Here, you are **explicitly telling Python** that argument 
`10` refers to parameter `x` and argument `5` refers to 
parameter `y`. This is an example of **Keyword argument**.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

Let's now switch the position of the parameters

**Code**

```python3
def addition(x, y):
    print("Value of x is:", x)
    print("Value of y is:", y)
    total = x+y
    return total

# Positional argument
result1 = addition(5, 10)

# Keyword argument
result2 = addition(y=5, x=10)
```

**Output**

```bash
Value of x is: 5
Value of y is: 10

Value of x is: 10
Value of y is: 5
```

The output should give you an idea of how positional and keyword arguments work. 

In case of positional arguments, since we switched places of the arguments, 
Python believes `x` is 5 and `y` is 10.

However, with keyword arguments, since we are explicitly mentioning the parameter names, the values of the arguments are maintained.

In a way, this shows why using **keyword arguments** have an advantage over positional arguments.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Default arguments

Sometimes, you would want to fix the argument to a certain parameter,
unless required otherwise. You can assign a default argument to any parameter in the function using the `=` operator.

Let's look at the below example.

**Code**

```python3
def greetings(name, msg="Hello"):
    return msg+' '+name

greet = greetings(name="Pylenin")
print(greet)
```

**Output**

```bash
Hello Pylenin
```

The above example uses a default argument of `Hello` for the `msg` parameter. 
Unless you want to change it, you don't have to pass in the argument for `msg` parameter in your function call. 
If you do pass an argument to this parameter, Python will **override the default argument with the 
new argument passed**.

**Code**

```python3
def greetings(name, msg="Hello"):
    return msg+' '+name

greet = greetings(name="Pylenin", msg="Namaste")
print(greet)
```

**Output**

```bash
Namaste Pylenin
```

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

**Also remember,** default arguments have to be the last thing in the list of parameters in the function.
They should follow **non-default** arguments. Otherwise, they will throw an error.

**Code**

```python3
def greetings(msg="Hello", name):
    return msg+' '+name

greet = greetings(name="Pylenin", msg="Namaste")
print(greet)
```

**Output**

```bash
SyntaxError: non-default argument follows default argument
```

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Variable Length Argument

These are also known as **Arbitrary arguments**.

Sometimes, you are unsure of how many parameters you need to define in your function. For e.g., 
the `addition` function defined above can only add two numbers. **What if you want to add more than 2 numbers?** Would you be 
adding/removing parameters as your requirements keep changing? **No!**

For this purpose, you can use variable length arguments. The parameter for using variable length arguments is defined by using a `*` in front of the parameter name.

**Code**

```python3
def addition(*x):
    print(x)

result = addition(1, 2, 3, 4, 5)
```

**Output**

```bash
(1, 2, 3, 4, 5)
```

You can now pass in any number of positional arguments and Python will treat all of them as a tuple. This way, you **limit the number of parameter definitions within your function**.

**Code**

```python3
def addition(*x):
    sum = 0
    for elem in x:
        sum += elem
    return sum


result = addition(1, 2, 3, 4, 5)
print(result)
```

**Output**

```bash
15
```

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

In case you are using both a non-default argument and a variable length argument in your function definition, 
make sure to pass in the non-default argument as a keyword argument. Else you will get unexpected results.

**Code**

```python3
def greetings(*name, msg):
    for people in name:
        msg+= people+","
    return msg

greet = greetings("Pylenin", "Ashish", "Shishir", msg="Hello ")
print(greet)
```

**Output**

```bash
Hello Pylenin,Ashish,Shishir,
```

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Advantages of functions

1.  **They maximize code reusability**

    Rather than writing duplicate copies of your logic everywhere in your code, 
    you can just store your logic within a function that can be called with ease.
    
2.  **Minimizes code redundancies**

    Using functions in your code keeps your code shorter. It therefore, saves space and execution time and enhances readability.

3.  **Functions are easily maintainable**

    Let's say your function holds an important business logic. If you want to make changes to the logic, 
    you only have to modify that function. You don't have to go through the entire code and exhaust yourself. 
    This shows that functions are very easy to maintain.
    
4.  **Enhances code clarity**

    Functions allow users to split their codes into various pieces that have well defined roles. This enhances clarity of the program.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
    
