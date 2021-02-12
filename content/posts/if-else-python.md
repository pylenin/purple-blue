---
title: "Python if elif else statements (With Examples)"
description: "Learn to evaluate decisions in  Python 3 using if, elif and else statements with examples."
date: 2021-02-12T08:21:32+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python control flows']
categories_weight: 1
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

The `if` statement in Python is similar to if statements in most procedural languages. 
It starts with an `if test`, followed by one or more 
optional `elif` (else if) tests and a final optional `else` block. 
The `if-elif` tests and the `else` part each have a block of 
nested statements, **indented by 4 spaces or a tab**. 

When an `if` statement is executed, Python executes the block of code 
associated with the first test that evaluates to True, or the
`else` block if all tests prove false. 

**Syntax of if, elif and else statements**

```bash
if <test_1>: # if test
    <statement_1> # Associated nested block of if
elif <test_2>: # Optional elifs
    <statement_2> # Associated nested block of elif
else: # Optional else
    <statement_3>
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

### Example 1

Let's write a Python program to **[check if a number is odd or even](https://www.pylenin.com/python-examples/odd-even/)**.

**Code**

```python3
num = 12

if num%2 == 0:
    print("It is even")
else:
    print("It is odd")
```

**Output**

```bash
It is even
```

There is only 1 test being performed here - **Checking of the remainder of a number divided by 2 is 0**. 
If the test returns True, the number is declared even. You don't have to write a second test to check if the number is odd. A number can either be even or odd. If the test returns False, the code in the `else` block gets executed.

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

### Example 2

Let's try out another example. Let's write a Python program to check 
if a number is positive, negative or 0.

For this example, 2 tests need to be performed.

1. Test 1 - Check if the number is positive
2. Test 2 - Check if the number is negative
3. If the number is neither positive nor negative, it is 0

**Code**

```python3
num = 10

if num > 0:
    print("It is positive")
elif num < 0:
    print("It is negative")
else:
    print("The number is 0")
```

**Output**

```bash
It is positive
```

The second test is used within an `elif` block. 
If your python program requires multiple tests, **add as many elif blocks you want**.

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

### Example 3

Let's write a Python program to check the status of a batsman's score.

1. Test 1 - Check if the batsman got out at 0. **It's a duck!**
2. Test 3 - Check if the batsman scored between 50 and 100. **It's a half century!**
3. Test 4 - Check if the batsman scored between 100 and 200. **It's a century!**
4. Test 5 - Check if the batsman score more than 200. **It's a double century!**
5. If none of the tests hold True, just print the score.

**Code**

```python3
score = 52

if score == 0:
    print("Duck")
elif score >= 50 and score < 100:
    print("Half century")
elif score >= 100 and score < 200:
    print("Century")
elif score >= 200:
    print("Double Century")
else:
    print(f"The score of the batsman is {score}")
```

**Output**

```bash
Half century
```

As you can see, we have multiple `elif` statements being used. Each statement covers a test scenario.

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

### Example 4 - Experimenting with Booleans

In an `if, elif, else` decision making in Python, except the first test under the `if` block, 
every other test is **optional**. Once one of the tests is evaluated as `True`, the following tests are ignored.

**Code - 1**

```python3
if True:
    print("if block was executed.")
elif True:
    print("1st elif block was executed")
elif True:
    print("2nd elif block was executed")
else:
    print("Finally, else block was executed.")
```

**Output**

```bash
if block was executed.
```

Let's add variations to the above code.

**Code - 2**

```python3
if False:
    print("if block was executed.")
elif True:
    print("1st elif block was executed")
elif True:
    print("2nd elif block was executed")
else:
    print("Finally, else block was executed.")
```

**Output**

```bash
1st elif block was executed
```

**Code - 3**

```python3
if False:
    print("if block was executed.")
elif False:
    print("1st elif block was executed")
elif True:
    print("2nd elif block was executed")
else:
    print("Finally, else block was executed.")
```

**Output**

```bash
2nd elif block was executed
```

**Code - 4**

```python3
if False:
    print("if block was executed.")
elif False:
    print("1st elif block was executed")
elif False:
    print("2nd elif block was executed")
else:
    print("Finally, else block was executed.")
```

**Output**

```bash
Finally, else block was executed.
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

### Example 4 - Nested If statements

You can also nest `if, elif, else` statements inside of another `if, elif, else` block.

Let's rewrite the Python program to check 
if a number is positive, negative or 0.

**Code**

```python3
num = -1

if num >= 0:
    if num == 0:
        print("The number is 0")
    else:
        print("It is positive")
else:
    print("It is a negative number")
```

**Output**

```bash
It is a negative number
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

### Example 4 - Membership test of data types

Using the `if, elif, else` statements, you can check if a certain element exists in any data type.

**Code**

```python3
user_input = int(input("Enter a number ==> "))

my_list = [1, 2, 3]

if user_input in my_list:
    print(f"{user_input} was found")
else:
    print(f"Couldn't find {user_input}")
```

**Output**

```bash
Enter a number ==> 10
Couldn't find 10
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

You can use the `in` keyword to check for membership in any other data type.

**Code**

```python3
# Membership test for string

if "lenin" in "Pylenin":
    print("It exists")
else:
    print("Doesn't exist")

# Membership tests in tuples

my_tuple = (1, 2, 3, 4)

if 2 in my_tuple:
    print("It exists")
else:
    print("Doesn't exist")

# Membership tests in dictionary

my_dict = {"name":"Pylenin",
           "YOB": 1992}

if 'YOB' in my_dict.keys():
    print("It exists")
else:
    print("Doesn't exist")
```

**Output**

```bash
It exists
It exists
It exists
```

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).