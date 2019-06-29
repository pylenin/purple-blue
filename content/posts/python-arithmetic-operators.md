---
title: "Python Arithmetic Operators"
description: "An article about various use cases of arithmetic operators with integers, floats and complex numbers in Python"
date: 2019-06-26T22:21:42+02:00
draft: false
image: /img/arithmetic-operators/arithmetic-operators.png
---

<div class="sharethis-inline-follow-buttons"></div>

*By [Mostapha Amenchar](https://www.pylenin.com/authors/#mostapha-amenchar)*

Python arithmetic expressions are combinations of numbers and at least one arithmetic operation. 

To perform an arithmetic expression, the following must be understood.

1. [Numbers](#numbers)
2. [Arithmetic operators](#arithmetic-operators)
3. [Number type conversion](#number-type-conversion)
4. [Combining two numbers of different types](#combining-two-numbers-of-different-types)
5. [Operators Precedence](#precedence-of-arithmetic-operators)

##### Numbers

Python version 3 supports three types of numbers: integers, floats and complex numbers.

**Integers**

   [According to Wikipedia](https://en.wikipedia.org/wiki/Integer), integers are numbers without a fractional component.
   
   ```python3
   a = 5
   print(type(a))

   >>> <class 'int'>
   ```

**Floats**

   Floats are the set of numbers containing numbers that have a decimal place.
   ```python3
   a = 7.23
   print(type(a))

   >>> <class 'float'>
   ```

**Complex numbers**
    
   Complex numbers are the set of numbers containing a real and imaginary parts.

   We write `C = x +yj`, where `x` is the real part and `y` is the imaginary part. `j` is the square root of -1.

   ```python3
   a = 5 + 2j
   print(type(a))

   >>> <class 'complex'>
   ```

   Python stores the real and imaginary parts of a complex number as floats.
   ```python3
   a = 5 + 2j

   print(a.real)
   >>> 5.0

   print(a.imag)
   >>> 2.0
   ```

##### Arithmetic Operators

Python arithmetic operators are:-

1. Addition (`+`) 
2. Subtraction (`-`) 
3. Multiplication (`*`)  
4. Division (`/`) 
5. Floor division (`//`) 
6. Exponent (`**`) 
7. Modulus (`%`)

The above operators are binary in nature, which means they operate on two numbers (also known as *operands*).

The **addition** operator (`+`) produces the sum of operands.

```python3
a = 15
b = 5

print(a + b)
>>> 20
```

The **subtraction** operator (`-`) subtracts the two operands, producing their difference.

```python3
a = 15
b = 5

print(a - b)
>>> 10
```

The **multiplication** operator (`*`) produces the product of the operands.

```python3
a = 15
b = 5

print(a * b)
>>> 75
```

The **division** operator (`/`) produces the quotient of its operands, the result will be a **float** type.

```python3
a = 15
b = 5

print(a / b)
>>> 3.0
```

The **floor** operator(`//`) is used to make a whole number adjusted to the left hand side in the number line. Basically, it produces the **quotient** of a division operation. The result is of type `int`.

```python3
a = 20
b = 3

print(a // b)
>>> 6

print(type(a // b))
>>> <class 'int'>
```

The **modulus** operator (`%`) returns the remainder left when one operand is divided by a second operand. The result is of type `int`.

```python3
a = 15
b = 4

print(a % b)
>>> 3

print(type(a % b))
>>> <class 'int'>
```

The **exponent** operator (`**`) returns the result of raising first operand to the power of the second operand.

```python3
a = 2
b = 3

print(a ** b)
>>> 8
```

##### Number type conversion

All integers can be converted to floats. Just add a decimal to the end.
```python3
a = 25
a = 25.0

print(type(a))
>>> <class 'float'>
```

Another way to do this is to pass an integer to the **float constructor**.
```python3
a = 25
b = float(a)

print(type(b))
>>> <class 'float'>
```

All intergers/floats can be converted to complex numbers but **not vice versa**. 

To convert an integer or a float to a complex number just add `0j` to the number.
```python3
a = 7.3
b = a + 0j

print(type(b))
>>> <class 'complex'>
```

Another way to do this is to pass an integer or a float to the **complex constructor**.
```python3
a = 12
b = complex(a)

print(type(b))
>>> <class 'complex'>

print(b)
>>> (12+0j)
```

It's not possible to convert complex number to an integer of a float number.

Let's try and convert a complex number to float.
```python3
a = 12 + 3j
print(float(a))

Traceback (most recent call last):
File <input>, line 2, in <module>
    float(a)
TypeError: can't convert complex to float
```

Now let's repeat the above and convert a complex number to integer.
```python3
a = 12 + 3j
print(int(a))

Traceback (most recent call last):
File <input>, line 2, in <module>
    float(a)
TypeError: can't convert complex to int
```

Only floats numbers with 0 as decimal can be converted to integer.
```python3
a = 3.0
b = int(a)

print(b)
>>> 3

print(type(b))
>>> <class 'int'>

# Notice this !!
print(a == b)
>>> True
```

But what happens when you convert an actual fraction to integer? Python just chops off the decimal.
```python3
a = 3.7
b = int(a)

print(b)
>>> 3

print(type(b))
>>> <class 'int'>

print(a == b)
>>> False
```

##### Combining two numbers of different types

To use numbers responsibly you should learn the rules of arithmetic. 

Arithmetic may seem trivial, but complications arise when you combine numbers of different types. To use arithmetic in python you first need to understand the idea of **narrower and wider types**.

As already mentioned above Python 3 supports 3 types of numbers : integers, floats and complex numbers. 

Python 3 also fully supports **mixed arithmetic**. 

The question that arises is: What is the type of the arithmetic expression, when a binary arithmetic operator
has operands of different numeric types. 

**The rule of thumb **is : the number with the `narrower` type is widened to that of the other, where integer is narrower than float and float is narrower than complex.

For example, expressions in which an integer and a float number is involved, the integer will be promoted to float.
In summary, Python will widen any numbers to make sure all values are of the same type.

**Example 1** - Arithmetics with integer and a float
```python3
a = 3
b = 4.5

print(a + b)
>>> 7.5

print(type(a + b))
>>> <class 'float'>
```

**Example 2** - Arithmetics with integer and a integer
```python3
a = 7
b = 3

print(a * b)
>>> 21

print(type(a * b))
>>> <class 'int'>
```

Since both `a` and `b` are integers, no widening is required.

**However**

Dividing an integer with an integer **returns a float**. This is a change introduced in Python 3. To learn more relevant differences between Python 3 and 2, check out our article [here](https://www.pylenin.com/blogs/10-benefits-of-switching-to-python-3/).

```python3
a = 12
b = 3

print(a/b)
>>> 4.0
```

**Example 3** - Arithmetics with integer and complex number.
```python3
a = 14 + 4j
b = 2

print(a/b)
>>> (7+2j)
```

**Integers are narrower than complex numbers**. So `b` is widened to a complex number before division. it becomes `2 + 0j`.

**Example 4** - Arithmetic with multiple types of numbers

When combining different types of numbers, Python will widen numbers to the same type.
```python3
a = 7
b = 3.5
d = 2.0
f = 2 + 3j

print(a + b * d - a / f )
>>> (12.923076923076923+1.6153846153846154j)
```

Are you wondering how Python decides the precedence of operations? Let's move on to the next section.

##### Precedence of arithmetic operators

Python has well-defined rules for specifying the order in which the arithmetic operators in an expression are evaluated when the expression has several operators.

The order of operation can be summarized as follows:

1. Any operations enclosed in parentheses are performed first.

2. Exponents are performed next.

3. Multiplication and Division is performed from left to the right.

4. In the end, any addition and subtraction operations are performed from left to the right. 

Let's see an illustration to understand this better.

![Precedence of Arithmetics](/img/arithmetic-operators/precedence.jpg)

I hope this article draws a clear picture about use of arithmetics in Python. If you have any questions or suggestions - do leave them in the comment box below.

_**Recommended articles**_

1. [A Step-by-Step guide to Python Logging](https://www.pylenin.com/blogs/python-logging-guide/)
2. [Mastering Python datetime module](https://www.pylenin.com/blogs/mastering-python-datetime/)
3. [5 reasons to learn Python in 2019](https://www.pylenin.com/blogs/5-reasons-to-learn-python/)
