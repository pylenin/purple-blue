---
title: "How to define Custom Exception Class in Python?"
description: "Learn to build custom exception classes in Python that provide more flexibility and readability"
date: 2021-01-22T12:13:27+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the 10th topic in the Python 30 series. [Check out the video here.](https://youtu.be/siXcty5yLf0)

Python provides a lot of [built-in exception classes](https://www.pylenin.com/tags/built-in-exception-class/) that outputs an error when something in your code goes wrong. The error classes can also be used to handle those specific exceptions using [try-except blocks](https://www.pylenin.com/blogs/python-try-except-else-finally/).

However, there are times, when you need to provide more context in exceptions to deal with specific requirements.

Let's look at an example.

#### Example 1

**Code**

```python3
x = [1, 2, 3, 4]

try:
    user_input = int(input("Guess a position ==> "))
    print(x[user_input])
except Exception as e:
    if e.__class__.__name__ == 'IndexError':
        print(f"You are only allowed to guess between {-1*len(x)} and {len(x) - 1}")
    elif e.__class__.__name__ == 'ValueError':
        print("You are only allowed to guess integers")
    else:
        print(e)
```

There is nothing wrong with the above code. You are asking for `user_input` and based on it, you are returning an element from the list.

If the user guesses an index that is not present, you are throwing a custom error message with [IndexError](https://www.pylenin.com/blogs/index-error-python/) Exception.

If the user enters anything apart from integers, he/she will be thrown a custom error message with `ValueError` Exception.

However, **over-using print statements** in your code can make it messy and difficult to understand. It reduces the readability of your code.

Also, **it reduces code reusability**. Instead of copy-pasting these custom print statements everywhere, you could create a class that stores them and call them wherever you want.

#### How to build a custom Exception class?

You can define custom exceptions in Python by creating a new class, that is derived from the built-in `Exception` class. 

**Code**

```python3
class UserDefinedException(Exception):
    pass

raise UserDefinedException
```

**Output**

```bash
Traceback (most recent call last):
  File "some_file_location", line 4, in <module>
    raise UserDefinedException
__main__.UserDefinedException
```

**You can also pass in a custom error message.**

**Code**

```python3
class UserDefinedException(Exception):

    def __init__(self):
        pass

    def __str__(self):
        return ("User Defined error occured")

raise UserDefinedException()
```

**Output**

```bash
Traceback (most recent call last):
  File "some_file_location", line 9, in <module>
    raise UserDefinedException()
__main__.UserDefinedException: User Defined error occured
```

#### Example 1 - Improving Readability with custom Exception class

Let's try to add custom exception class to our earlier discussed example.

##### Step 1 - Add a custom Exception class

**Code**

```python3
class MyIndexError(Exception):
    
    def __init__(self, x):
        self.allowed_length = x
    
    def __str__(self):
        return f"You are only allowed to guess between "\
               f"{-1*self.allowed_length} and {self.allowed_length - 1}"

class MyValueError(Exception):

    def __str__(self):
        return f"You are only allowed integers."
```

Everytime, you want to call the `MyIndexError` class, you have to pass in the length of our iterable.

##### Step 2 - Use `MyIndexError` class in your code

**Code**

```python3
try:
    user_input = int(input("Guess a position ==> "))
    print(x[user_input])
except Exception as e:
    if e.__class__.__name__ == 'IndexError':
        msg = MyIndexError(len(x))
        print(msg)
    elif e.__class__.__name__ == 'ValueError':
        msg = MyValueError()
        print(msg)
    else:
        print(e)
```

##### Final Code

**Code**

```python3
class MyIndexError(Exception):

    def __init__(self, x):
        self.allowed_length = x

    def __str__(self):
        return f"You are only allowed to guess between "\
               f"{-1*self.allowed_length} and {self.allowed_length - 1}"

class MyValueError(Exception):

    def __str__(self):
        return f"You are only allowed integers."

x = [1, 2, 3, 4]

try:
    user_input = int(input("Guess a position ==> "))
    print(x[user_input])
except Exception as e:
    if e.__class__.__name__ == 'IndexError':
        msg = MyIndexError(len(x))
        print(msg)
    elif e.__class__.__name__ == 'ValueError':
        msg = MyValueError()
        print(msg)
    else:
        print(e)
```

When you run the above code, you should get an output like this.

**Output**

```bash
Guess a position ==> 10
You are only allowed to guess between -4 and 3

Guess a position ==> 1.5
You are only allowed integers.

Guess a position ==> -1
4
```

With the print statements gone from your block of code, 
the readability has certainly increased. 
Also, since you have made a class for your custom errors, 
they can be reused wherever you want.

#### Example 2 - Project Specific Exception handling

Sometimes you are working on specific projects that require you to provide a better context into your project's functionality.

For example, **You are creating your own list data type in Python that only stores integer**.

In such cases, it is better to define a custom Exception class that provides a better understanding of the errors that users can understand and relate. Using [built-in exception classes](https://www.pylenin.com/tags/built-in-exception-class/) may not be very useful in such scenarios.

Let's build the new list data type.

**Code**

```python3
class MyIntegerOnlyList():

    def __init__(self):
        self.my_list = []

    def add_items(self,x):
        if not isinstance(x, int):
            return
        self.my_list.append(x)

    def get_list(self):
        return self.my_list

x = MyIntegerOnlyList()

x.add_items(23)
print(x.get_list())
x.add_items("Lenin")
print(x.get_list())
```

If you run the above code, you should get an output like the below.

**Output**

```bash
[23]
[23]
```

The `add_items()` method ignores the entry of string `Pylenin` and only returns the list with integers. However, this is not very descriptive of its functionality.

Ideally, when a user tries to add any other data type to your custom list, they should see an error that says something like "Only integers Allowed".

Let's add a custom exception class.

**Code**

```python3
class CustomTypeError(Exception):

    def __init__(self, x):
        self.data_type = x

    def __str__(self):
        return f"{self.data_type} is not allowed. Only integers"

class MyIntegerOnlyList():

    def __init__(self):
        self.my_list = []

    def add_items(self,x):
        if not isinstance(x, int):
            raise CustomTypeError(type(x))
        self.my_list.append(x)

    def get_list(self):
        return self.my_list

x = MyIntegerOnlyList()

x.add_items(23)
print(x.get_list())
x.add_items("Pylenin")
print(x.get_list())
```

The `CustomTypeError` Exception class takes in the data type of the provided input and is raised everytime, someone tries to add anything to the list, other than integers.

When you run the above code, it should produce an output like below.

**Output**

```bash
[23]
Traceback (most recent call last):
  File "some_file_location", line 26, in <module>
    x.add_items("Pylenin")
  File "some_file_location", line 16, in add_items
    raise CustomTypeError(type(x))
__main__.CustomTypeError: <class 'str'> is not allowed. Only integers
```

#### Why do you need a Custom Exception Class?

In conclusion, you would want to use a Custom Exception class for the following reasons.

1. To improve readability of your code.
2. To enhance reusability of features.
3. To provide custom messages/instructions to users for specific use cases.

Check out how to work with [Python Built-in Exception classes in Python](https://www.pylenin.com/tags/built-in-exception-class/).

#### Related Articles

1. [Python Exception Handling with Try Except Else and Finally](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [Catch Multiple Exceptions in Python](https://www.pylenin.com/blogs/catch-multiple-exceptions-python/)
3. [ZeroDivisionError Exception in Python](https://www.pylenin.com/blogs/zero-division-error-python/)
4. [OverflowError Exception in Python](https://www.pylenin.com/blogs/overflow-error-python/)
5. [ArithmeticError Exception in Python](https://www.pylenin.com/blogs/arithmetic-error-python/)
6. [KeyError Exception in Python](https://www.pylenin.com/blogs/key-error-python/)
7. [IndexError Exception in Python](https://www.pylenin.com/blogs/index-error-python/)
8. [LookupError Exception in Python](https://www.pylenin.com/blogs/lookup-error-python/)
9. [StopIteration Exception in Python](https://www.pylenin.com/blogs/stop-iteration-error-python/)
10. [NameError Exception in Python](https://www.pylenin.com/blogs/name-error-python/)
11. [FileNotFoundError Exception in Python](https://www.pylenin.com/blogs/file-not-found-error-python/)
12. [TypeError Exception in Python](https://www.pylenin.com/blogs/type-error-python/)





