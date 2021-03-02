---
title: "Recursive Functions in Python"
description: "Learn to create a recursive function in Python that calls itself"
date: 2021-03-02T08:17:45+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python functions']
categories_weight: 6
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

## Youtube Video

<br>
{{< youtube id="06q7Gr4gPpA" >}}
<br>

## What is recursion?

Recursion is the process of repeating items or operations in a self-similar way. 
In Python, if your program allows you to call a function inside the same function, 
then it is called a **Recursive Function**.

Recursion is an advanced and to some extent **an unused topic**. 
However, it is useful to know about this technique, 
as it allows you to deal with arbitrary structures 
and unpredictable shapes.

![Recursive Function in Python](/img/recursion-recursive-call-python.png)

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

## Example of Recursive Functions

Let's calculate the **factorial of a number in Python**.

Ideally, you would do this by using a [for loop](https://www.pylenin.com/blogs/python-for-loop/).

**Code**

```python3
num = 5
factorial = 1

for i in range(1, num+1):
    factorial *= i

print(factorial)
```

**Output**

```bash
120
```

**Pretty straight forward, right?**

You can also do it using **Recursion**.

**Code - Using Recursion**

```python3
def factorial(x):

    if x == 1:
        return 1
    else:
        # call the function again
        return (x * factorial(x-1))

num = 5
print(factorial(num))
```

**Output**

```bash
120
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

When you call this function with a positive integer, 
it will keep calling itself recursively by decreasing the number.

Each function call multiplies the number with the factorial of the 
number until it is **equal to one**. 

```bash
factorial(5)          # First function call
5 * factorial(4)      # 2nd function call with 4
5 * 4 * factorial(3)  # 3rd function call with 3
5 * 4 * 3 * factorial(2)  # 4th function call with 2
5 * 4 * 3 * 2 * factorial(1) # 5th function call with 1
5 * 4 * 3 * 2 * 1 
120
```

Basically, when the `factorial()` function returned 1, the recursion stopped. 
This is called **Base Condition**. Every recursive function should have a base condition, 
otherwise the recursion continues **infinitely**.

The Python interpreter limits the depths of recursion to help 
avoid infinite recursions. By default, the maximum depth of 
recursion is **1000**. If the limit is crossed, 
it results in `RecursionError`. 

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

## Advantages of Recursion

1. Recursive functions look clean and elegant.
2. It can break down complex problems into multiple small problems using recursion.

## Disadvantages of Recursion

1. Can be difficult to understand.
2. Recursion is expensive.
3. They are also hard to debug.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).

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