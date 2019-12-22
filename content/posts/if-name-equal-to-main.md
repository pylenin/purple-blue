+++ 
draft = false
date = 2019-12-22T16:18:24+01:00
title = """What is if __name__ == "__main__" ?"""
description = "Understand how __name__ and __main__ work in Python 3"
slug = "" 
tags = []
categories = []
externalLink = ""
series = []
image = /img/name-main/name-main.png
+++

<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

##### So what is __ name __?

Before we get rolling, I want you to create 2 python files. For the sake of this article, I will create `test.py` and `test2.py`.

When the Python interpeter executes a file, it defines a few special variables. 
One of them is the  `__name__` variable.

```python3
# test.py

print("This is the test file")
print(__name__)

>>> This is the test file
    __main__
```
See how when we print `__name__`, it prints out `__main__`. What happens is, Python assigns the hard-coded string `"__main__"` to the `__name__` variable.

So when you use `if __name__ == "__main__"` in your python script, you are asking Python to run the script as a main file.

Check out the 2 scripts below.

**Script 1**

```python3
# test.py

def hello():
    return "I am saying Hello"

print(hello())
```
and then,

**Script 2**

```python3
# test.py

def hello():
    return "I am saying Hello"

if __name__ == "__main__":
    print(hello())
```

There is no difference between Script 1 and Script 2. Both of them will output the below result.

```bash
>>> I am saying Hello
```

##### So why use if __ name __ == "__ main __"?

You will understand the difference when you start importing your `test.py` as a library.

Let's make some changes to our `test.py`.

```python3
# test.py

def hello():
    return "This is from test.py"

if __name__ == "__main__":
    print("Executing test.py")
    
print(hello())
```

When we run the above script, we get the following results.

```bash
>>> Executing test.py
    This is from test.py
```

Let's now make use of `test2.py`. We will import `test.py` into our `test2.py`.

```python3
# test2.py

import test

def hello2():
    return "This is test2"

if __name__ == '__main__':
    print(hello2())
```

Now if you run `test2.py`, you should get the following result.

```bash
>>> This is from test.py
    This is test2
```

When you import a python file, the code in the python file is executed first. Notice how, `Executing test.py` line didn't get printed out. This is because it is within the `if __ name __ == "__ main __"` block.

Let's now change the `test.py` to print the `__name__` variable.

```python3
# test.py

def hello():
    return "This is from test.py"

if __name__ == "__main__":
    print("Executing test.py")

print(hello())
print(__name__) # New print statement
```

When we execute `test.py` now, we will get the following results.

```bash
>>> Executing test.py
    This is from test.py
    __main__
```

Now if we execute `test2.py`, we should get the following result.

```bash
This is from test.py
test # Result of printing __name__
This is test2
```

So now instead of printing `__main__`, the `print(__name__)` statement prints out the name of the file.

This is the benefit of using `if __ name __ == "__ main __"`. You can easily identify which variables are being imported from which libraries.

