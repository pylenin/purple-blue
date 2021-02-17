+++ 
draft = true
date = 2021-02-17T07:19:51+05:30
title = ""
description = ""
slug = "" 
tags = []
categories = []
externalLink = ""
series = []
+++
---
title: "Python While loops (With Examples)"
description: "Learn to perform iterations until a condition holds True in Python using while loops with examples."
date: 2021-02-17T07:19:51+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python control flows']
categories_weight: 3
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

The `while` statement in Python repeatedly executes a block of code as long
as a test at the top keeps evaluating to `True`. It is referred to as a **loop** because control 
keeps looping back to the beginning **until the test becomes `False`**. 

When the test becomes false, the code block following the while block is executed. 
If the test is false to begin with, **the body never runs**.

**Syntax of while loops**

```bash
while <test>: # Loop test
    <code block> # Loop body
else: # Optional else
    <code block> # Run if didn't exit loop with break
```

### Example 1 - Printing a statement forever

**Code**

```python3
while True:
    print("Press Ctrl-C to exit this while loop")
```

**Output**

```bash
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Press Ctrl+C to exit this while loop
Traceback (most recent call last):
  File "some_file_location", line 2, in <module>
    print("Press Ctrl-C to exit this while loop")
KeyboardInterrupt
```

The above code will run forever as long as it is not interrupted. From the article on [booleans](https://www.pylenin.com/blogs/booleans-in-python/), you should know that `True` is the boolean representation of integer 1. 
Similarly, `False` is the boolean representation of 0.

You can also use integer representations of booleans in `while` loops.

**Code**

```python3
# The code block won't be executed
while 0:
    print("It won't be executed!")

while 1:
    print("It will be executed. Press Ctrl-C to exit")
```

**Output**

```bash
It will be executed. Press Ctrl-C to exit
It will be executed. Press Ctrl-C to exit
It will be executed. Press Ctrl-C to exit
It will be executed. Press Ctrl-C to exit
It will be executed. Press Ctrl-C to exit
It will be executed. Press Ctrl-C to exit
Traceback (most recent call last):
  File "some_file_location", line 5, in <module>
    print("It will be executed. Press Ctrl-C to exit")
KeyboardInterrupt
```

### Example 2 - Remove elements from a list until empty

This example demonstrates how to [pop](https://www.pylenin.com/blogs/python-lists/#python-list-pop) an element from a list, until it is empty.

**Code**

```python3
x = [1, 2, 3]

while len(x) > 0:
    popped_elem = x.pop()
    print(f"The removed element is {popped_elem}")
    print("Now the list is", x)
    print()
else:
    print("The list is empty")
```

**Output**

```bash
The removed element is 3
Now the list is [1, 2]

The removed element is 2
Now the list is [1]

The removed element is 1
Now the list is []

The list is empty
```

As long as `len(x)` is greater than 0, the while block is executed. Once all the elements are removed from the list, the test returns `False`. Python then moves on the `else` block.

**Note:-** The empty `print()` statement within the `while` loop is used to create an empty line for better readability of results. 
To learn more about different variations of print statements, [check out this article](https://www.pylenin.com/blogs/python-print/).

### Example 3 - Taking user inputs

This example demonstrates usage of [user inputs](https://www.pylenin.com/blogs/how-input-works-python/) 
with `while` loops to execute a certain task.

For e.g., the current example demonstrates, asking user to enter the names of their friends and terminate when the user presses `q`. 
Ultimately, show the list of friends entered by the user.

**Code**

```python3
# Set a variable to check if user wants to input
user_will_input = True
friends = []

while user_will_input:
    friend_name = input("Enter your friend's name ==> ")
    if friend_name != 'q':
        # Add to friends, only if user doesn't enter "q"
        friends.append(friend_name)
    else:
        # Set to False, if user enters "q"
        user_will_input = False
else:
    if len(friends) > 0:
        print(f"Your friends are {','.join(friends)}")
    else:
        print("You have no friends!")
```

**Output**

```bash
Enter your friend's name ==> Sonali
Enter your friend's name ==> Chinmayee
Enter your friend's name ==> Ashish
Enter your friend's name ==> q
Your friends are Sonali,Chinmayee,Ashish
```

The above code uses the [join() method](https://www.pylenin.com/blogs/python-string-join/). 
Check out the linked article to learn what it does.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).
