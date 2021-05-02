---
title: "*args vs **kwargs in Python"
description: "Learn the different types of arguments you can pass in Python functions like *args and **kwargs and their usage with examples."
date: 2021-02-25T08:18:20+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python functions']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

## Youtube Video

<br>
{{< youtube id="x-dH73VMF_w" >}}
<br>

In [Python functions](https://www.pylenin.com/blogs/python-functions/#https://www.pylenin.com/blogs/python-functions/#variable-length-argument), we had talked about the 
advantages of using **Variable Length arguments** using the `*` symbol.

I Python there are actually 2 ways to pass in variable length arguments.

1. *args (Variable Length arguments)
2. **kwargs (Variable Length **Keyword** arguments)



## Importance of *args and **kwargs in Python

Sometimes, you are unsure of how many parameters you need to 
define in your function. Let's look at an example.

**Code**

```python3
def addition(x, y):
    print("Value of x is:", x)
    print("Value of y is:", y)
    total = x+y
    return total

result1 = addition(5, 10)
print(result1)
```

**Output**

```bash
Value of x is: 5
Value of y is: 10
15
```

The `addition` function defined above can only add two numbers. 
**What if you want to add more than 2 numbers?** Would you be 
adding/removing parameters as your requirements keep changing? 
**No!**

For this purpose, you can use variable length arguments. 
The parameter for using variable length arguments is 
defined by using a `*`(for *args) or `**`(for **kwargs) 
in front of the parameter name.



## *args in Python

By using `*args` in your function definition, you can match and collect 
remaining positional arguments in the form of a **tuple**.
Let's revisit the addition function above by using `*args`.

**Code**

```python3
def addition(*x):
    print(x)
    sum = 0
    for num in x:
        sum += num
    print(sum)

result = addition(1, 2, 3, 4, 5)
```

**Output**

```bash
(1, 2, 3, 4, 5)
15
```



## **kwargs in Python

`**kwargs` in Python function definitions can be used to pass 
**keyworded** variable-length arguments. Keyword arguments need a double star `**` in front of them. 

The arguments you pass as `**kwargs` will be interpreted by Python as a **dictionary**.

**Code**

```python3
def employee_details(**kwargs):
    for key, value in kwargs.items():
        print("%s = %s" % (key, value))

employee_details(name='Pylenin',
                 job='Developer',
                 salary='NA')
```

**Output**

```bash
name = Pylenin
job = Developer
salary = NA
```




## How to position *args and **kwargs in a function

The general syntax of a function is

```bash
def func(x, *args, **kwargs)
```

This should be the order in which you should pass arguments in 
your Python functions. Let's look at an example.

**Code**

```python3
def pretty_printing(x, *args, **kwargs):
    print(x)
    print(args)
    print(kwargs)

pretty_printing("Lenin", "Mishra", "Pylenin", job="Dreamer")
```

**Output**

```bash
Lenin
('Mishra', 'Pylenin')
{'job': 'Dreamer'}
```

The function definition starts with a fixed length parameter, so, 
Python takes in the argument `Lenin` for parameter `x`.

Since, no more fixed length parameters are defined, 
Python takes in the next 2 arguments as part of `*args` variable length argument. 

Finally, it encounters a keyword based argument and Python takes it in as 
`**kwargs` variable length argument.




**Let's say, we remove `**kwargs` from our function definition.**

**Code**

```python3
def pretty_printing(x, *args):
    print(x)
    print(args)
    print(kwargs)

pretty_printing("Lenin", "Mishra", "Pylenin", job="Dreamer")
```

**Output**

```bash
TypeError: pretty_printing() got an 
unexpected keyword argument 'job'
```

As you can see, Python now throws a `TypeError`. **Why?**

To pass in keyword arguments, you need to satisfy either of the two requirements.

1. Have a parameter defined in your function which is same as the keyword.

    ```python3
    def pretty_printing(x, *args, job):
        print(x)
        print(args)
        print(job)

    pretty_printing("Lenin", "Mishra", "Pylenin", job="Dreamer")
    ```
   
2. Use `**kwargs` in function definition

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).


