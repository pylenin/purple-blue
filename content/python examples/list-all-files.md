---
title: "Python program to list all files in a directory"
description: "Learn how to list all the files in any given directory in Python"
date: 2021-01-29T11:50:42+05:30
draft: false
image: /img/pylenin_logo.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

#### Method 1 - Using `os.listdir()`

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

#### Method 2 - Using `os.path` 

**If you just want files, you could filter the above code down using `os.path`.

```python3
from os import listdir
from os.path import isfile, join

dir_to_search = 'C:\\Users\\91824\\'

for file in listdir(dir_to_search):
    if isfile(join(dir_to_search, file)):
        print(file)
```

#### Method 3 - Using `os.walk()`

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

#### Method 4 - Using `glob` module for pattern matching

If you want to search for only specific types of files like `.txt` or `.csv`, use the `glob` module.
It will return a list of files matching the pattern.

```python3
import glob

dir_to_search = 'C:\\Users\\91824\\'
pattern = "*.txt"
print(glob.glob(dir_to_search+"\\"+pattern))
```

**This method doesn't search for the files in the subdirectories. To search in all the subdirectories, use `os.walk` with the `glob` module**

```python3
import os
import glob

dir_to_search = 'C:\\Users\\91824\\PycharmProjects'
pattern = "*.py"
files = []
for (dirpath, dirnames, filenames) in os.walk(dir_to_search, topdown=True):
    for dir in dirnames:
        print(glob.glob(os.path.join(dirpath, dir)+"\\"+pattern))
```

#### Related Reading

1. [Python program to find the path of a given file](https://www.pylenin.com/python-examples/file-path-python/)