---
title: "Python program to find the HCF or GCD of 2 numbers"
description: "Learn how to find the highest common factor(HCF) or greatest common divisor(GCD) of 2 numbers in Python."
date: 2021-02-18T10:39:41+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

Let's say you want to find the HCF of 8 and 20.

**Step 1**

Take the smallest number. In this case, the smallest number is 8.

**Step 2**

Divide the smallest number by all the numbers from 1 to that 
number itself and check for numbers that properly divide the 
smallest number with remainder 0. Those numbers are called **Factors**.

```bash
8 / 1 --> Divisible
8 / 2 --> Divisible
8 / 3 --> Not Divisible
8 / 4 --> Divisible
8 / 5 --> Not Divisible
8 / 6 --> Not Divisible
8 / 7 --> Not Divisible
8 / 8 --> Divisible
```

1, 2, 4 and 8 are factors of 8.

**Step 3**

Divide the largest number with the factors of the smallest number. 
The largest factor that divides the largest number with remainder 0, **is the HCF**.

```bash
20 / 1 = 20
20 / 2 = 10
20 / 4 = 5 <-- HCF is 4
20 / 8 --> Not Divisible
```

**The HCF of 8 and 20 is 4**.

### Using for loops

**Code**

```python3
num1 = 8
num2 = 20

smallest_num = min(num1, num2)
largest_number = max(num1, num2)
factors = []
hcf = None

for i in range(1, smallest_num+1):
    if smallest_num%i == 0:
        factors.append(i)
        
print(factors) # This should be in ascending order

for factor in factors:
    if largest_number%factor == 0:
        # Keep re-assigning the variable 
        # with bigger factor
        hcf = factor

print(hcf)
```

**Output**

```bash
[1, 2, 4, 8]
4
```

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).
