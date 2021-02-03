---
title: "Understanding width and precision in Python string formatting"
description: "Learn the intricacies of width and precision in Python string formatting"
date: 2021-02-03T09:47:26+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Getting Started with Python']
categories_weight: 7
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

If you have learnt C, C++ or Bash, you would be familiar with the `printf` function. **It is used for printing formatted data to stdout.**

**Question** - Does Python have something similar to `printf`?

**Not really**. Python only provides the `print` function.

**However, you can mimic the behaviour of `printf` by using string formatting.**

This is where terms like **width** and **precision** come into play.

In this article, you will learn the intricacies of using width and precision with string formatting by comparing 3 different ways of string formatting.

1. [% operator](https://www.pylenin.com/blogs/string-formatting-percentage-operator/)
2. [format method](https://www.pylenin.com/blogs/format-method-python-string/)
3. [f-strings](https://www.pylenin.com/blogs/f-strings-python/)

## Example 1

Let's print the **floating point representation** of `4 divided by 3`.

**Code**

```python3
# Using % operator
print("%f"%(4/3))

# Using format method
print("{:f}".format(4/3))

# Using f-strings
print(f"{4/3:f}")
```

**Output**

```bash
1.333333
1.333333
1.333333
```

Each of the above formatting methods, produce the same output. The output of `4 divided by 3` has 6 digits after the decimal.

**Let's try to limit the number of decimal places to 3.**

**Code**

```python3
# Using % operator
print("%0.3f"%(4/3))

# Using format method
print("{:0.3f}".format(4/3))

# Using f-strings
print(f"{4/3:0.3f}")
```

**Output**

```bash
1.333
1.333
1.333
```

By using `0.3f` as format placeholders, we are able to contain the number of decimal places to 3.

**Understanding the structure of `0.3f`**

Let's generalize `0.3f` into a formula - `x.yf`

1. `x` represents the **minimum width** or **padding** of the output string.
2. `y` represents the **maximum number of characters** after the decimal.
3. `f` symbolizes **floating point representation**.

Let's alter the `x` and `y` values and see how the output changes.

**Code**

```python3
# Using % operator
print("%10.2f"%(4/3))

# Using format method
print("{:10.2f}".format(4/3))

# Using f-strings
print(f"{4/3:10.2f}")
```

**Output**

```bash
      1.33
      1.33
      1.33
```

You can see that your result contains **empty white spaces** to the left of each output.

**So what happened?** Let's dive in.

## Understanding width and precision in Python

### Stage 1 - Using only `%f` representation

If you just use `%f` representation, the output will have a **width/length of 8**.

**Code**

```python3
# Using % operator
print("%f"%(4/3))

# Using format method
print("{:f}".format(4/3))

# Using f-strings
print(f"{4/3:f}")
```

**Output**

```bash
1.333333
1.333333
1.333333
```

![Results from using %f](/img/width-precision/wp-1.png)

### Stage 2 - Adding width

Let's add only a `width` placeholder to `%f`.

**Code**

```python3
# Using % operator
print("%10f"%(4/3))

# Using format method
print("{:10f}".format(4/3))

# Using f-strings
print(f"{4/3:10f}")
```

**When the user-defined width is different(greater or smaller) than original width, the length of the output is changed to the user defined width.** In the above example, the new length of output will be 10 characters long.

**Output**

```bash
  1.333333
  1.333333
  1.333333
```

The resulting output is now right-aligned with extra 2 white space characters added as padding to the left.

![Results from adding width to %f formatting](/img/width-precision/wp-2.png)

**However, if the user-defined width is 0, 
the original length of the output is maintained.**

Try providing the `width` as **0**. 
`0f` will provide the same result as using `f` floating point representation.

**Code**

```python3
# Using % operator
print("%0f"%(4/3))

# Using format method
print("{:0f}".format(4/3))

# Using f-strings
print(f"{4/3:0f}")
```

**Output**

```bash
1.333333
1.333333
1.333333
```

### Stage 3 - Adding precision

Let's now change the number of decimal places in the output to 2. This can be done by providing the `precision` value.

**Code**

```python3
# Using % operator
print("%10.2f"%(4/3))

# Using format method
print("{:10.2f}".format(4/3))

# Using f-strings
print(f"{4/3:10.2f}")
```

Upon fixing the `precision` to 2, the resulting output will only have 2 characters after the decimal. All the other characters after the 2nd decimal places are chopped off.

Hence, the output string moves even further to the right, creating more empty white spaces.

**Output**

```bash
      1.33
      1.33
      1.33
```

![Results from adding precision to %f formatting](/img/width-precision/wp-6.png)

## Using width and precision with integers

### Formatting integers with width

Formatting integers with width has similar effect as formatting floating points.

**Code**

```python3
# Using % operator
print("%10d"%(1992))

# Using format method
print("{:10d}".format(1992))

# Using f-strings
print(f"{1992:10d}")
```

**Output**

```bash
      1992
      1992
      1992
```

![Results from adding width to integer formatting](/img/width-precision/wp-3.png)

### Formatting integers with precision

**However, providing precision with `%` formatting has no effect 
and with `f-strings` and `format` method, it throws an error.**

**Code/Output - precision with % operator**

```python3
# Using % operator
print("%10.2d"%(1992))
>>>       1992
```

**Code/Output - precision with format and f-strings**

```python3
# Using format method
print("{:10.2d}".format(1992))

>>>Traceback (most recent call last):
     File "some_file_location", line 5, in <module>
       print("{:10.2d}".format(1992))
   ValueError: Precision not allowed in integer format specifier

# Using f-strings
print(f"{1992:10.2d}")

>>>Traceback (most recent call last):
     File "some_file_location", line 8, in <module>
       print(f"{1992:10.2d}")
   ValueError: Precision not allowed in integer format specifier
```

## Using width and precision with strings

### Formatting string with width

Unfortunately the default alignment differs between `%` formatting (old style) 
and formatting with `format` method and `f-strings` (new style). 

**The old style defaults to right aligned while for new style it's left.**

**Code**

```python3
# Using % operator
print("%10s"%("Pylenin"))

# Using format method
print("{:10s}".format("Pylenin"))

# Using f-strings
print(f"{'Pylenin':10s}")
```

**Output**

```bash
   Pylenin
Pylenin   
Pylenin   
```

![Results from adding width to string formatting](/img/width-precision/wp-4.png)

You can change this behaviour easily by using certain operators.

**To right align your string, use `>` operator with the new formatting methods.**

**Code - To right align strings**

```python3
# Using % operator
print("%10s"%("Pylenin"))

# Using format method
print("{:>10s}".format("Pylenin"))

# Using f-strings
print(f"{'Pylenin':>10s}")
```

**Output**

```bash
   Pylenin
   Pylenin
   Pylenin
```

**To left align your string, use `-` operator with the old formatting method.**

**Code - To left align strings**

```python3
# Using % operator
print("%-10s"%("Pylenin"))

# Using format method
print("{:10s}".format("Pylenin"))

# Using f-strings
print(f"{'Pylenin':10s}")
```

**Output**

```bash
Pylenin   
Pylenin   
Pylenin   
```

### Formatting string with precision

When you add `precision` to string formatting, the characters of the string are truncated.

Let's say, you provide a precision of `n`. All the characters except the first `n` characters are truncated.

**Code**

```python3
# Using % operator
print("%10.2s"%("Pylenin"))

# Using format method
print("{:10.2s}".format("Pylenin"))

# Using f-strings
print(f"{'Pylenin':10.2s}")
```

**Output**

```bash
        Py
Py        
Py           
```

![Results from adding precision to string formatting](/img/width-precision/wp-5.png)


