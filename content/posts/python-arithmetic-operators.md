---
title: "Python Arithmetic Operators"
description: "A simple article about various use cases of arithmetic operators in Python"
date: 2019-06-26T22:21:42+02:00
draft: true
image: /img/arithmetic-operators/arithmetic-operators.png
---

<div class="sharethis-inline-follow-buttons"></div>

*By [Mostapha Amenchar](https://www.pylenin.com/authors/#mostapha-amenchar)*

Python arithmetic expressions are combinations of numbers and at least one arithmetic operation. 

To perform an arithmetic expression, the following must be understood.

1. Numbers.
2. Arithmetic operators.
3. Number type conversion.
4. Combining of two numbers of different types.
5. Precedence of arithmetic operators.

##### Numbers

Python version 3 supports three types of numbers: integers, floats and complex numbers.


1. Integers 

   Integers are the set of numbers containing whole numbers and their opposites.
   ```python3
   a = 5
   print(type(a))

   >>> <class 'int'>
   ```

2. Floats

   Floats are the set of numbers containing numbers that has a decimal place.
   ```python3
   a = 7.23
   print(type(a))

   >>> <class 'float'>
   ```

3. Complex numbers
    
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
**Remember**

To use numbers responsibly you should learn the rules of arithmetic.

Arithmetics may seem trivial, but complications arise when you combine numbers of different types. 

To use arithmetic in python, you first need to understand the idea of **narrower** and **wider** types.

When a binary arithmetic operator has operands of different numeric types, **the operand with the narrower type is widened to that of the other**. 

Integers are narrower than floats.

Floats are narrower than complex numbers.

This has an effect on both type conversion and combining numbers.

Let's see them in action.

##### Number type conversion

All integers can be converted to floats. Just add a decimal to the end.
```python3
a = 25
a = 25.0

print(type(a))
>>> <class 'float'>

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

But what happens when you convert an actual fraction to int? Python just chops off the decimal.
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
