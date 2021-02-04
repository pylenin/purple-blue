---
title: "Python Assignment Operators"
description: "Learn to use assignment operators to carry out arithmetic, logical and bitwise operations in Python."
date: 2021-02-03T09:47:26+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Getting Started with Python']
categories_weight: 8
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Assigning means allocating values to variables. 
Assignment operators can perform various operations like arithmetic, logical and bitwise operation and then assign the computed value to a variable.

Before understanding assignment operators, let's talk about **Operands**.

**Operands are quantities or values on which an operation is being performed.**

Let's say you are **adding 3 and 2**. Here, addition is the **operation** and, 3 and 2 are the **operands**.

In this article, we will discuss various assignment operators and also a special operator introduced in Python 3.8 - [**Walrus operator**](https://www.pylenin.com/blogs/python-assignment-operators/#walrus-operator).

| Operator | Description | Syntax |
|:----------|:-------------|:--------|
| += | Add and assign | x += y |
| -= | Subtract and assign | x -= y |
| *= | Multiply and assign | x *= y |
| /= | Divide and assign | x /= y |
| %= | Take Modulus and assign | x %= y |
| //= | Floor Divide and assign | x //= y |
| **= | Take exponent and assign | x **= y |
| &= | Perform bitwise "AND" operation and assign | x &= y |
| \|= | Perform bitwise "OR" operation and assign | x \|= y |
| ^= | Perform bitwise "xOR" operation and assign | x ^= y |
| >>= | Perform bitwise "Right Shift" operation and assign | x >>= y |
| <<= | Perform bitwise "Left Shift" operation and assign | x <<= y |

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

### += operator - Add nd assign

The `+=` operator is used to add 2 operands and 
assign the new value to the left operand.

**Code**

```python3
x = 3
y = 2

x += y
print(x)
```

**Output**

```bash
5
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

### -= operator - Subtract and assign

The `-=` operator is used to subtract 2 operands and 
assign the new value to the left operand.

**Code**

```python3
x = 3
y = 2

x -= y
print(x)
```

**Output**

```bash
1
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

### *= operator - Multiply and assign

The `*=` operator is used to multiply 2 operands and 
assign the new value to the left operand.

**Code**

```python3
x = 3
y = 2

x *= y
print(x)
```

**Output**

```bash
6
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

### /= operator - Floor Divide and assign

The `/=` operator is used to subtract 2 operands and 
assign the new value to the left operand.

**Code**

```python3
x = 3
y = 2

x /= y
print(x)
```

**Output**

```bash
1.5
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

### %= operator - Modulus and assign

The `%=` operator is used to perform modulus operation on 2 operands and 
assign the new value to the left operand.

**Modulus operation returns the remainder from dividing 2 operands.**

**Code**

```python3
x = 3
y = 2

x %= y
print(x)
```

**Output**

```bash
1
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

### //= operator - Divide and assign

The `//=` operator is used to perform floor division on 2 operands and 
assign the new value to the left operand.

**Floor division returns the quotient from dividing 2 operands.**

**Code**

```python3
x = 3
y = 2

x //= y
print(x)
```

**Output**

```bash
1
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

### **= operator - Exponent and assign

The `**=` operator is used to perform exponential operation on 2 operands and 
assign the new value to the left operand.

**Code**

```python3
x = 3
y = 2

x **= y
print(x)
```

**Output**

```bash
9
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

### What are Bitwise operators?

Before moving onto Bitwise Assignment operators, let's understand Bitwise operations.

In Python, bitwise operations are performed 
on integers. 
The integers are first converted into binary format 
and then operations are performed on every bit. 
The result is returned in **decimal format**.

Let's learn how to convert an integer to binary format. The binary representation of **10** is **1010**.

![Convert an Integer to Binary](/img/bitwise/integer-to-binary.png)

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

### &= operator - Bitwise AND operation and assign

The `&` operator returns **True** if both the operands are True. **This is the AND operation.**
[From the article on Booleans](https://www.pylenin.com/blogs/booleans-in-python/), it is clear that Python treats `1` as True and `0` as False.

So, the `&=` operator performs the **bitwise AND operation** and 
assigns the new value to the left operand.

**Code**

```python3
x = 3
y = 2

x &= y
print(x)
```

**Output**

```bash
2
```

**Explanation**

```bash
x = 3 --> binary format = 0011
y = 2 --> binary format = 0010

x & y = 0011
         &
        0010
      = 0010
```

The decimal representation of **0010** is **2**.

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

### |= operator - Bitwise OR operation and assign

The `|` operator returns **True** if either of the operands are True. **This is the OR operation.**
[From the article on Booleans](https://www.pylenin.com/blogs/booleans-in-python/), it is clear that Python treats `1` as True and `0` as False.

So, the `|=` operator performs the **bitwise OR operation** and 
assigns the new value to the left operand.

**Code**

```python3
x = 3
y = 2

x |= y
print(x)
```

**Output**

```bash
3
```

**Explanation**

```bash
x = 3 --> binary format = 0011
y = 2 --> binary format = 0010

x & y = 0011
         |
        0010
      = 0011
```

The decimal representation of **0011** is **3**.

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

### ^= operator - Bitwise xOR operation and assign

The `^` operator returns **True** if one of the operand is True and other is False, else it returns False. **This is the xOR operation.**
[From the article on Booleans](https://www.pylenin.com/blogs/booleans-in-python/), it is clear that Python treats `1` as True and `0` as False.

So, the `^=` operator performs the **bitwise xOR operation** and 
assigns the new value to the left operand.

**Code**

```python3
x = 3
y = 2

x ^= y
print(x)
```

**Output**

```bash
1
```

**Explanation**

```bash
x = 3 --> binary format = 0011
y = 2 --> binary format = 0010

x & y = 0011
         ^
        0010
      = 0001
```

The decimal representation of **0001** is **1**.

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

### >>= operator - Bitwise Right Shift operation and assign

When shifting right, the most-significant bit is lost, and a `0` bit is inserted on the left side.

The right shift operator is written as `>>`.

```bash
0011 >> 1 --> 0001 (Moved right by one place)
0011 >> 2 --> 0000 (Moved right by two places)
```

**Code**

```python3
x = 3
y = 2

x >>= y
print(x)
```

**Output**

```bash
0
```

**Explanation**

```bash
x = 3 --> binary format = 0011
y = 2 

x >> y = 0011 >> 2 (Move right by two places)
       = 0000
```

The decimal representation of **0000** is **0**.

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

### <<= operator - Bitwise Left Shift operation and assign

When shifting left, the most-significant bit is lost, and a `0` bit is inserted on the right side.

The left shift operator is written as `<<`.

```bash
0011 << 1 --> 0110 (Moved left by one place)
0011 << 2 --> 1100 (Moved left by two places)
```

**Code**

```python3
x = 3
y = 2

x <<= y
print(x)
```

**Output**

```bash
12
```

**Explanation**

```bash
x = 3 --> binary format = 0011
y = 2 

x << y = 0011 << 2 (Move left by two places)
       = 1100
```

The decimal representation of **1100** is **12**.

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

### Walrus Operator

The Walrus operator **(:=)** is a cool little feature that was introduced in Python 3.8.

It allows you to assign a value to a variable while also returning the value, **without having to declare it before**.

#### Example 1

**Code - Without Walrus Operator**

```python3
x = 3
print(x)
```

You can convert the above code into a **one-liner** by using the Walrus Operator.

**Code - Using Walrus Operator**

```python3
print(x:=3)
```

**Output**

```bash
3
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

#### Example 2

**Code - Without Walrus Operator**

```python3
list_of_names = []
name = input("Name a friend: ")
while name != "stop":
    list_of_names.append(name)
    name = input("Name a friend: ")
```

The above code asks the user for an input, and continues within the `while` loop until we ask to `stop`. It uses the Python built-in [input() function](https://www.pylenin.com/blogs/how-input-works-python/). If you don't know how to use it, check it out!

**Using the Walrus operator**, we can rewrite above code the following way.

**Code - Using Walrus Operator**

```python3
list_of_names = []
while (name := input("Name a friend: ")) != "stop":
    list_of_names.append(name)
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