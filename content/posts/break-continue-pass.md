---
title: "Python break, continue and pass (With Examples)"
description: "Learn to use break, continue and pass statements inside loops in Python with examples."
date: 2021-02-18T08:31:21+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python control flows']
categories_weight: 4
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Prerequisites**

1. [for loops in Python](https://www.pylenin.com/blogs/python-for-loop/)
2. [while loops in Python](https://www.pylenin.com/blogs/python-while-loop/)

Loops allow you to perform repetitive tasks on iterables in an automated fashion. However, you might have an additional requirements in your loop. For e.g.

1. Stop an iteration when a condition is satisfied
2. Move on to the next iteration without performing any task
3. Add an empty statement placeholder to allow further improvements to your code later.

Keywords like `break`, `continue` and `pass` prove useful in such situations.

**break** - jumps out of the closest enclosing loop

**continue** - moves on to the next iteration in the loop

**pass** - Empty placeholder. Does nothing at all.



## break statement in Python

`break` is used to exit the loop when a specific condition is met.

### Example 1

**Code**

```python3
i = 1
while True:
    print(f"The value of i is {i}")
    # Break the loop when i reaches 10
    if i == 10:
        break
    i+=1
```

**Output**

```bash
The value of i is 1
The value of i is 2
The value of i is 3
The value of i is 4
The value of i is 5
The value of i is 6
The value of i is 7
The value of i is 8
The value of i is 9
The value of i is 10
```

The other way to do it would be to include this condition with the `while` statement.

**Code**

```python3
i = 1
while i <= 10:
    print(f"The value of i is {i}")
    i+=1
```

**Output**

```bash
The value of i is 1
The value of i is 2
The value of i is 3
The value of i is 4
The value of i is 5
The value of i is 6
The value of i is 7
The value of i is 8
The value of i is 9
The value of i is 10
```

Now don't think the usage of break is useless because, 
you can rewrite the above code even smaller without the 
use of `break`. In programming, you will be faced with other 
complicated situations where `break` will provide you with a 
cleaner and more efficient code.



### Example 2

Let's try to redo the example from the article on [while loops](https://www.pylenin.com/blogs/python-while-loop/#example-3-taking-user-inputs).
In that example, a temporary variable `user_will_input` is used to check if the user wants to enter a friend's name. If the user enters `q`, the variable is set to `False` and the loop is terminated. 
This time, let's make use of the `break` statement when the same condition is met **but without using a temporary variable**.



**Code**

```python3
friends = []
while True:
    friend_name = input("Enter your friend's name ==> ")
    if friend_name == 'q':
        break
    else:
        friends.append(friend_name)

if len(friends) > 0:
    print(f"Your friends are {','. join(friends)}")
else:
    print("You have no friends!")
```

**Output**

```bash
Enter your friend's name ==> Shishir
Enter your friend's name ==> Ashish
Enter your friend's name ==> Chinmayee
Enter your friend's name ==> q
Your friends are Shishir,Ashish,Chinmayee
```

**There are 2 observations that you should make.**

1. Using `break` instead of an additional variable achieves the same objective. This makes your code relatively more efficient.
2. In the previous example, the print statement that tells your friends was within an `else` block. But in this code, the print statements are being used outside the `while` loop.

The code within an `else` block(part of the while loop) is only executed when the loop terminates naturally, i.e., you didn't terminate the loop with `break` statement. 
Try and run the below code.

**Code**

```python3
friends = []
while True:
    friend_name = input("Enter your friend's name ==> ")
    if friend_name == 'q':
        break
    else:
        friends.append(friend_name)
else:
    if len(friends) > 0:
        print(f"Your friends are {','.join(friends)}")
    else:
        print("You have no friends!")
```

**Output**

```bash
Enter your friend's name ==> Shishir
Enter your friend's name ==> Ashish
Enter your friend's name ==> Chinmayee
Enter your friend's name ==> q
```

As you can see, the code within the `else` block isn't executed 
as your `while` loop has a break statement in it.



### Example 3 - Using break in for loops

You can also use `break` statements in `for` loops. 

**Code - [Finding Nemo Example - Start at 2:12](https://youtu.be/m-mdlS4ynis)**

```python3
my_list = ["Gill", "Nemo", "Bloat", "Dory", "Gurgle"]

for elem in my_list:
    if elem == "Nemo":
        print("I found Nemo!")
        break
    else:
        print("Still looking for Nemo!")
```

**Output**

```bash
Still looking for Nemo!
I found Nemo!
```

Without the use of `break` statement, you would unnecessarily iterate over every fish in the list. This is very inefficient. By using the `break` statement, you **terminate the iteration, once Nemo is found!**.



## continue statement in Python

The `continue` causes an immediate jump to the next iteration in the loop. 
You can use it to skip code executions for certain conditions.



### Example 1

The code below runs infinitely, asking users to input a number and only prints out, if the number is odd.

**Code**

```python3
while True:
    number = int(input("Enter a number ==> "))
    if number %2 == 0:
        continue
    print(f"{number} is odd")
```

**Output**

```bash
Enter a number ==> 3
3 is odd
Enter a number ==> 2
Enter a number ==> 1
1 is odd
Enter a number ==> 10
```

Because `continue` immediately moves to the top of the loop, 
you don't need to nest the `print` statement within an `else` block. 
The `print` statement is only reached, if `continue` statement 
isn't executed. 



### Example 2 - Using continue with for loops

You can also use `continue` statements in `for` loops. 
Let's go back to the **[Finding Nemo Example](https://youtu.be/m-mdlS4ynis)**.

**Code - Without using continue**

```python3
my_list = ["Gill", "Nemo", "Bloat", "Dory", "Gurgle"]

for elem in my_list:
    if elem == "Nemo":
        print("I found Nemo!")
        break
    else:
        print("Still looking for Nemo!")
```

**Output**

```bash
Still looking for Nemo!
I found Nemo!
```

What we would like to additionally do is, stop printing `Still looking for Nemo!` when Nemo isn't found. Also we want to keep track of the number of fish we had to iterate over until we found Nemo.

**Code**

```python3
my_list = ["Gill", "Nemo", "Bloat", "Dory", "Gurgle"]
number_of_loops = 0
for elem in my_list:
    if elem == "Nemo":
        number_of_loops += 1
        print(f"Fish no. {number_of_loops} is Nemo")
        break
    else:
        number_of_loops += 1
        continue
```

**Output**

```bash
Fish no. 2 is Nemo
```



## pass statement in Python

`pass` is merely a placeholder statement. It does nothing.

Ideally when you are working on a problem and want to 
revisit your code later to make changes, you make use of 
a pass statement.

If you are a beginner, that is the only use of `pass` statements. 
However, if you have little bit of experience with programming, 
you can use `pass` statements to ignore exceptions 
caught during [exception handling](https://www.pylenin.com/blogs/python-try-except-else-finally/) 
and to define empty class objects and functions.



### Example 1 - Infinite while loop 

**Code**

```python3
while True:
    pass
```

The above code does nothing other than **warming up your computer.**



### Example 2 - Empty functions and classes

**Code**

```python3
def my_new_function():
    pass # Code to be added later
```

**Fun fact -** You can also use `...` to replace pass statements and your code won't run into any issue.

**Code**

```python3
def my_new_function():
    ...
```

The three dots (`...`) are known as **Ellipsis**. 
They do nothing by themselves and hence, can be used to serve as
an alternative to the `pass` statement, especially for code to be filled in
later.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).


