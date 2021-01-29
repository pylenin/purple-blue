---
title: "Python program to list all files in a directory"
description: "Learn how to list all the files in any given directory in Python"
date: 2021-01-29T11:50:42+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Using `os.listdir()`

You can use `os.listdir()` to get you everything that is present in a directory(both files and directories).

**Example**

```python3
import os

# List everything in current directory
print(os.listdir())

# List everything in a different directory
print(os.listdir('C:\\Users\\91824\\'))
```
**The above code gets you every file and directory present in the path.**

#### Using `os.path` 

**If you just want files, you could filter the above code down using `os.path`.

```python3
from os import listdir
from os.path import isfile, join

dir_to_search = 'C:\\Users\\91824\\'

for file in listdir(dir_to_search):
    if isfile(join(dir_to_search, file)):
        print(file)
```

#### Using `os.walk()`

You could also use `os.walk()` function 
which will generate the file names present in a directory 
by going through the directory tree, either top-down or bottom-up.

```python3
import os

dir_to_search = 'C:\\Users\\91824\\'
files = []
for (dirpath, dirnames, filenames) in os.walk(dir_to_search, topdown=True):
    files.append(filenames)
```

**You could also make it shorter.**

```python3
import os

dir_to_search = 'C:\\Users\\91824\\'
_, _, filenames = next(os.walk(dir_to_search))
```

#### Related Reading

1. [Python program to find the path of a given file](https://www.pylenin.com/python-examples/file-path-python/)