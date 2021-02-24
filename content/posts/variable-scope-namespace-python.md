---
title: "Variable Scope and Namespace in Python"
description: "Learn the various scopes of variables in Python like local, global and non local and their usage with examples."
date: 2021-02-23T11:56:11+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Python functions']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

## Youtube Video

<br>
{{< youtube id="Dnm2IWh_kxE" >}}
<br>

## An Experiment with Names

People not only have official names, but they also have nicknames 
used by their parents, friends and close acquaintances.

Let's try to understand how Python interprets names through variables.

**Code**

```python3
name = "Pylenin"
print(name)
```

**Output**

```bash
Pylenin
```

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

Let's now write a function that contains the name that I am called at home.

**Code**

```python3
name = "Pylenin"

def home():
    name = "Lenin"
    print(name)

home()
```

**Output**

```bash
Lenin
```

When we call the `home` function, Python prints `Lenin`. 
**What would happen, if I also print the `name` variable 
outside the function?**

**Code**

```python3
name = "Pylenin"

def home():
    name = "Lenin"
    print(name)

home()
print(name)
```

**Output**

```bash
Lenin
Pylenin
```

Although, the `name` variable inside the function refers to 
`Lenin`, when you print the `name` variable outside the function, 
it refers the variable declared outside the function.

The above example demonstrates the working of **Global and Local Scope**.

Before we understand that, let's understand **Namespace** in Python.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Python Namespace

**Namespace is basically a collection of names.**

When you declare a variable or an object(everything in Python is an object), Python looks up the name in what 
is known as a **Namespace** - a place where names live. If it doesn't exist, 
Python creates the name. The location of a name's assignment in your code determines the scope of the 
name's visibility to your code.

For example, when you assign `name = "Pylenin"`, 
`Pylenin` is an object which is stored in memory 
and `name` is the name we associate it with. 
We can get the address of an object through the 
built-in function `id()`.

**Code**

```python3
name = "Pylenin"
print(id(name))
```

**Output**

```bash
2088455986800
```

Now unlike other languages like C, C++ etc., you don't have to 
declare a variable way ahead of time. Also, you can assign any value to a variable 
as many times you want during the course of a program. Everytime this happens, the `id()` of the object changes.

**Code**

```python3
name = "Pylenin"
print(id(name))

name = "Lenin"
print(id(name))

name = [1, 2, 3, 4]
print(id(name))
```

**Output**

```bash
1874212773488
1874212702448
1874212772928
```

Python uses the assignment location of a variable/name **to bind it to a particular namespace**. 
In other words, the place where you assign a name in your source 
code determines the namespace it will live in, and hence its scope of visibility.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Global vs Local vs Nonlocal Scope

1. If a variable is assigned inside a `def`, it is **local** to that function.
2. If a variable is assigned in an **enclosing `def`**, it is **nonlocal** to nested functions.
3. If a variable is assigned **outside** all defs, it is **global** to the entire file.

**Code**

```python3
# global scope
name = "Pylenin"

def home():
    # local scope
    name = "Lenin"

    def sister():
        # nonlocal scope
        name = "Brother"
        print("The value of name in sister function is", name)

    sister()
    print("The value of name in home function is", name)

home()
print("The value of name outside a function is", name)
```

**Output**

```bash
The value of name in sister function is Brother
The value of name in home function is Lenin
The value of name outside a function is Pylenin
```

If you reuse a global name inside a local namespace, 
then Python creates a new local variable with the same name.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## global statement

If you don't want o create a new local variable inside your function, you can use the `global` keyword.

**Code**

```python3
name = "Pylenin"

def home():
    global name
    print(name)

home()
```

**Output**

```bash
Pylenin
```

By adding a `global` declaration to the above example, 
the variable `name` inside the def refers to the variable `name` 
outside the function. They are the same variable this time. 

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Nonlocal scope

It restricts scope lookup to just enclosing defs and **not in the global scope**. 
Nonlocal scope can only be applied for nested functions.

**Code**

```python3
name = "Pylenin"

def home():
    name = "Lenin"

    def sister():
        nonlocal name
        name = "Brother"
        print("The value of name in sister function is", name)

    sister()
    print("The value of name in home function is", name)

home()
print("The value of name outside a function is", name)
```

**Output**

```bash
The value of name in sister function is Brother
The value of name in home function is Brother
The value of name outside a function is Pylenin
```

As you can see from the above example, by usig the `nonlocal` keyword 
inside the `sister` function, you can access the variable `name` created in 
the enclosed scope of the `home` function.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Built-in Functions - globals() and locals()

To check if a variable is in the global or local scope, you can make use of 
`globals()` and `locals()` built-in methods.

Python maintains data about each identifier appearing in your 
program. This data relates to the type, value, scope level 
and location of an identifier (also called symbol). By using the 
`globals()` and `locals()` methods, you get to access all that data 
in the form of a **dictionary**.

**Code**

```python3
name = "Pylenin"

def home():
    name = "Lenin"

    def sister():
        name = "Brother"

print(globals()["name"])
print(locals()["name"])
```

**Output**

```bash
Pylenin
Pylenin
```

Now you might be confused looking at the results. Since in the global scope, 
our variable `name` corresponds to the value `Pylenin`, it makes sense that 
`globals()` built-in function contains that value in the `name` key.

However, it is also returning the same value for `locals()` \
built-in function. **Why is that?**

The reason is, Python is unable to distinguish between global scope and local scope,
when you are accessing the `locals()` function in the global scope.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

Let's try to move it within a function.

**Code**

```python3
name = "Pylenin"

def home():
    name = "Lenin"

    def sister():
        name = "Brother"
        print("locals() within sister returns",locals()["name"])

    print("locals() within sister returns",locals()["name"])
    sister()

home()
print(globals()["name"])
```

**Output**

```bash
locals() within sister returns Lenin
locals() within sister returns Brother
Pylenin
```

As you can see, now the `locals()` function is returning the appropriate 
name in the local scope of each function.

Build your foundation in Python with our [self-paced Python Bootcamp for Beginners](https://www.pylenin.com/python-bootcamp/).

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Horizontal display ad Pylenin -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-6088392832221933"
     data-ad-slot="8875064651"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
