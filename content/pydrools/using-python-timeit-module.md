---
title: "Drool 4: Benchmark your Python code with the timeit module"
date: 2019-09-22T19:25:36+02:00
draft: false
image: /img/Pydrools.png
---
<div class="sharethis-inline-follow-buttons"></div>

Think about the last time you were solving a problem! Did you have more than 1 approach to solve it?

Don't know about life, but Python has a great module to help you decide the better(fastest) way to solve a problem.

Let me introduce you to the **timeit** module. You can use it directly on your commandline or any Python IDLE.

1. **On the commandline**

        python3 -m timeit '"-".join(char for char in "Pylenin")'
        >>> 1000000 loops, best of 3: 0.851 usec per loop

2. **On a Python IDLE**

        >>> import timeit
        >>> timeit.timeit('"-".join(str(n) for n in range(100))', number=10000)
        0.8187260627746582

Read about this topic in more details in this [blog](https://www.pylenin.com/blogs/python-timeit-module/).

[**Python titmeit Module**](https://www.pylenin.com/blogs/python-timeit-module/)

<a href="https://www.pylenin.com/blogs/python-timeit-module/" rel="timeit-image">![timeit-image](/img/timeit/timeit.png)</a>

[Follow @pydrools on Twitter](https://twitter.com/pydrools)

<div align="center"><b>Don't forget to subscribe to the Pydrools Newsletter</b></div>
<div align="center"><iframe width="480" height="320" src="https://pydrools.substack.com/embed" frameborder="0" scrolling="no"></iframe></div>

