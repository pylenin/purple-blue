---
title: "Why is 0.1 + 0.2 not equal to 0.3 in Python?"
description: "Learn how arithmetics with floating point works in Python and how Python stores floating point numbers."
date: 2021-02-03T09:47:26+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Getting Started with Python']
categories_weight: 9
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Try running the below code in your favorite IDE.

**Code**

```python3
print(0.1+0.2)
```

**Output**

```bash
0.30000000000000004
```

Are you confused withe result? **You should be!**

The mystery behind this lies in the way, Python stores floating point data types.

### How humans deal with floats?

Mathematics for human is made in **Base 10**. 
It means, there are 10 different numbers ranging from 0 to 9 
that make up all the numbers.

With Base 10, you can express all the fractions **finitely** that are Prime Factors of 10.

For example, **prime factors of 10 are 2 and 5.**

So fractions like `1/2`, `1/4`, `1/5`, `1/8` and `1/10` can all be expressed with finite digits as the denominator uses the prime factor of 10.

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

**But what about `1/3` or `1/6` or `1/7`?** 
Each of them have repeating decimals as the prime factor of denominator is 3 or 7.

What is 1 divided by 3.

Approximately,
```bash
0.3
```

or even better,
```bash
0.33
```

or even a better approximation would be 
```bash
0.333
```

and it continues!

Therefore, **1/3 cannot be measured in Base 10.**

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

### How do computers deal with floats?

Unlike humans, computers do not use a Base 10 system. 
They use a **Base 2** system, which is also known as **Binary code**. 
**By using only 1 and 0**, a computer builds up a series of bits to 
represent all possible numbers, up to some maximum value allowed by its memory.

In a Base 2 system (binary system), 
you can express all the fractions **finitely** that are Prime Factors of 2.

So `1/2`, `1/4`, `1/8`, `1/16` etc., can be expressed cleanly as decimal.

However, fractions like `1/5`, `1/10` etc. will be expressed as repeating decimals as the **prime factor of denominator are values other than 2**. 

So, the binary value of `0.1 ==> (1/10)` is `0.0001100110011001100110011001100110011001100110011001101....`.

Binary value of `0.2 ==> (1/5)` is `0.001100110011001100110011001100110011001100110011001101....`.

Let's prove the above by learning how to convert floats to binary.

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

#### Convert floating point numbers to binary numbers

In a floating point number, there is an **integral part** and **fractional part**. So, in `0.1`, **0** is the integral part and **1** is the fractional part.

To convert the integral part to binary, follow the instructions provided in [Bitwise operation](https://www.pylenin.com/blogs/python-assignment-operators/#what-are-bitwise-operators). **The binary representation of 0 is `0`.**

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

**Let's learn to convert the fractional part to binary.**

To convert the fractional part of a floating point to binary, 
you have to multiply fractional part with 2 
and take the one bit which appears before the decimal point.

Follow the same procedure, until it becomes 1.0.

**Example 1 - Convert 0.125 to binary**

Integral part - 0.
Binary value of Integral part is 0.

Fractional part - 0.125
Calculate the binary value of fractional part as shown below.

```bash
0.125 X 2 = 0.25 // Keep 0 and move 0.25 to next step
0.25 X 2 = 0.5 // Keep 0 and move 0.5 to next step
0.5 X 2 = 1.0 // Keep 1 and stop the process

The binary value is 001
```

So the combined binary value of integral and fractional part of 0.125 is **0.001**

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

**Example 2 - Convert 0.1 to binary**

Integral part - 0.
**Binary value of Integral part is 0.**

Fractional part - 0.1.
Calculate the binary value of fractional part as shown below.

```bash
0.1 X 2 = 0.2 // Keep 0 and move 0.2 to next step
0.2 X 2 = 0.4 // Keep 0 and move 0.4 to next step
0.4 X 2 = 0.8 // Keep 0 and move 0.8 to next step
0.8 X 2 = 1.6 // Keep 1 and move 0.6 to next step
0.6 X 2 = 1.2 // Keep 1 and move 0.2 to next step
0.2 X 2 = 0.4 // Keep 0 and move 0.4 to next step
0.4 X 2 = 0.8 // Keep 0 and move 0.8 to next step
0.8 X 2 = 1.6 // Keep 1 and move 0.6 to next step
0.6 X 2 = 1.2 // Keep 1 and move 0.2 to next step

and it never stops.
```

So binary value of `0.1` is stored as `0.000110011..`. 
Similarly, the binary value of `0.2` is stored as `0.001100110..`

Now, when you add `0.1 + 0.2` in Python(or in some other programming language), Python converts `0.1` and `0.2` to its binary form.

Then it performs the addition. **The result will never be equal to 0.3 exact.** It will always tend to 0.3.

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

### Is this a problem?

Honestly, there is no reason to panic. 
The level of precision is more than sufficient for **99.99%** of the cases, **until Sauron strikes!**

