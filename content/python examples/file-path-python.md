---
title: "Python program to find the path of a given file"
description: "Learn how to find the path of any file in Python"
date: 2021-01-29T11:40:42+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### If the file is in the current directory

**Code**

```python3
import os

filename = "findme.py"
print(os.path.abspath(filename))
```

**Output**

```bash
C:\Users\91824\PycharmProjects\pythonProject\findme.py
```

#### If the file is present in some other directory

Let's say the file is present in some other directory. To get the path of the file, you have to use `os.walk()` function to get it's location..

**Code**

```python3
import os

filename = "findme.py"
dir_to_search = "C:\\Users\\91824\\PycharmProjects\\"

for root, dirs, files in os.walk(dir_to_search):
    # print(root, dirs, files)
    for name in files:
        if name == filename:
            # Path of the file
            print(os.path.join(root, name))
            # Absolute Path of the file
            print(os.path.abspath(os.path.join(root, name)))
```

**Output**

```bash
C:\Users\91824\PycharmProjects\findme.py
C:\Users\91824\PycharmProjects\findme.py
```

#### Related Reading

1. [Python program to list all files in a directory](https://www.pylenin.com/python-examples/list-all-files/)