+++ 
draft = true
date = 2021-01-13T10:11:30+05:30
title = ""
description = ""
slug = "" 
tags = []
categories = []
externalLink = ""
series = []
+++
---
title: "Python String count() Method"
description: "Learn what count() method does to Python strings"
date: 2021-01-13T10:11:30+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

The `encode()` method in Python encodes a string using the specified encoding. 
If no encoding is specified, `UTF-8` encoding will be used.

#### Syntax of `encode()` method

```bash
string.encode(encoding, errors)

encoding: Encoding to use(optional)
          Default value is UTF-8.
errors:	Required Error method(Optional)
```

Check out the list of [standard encodings with Python](https://docs.python.org/2.4/lib/standard-encodings.html).

You can use the following error values.

1. `backslashreplace` - use a backslash instead of the character that could not be encoded
2. `ignore`	- ignore the characters that cannot be encoded.
3. `namereplace` - replace the character with a text explaining the character.
4. `strict`	- Default, will raise an error on failure.
5. `replace` - replace the character with a question mark.
6. `xmlcharrefreplace` - replace the character with an xml character.

Python is only going to use these above error types, if it runs into some error while encoding.

##### Example 1 - Simple encoding to UTF-8

**Code**
```python3
str1 = "I like Pylenin"

print(str1.encode())
```

**Output**

```bash
b'I like Pylenin'
```

##### Example 2 - Encoding a Non-ASCII string to ASCII

**Code**
```python3
str1 = "Pylenin like äpples"

print(str1.encode('ASCII', errors='backslashreplace'))
print(str1.encode('ASCII', errors='ignore'))
print(str1.encode('ASCII', errors='namereplace'))
print(str1.encode('ASCII', errors='replace'))
print(str1.encode('ASCII', errors='xmlcharrefreplace'))
```

**Output**

```bash
b'Pylenin like \\xe4pples'
b'Pylenin like pples'
b'Pylenin like \\N{LATIN SMALL LETTER A WITH DIAERESIS}pples'
b'Pylenin like ?pples'
b'Pylenin like &#228;pples'
```

Check out other [commonly used Python string methods](https://www.pylenin.com/blogs/common-python-string-methods).

#### Related Articles

1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
4. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
5. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
6. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
7. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
8. [Python String Formatting - The Definitive Guide](https://www.pylenin.com/blogs/python-string-formatting/)
