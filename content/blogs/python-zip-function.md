---
title: "Power of zip() in Python"
description: "A simple guide to understanding the applications of zip() in python"
date: 2019-06-07T10:52:43+02:00
draft: false
---
<a href="https://twitter.com/pylenin?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large" data-show-screen-name="false" data-show-count="false">Follow @pylenin</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Sections covered:

1. [Why use zip?](#why-use-zip)
2. [Unzipping](#unzipping)
3. [Solve a competitive interview question](#solve-a-competitive-interview-question)

##### Why use zip?

`zip()` allows you to map the same index of multiple iterables.

Syntax of zip
```python
zip(*iterables)
```
Let's look at an example.
```python
x = [1, 2, 3]
y = [4, 5, 6]

mapping = zip(x, y)
print(mapping)
```
If you run the above snippet, it will return you something like this.
```bash
<zip object at 0x1033d7d08>
```

As you can see, when you `print(mapping)`, it returns a `zip object`. This is an iterator object that consists of `tuples`. To check out its contents, let's convert it to a list.
```python
print(list(mapping))
```
This snippet produces the following result.
```bash
[(1, 4), (2, 5), (3, 6)]
```

##### Unzipping
Now how to unzip? You can do that with the `*` operator. Let's convert our `mapping` variable back to its components.
```python
x,y = zip(*mapping)

print(x)
print(y)
```
This in turn assigns tuples to `x` and `y` variables.

```bash
(1, 2, 3) # Value of x
(4, 5, 6) # Value of y
```
As I mentioned earlier, zip() creates an **iterator of tuples**. Therefore when we unpack, we get our x and y values back as tuples. You can use the `list()` method to convert them back to lists.

##### Solve a competitive interview question

Write a function to map all elements of the same index for the following list. 
```python
input_lst = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

output_lst = [[1, 4, 7], [2, 5, 8], [3, 6, 9]]
```
The function should take in the `input_lst` and return the `output_lst`.

If you are able to solve it, make sure to **tweet** your answer to me **@pylenin**.
