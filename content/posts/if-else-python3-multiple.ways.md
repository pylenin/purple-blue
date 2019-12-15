---
title: "Writing If-else multiple ways in Python 3"
description: "Different ways to write if else clause in Python 3"
date: 2019-12-15T16:43:32+01:00
draft: false
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

We all know about `if else` clauses in Python 3. Probably we use them on a daily basis.

In this article, I will show you different ways to write `if else` clause.

* **Most Readable Way**

  ```python3
  score = 46
  
  if score > 35:
    print("Passed")
  else:
    print("Fail")
  ``` 

* **A little shorter**

  ```python3
  score = 46
  
  result = "Passed" if scored > 35 else "Fail"
  ```
  
  You would usually see such forms while writing list comprehensions in Python 3. However, you could still use them in other ways.
  
* **Code Golf Suitable**

  ```python3
  score = 46
  
  result = scored > 35 and "Passed" or "Fail"
  ```
  As we progress, we see that the readability keeps going down. According to Zen of Python, your code should always be readable.
  Hence, I wouldn't recommend using this form of `if else` clause.
  
  However, it is still pretty useful for [Code Golf](https://youtu.be/Jx8JyhrJo4c).
  
To learn more about `if else` clause in Python 3, check out this video.

<br>
{{< youtube id="LEQNrCdV_Cg" >}}
<br>

<div align="center"><b>Don't forget to subscribe to the Pydrools Newsletter</b></div>
<div align="center"><iframe width="480" height="320" src="https://pydrools.substack.com/embed" frameborder="0" scrolling="no"></iframe></div>
