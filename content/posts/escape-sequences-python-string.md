---
title: "Escape sequences in Python String"
description: "Learn to use escape sequences in a string in Python"
date: 2021-01-10T23:31:05+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

#### Escape Sequences in Python

Escape sequences or Escape characters in Python, are used to insert characters that are illegal in a string.

Here is an example of an illegal character in a Python string.

```bash
Example1 - "Pylenin said, "Hi there""
Example2 - 'Pylenin said, 'Hi there''
```

In Example 1, we have double quotes inside double quotes. In Example 2, we have single quotes inside of single quotes.
These qualify as **illegal characters in a string**.

If we try to print it, Python will throw us a `SyntaxError`.

One way to fix this is by using Escape characters or sequences.

If we are using single quotes to represent a string, all the single quotes inside the string must be escaped with a `\` character. 

Similarly, if we are using double quotes to represent a string, all the double quotes inside the string must be escaped with a `\` character. .

**Code**

```python3
str1 = "Pylenin said, \"Hi there\""
print(str1)

str2 = 'Pylenin said, \'Hi there\''
print(str2)
```

**Output**

```bash
Pylenin said, "Hi there"
Pylenin said, 'Hi there'
```

#### Other Escape Sequences in Python

| Escape Sequence      | Description |
| ----------- | ----------- |
| \newline      | Backslash and newline ignored       |
| \\   | Backlash        |
| \'      | Single Quote       |
| \"   | Double Quote        |
| \a      | ASCII Bell       |
| \b   | ASCII Backspace        |
| \f      | ASCII Formfeed       |
| \n   | ASCII Linefeed        |
| \r      | ASCII Carriage Return       |
| \t   | ASCII Horizontal Tab        |
| \v      | ASCII Vertical Tab       |
| \ooo   | Character with octal value ooo        |
| \xHH      | Character with hexadecimal value HH       |

#### Related Articles
1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
4. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
5. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
6. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
7. [Python String Formatting - The Definitive Guide](https://www.pylenin.com/blogs/python-string-formatting/)