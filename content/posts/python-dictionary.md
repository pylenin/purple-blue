---
title: "Dictionaries in Python"
description: "This article provides a clear overview of how to work with Python dictionaries"
date: 2019-08-17T21:18:30+02:00
draft: false
image: /img/python-dictionary/python-dictionary.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Mostapha Amenchar](https://www.pylenin.com/authors/#mostapha-amenchar)*

A data structure is a method to store and organize data. Python supports a number of important data structures including lists, sets ,tuples and **dictionaries**.

In this article we will focus on the Python Dictionaries. If you prefer to watch videos over text, check out the video [here](https://youtu.be/FvD0Zum8L3s).

Think of a phone book. You have names of people and the phone numbers associated to those people. A dictionary is exactly a data structure what you need if you want to implement a phone book.

A phone book is nothing more than a collection of `name: phone number` pairs.

Simillarly, a dictionary is a collection of `key: value` pairs. 

1. In python dictionaries, the key-value pair is separated by a **colon(:)**. This pair is known as an item. 
2. Items are separated from each other by a **comma (,)**. 
3. Different items are enclosed within a curly brace **({})** and all this forms a dictionary. 

Syntax of a Python dictionary:
```python3
{ key1: value1, key2: value2,...,keyN: valueN}
```

Because dictionaries are indexed by keys, the dictionary key must meet the following two conditions:

1. **A key must be unique**. Which means more than one entry per key is not allowed. When duplicate keys are encountered during assignment, the last assignment wins.


2. The keys in a dictionary **should be immutable types** like integers, floats, boolean, strings and unicodes. Tuples can also be used as a key if it does not contain a mutable structure such as a list.

```python3
# This runs fine
dict_example = {
    ("title"):"Python Dictionary"
}
print(dict_example)
>>> {'title': 'Python Dictionary'}

# This throws an error
dict_example = {
    ([1,2,3]):"Python Dictionary"
}
print(dict_example)
>>> Traceback (most recent call last):
    File <input>, line 2, in <module>
      ([1,2,3]):"Python Dictionary"
    TypeError: unhashable type: 'list'
```

Unlike keys, dictionary values have no restrictions. They can be any arbitrary python object.

In this tutorial, the following topics will be explained in details with many examples - 

1. [Creating a dictionary](#creating-a-dictionary)
 * [Curly bracket syntax](#curly-bracket-syntax)
 * [Using dict() constructor](#using-dict-constructor)
 * [Dictionary comprehension](#dictionary-comprehension)
 * [Transformation of an existing dictionary to a new dictionary](#transformation-of-an-existing-dictionary-to-a-new-dictionary)
2. [Accessing dictionary keys, values and items](#accessing-dictionaries)
 * [Accessing keys in a Dictionary](#accessing-keys)
 * [Built in methods](#built-in-methods)
3. [Modifying a dictionary](#modifying-a-dictionary)
 * [Removing an item from a dictionary](#removing-an-item-from-a-dictionary)
 * [Adding new key-values to a dictionary](#adding-new-key-values-to-a-dictionary)
 * [Sorting a dictionary](#sorting-a-dictionary)
4. [Copying a dictionary](#copying-a-dictionary)
4. [Nested dictionary](#nested-dictionary)
 * [Creation of a nested dictionary](#creation-of-a-nested-dictionary)
 * [Adding elements to a nested dictionary](#adding-elements-to-a-nested-dictionary)
 * [Accessing elements in a nested dictionary](#accessing-elements-in-a-nested-dictionary)
 * [Deleting elements from a nested dictionary](#deleting-elements-from-a-nested-dictionary)


#### Creating a dictionary

In order to create a python dictionary, you can either use the **curly bracket syntax** or the **dict()** constructor.

###### Curly bracket syntax

A pair of **empty braces {}** create an empty dictionary.

```python3
empty_dict = {}
print(empty_dict)
>>> {}

print(type(empty_dict))
>>> <class 'dict'>
```

Placing a comma-separated items **(key: value)** pairs within the braces {} adds initial items to the dictionary.

```python3
capital_dict = {"India": "New Delhi",
		        "Pakistan": "Islamabad",
		        "Nigeria": "Abuja",
		        "Zambia": "Lusaka"}
print(capital_dict)
>>> {'India': 'New Delhi', 'Pakistan': 'Islamabad', 'Nigeria': 'Abuja', 'Zambia': 'Lusaka'}
```

Merging existing dictionaries is also very easy.

```python3
capital_dict_1 = {"India": "New Delhi",
		          "Pakistan": "Islamabad",
		          "Nigeria": "Abuja",
		          "Zambia": "Lusaka"}

capital_dict_2 = {"Peru": "Lim", 
                  "Ghana": "Accra"}

capital = {**capital_dict_1, **capital_dict_2}
print(capital)
>>> {'India': 'New Delhi', 'Pakistan': 'Islamabad', 
     'Nigeria': 'Abuja', 'Zambia': 'Lusaka', 
	 'Peru': 'Lim', 'Ghana': 'Accra'}
```

###### Using dict() constructor
The **dict()** constructor build dictionaries directly from sequences of (key: value) pairs.

In order to create an empty dictionary, you can call `dict()` with no arguments.

```python3
capital_dict = dict()
print(capital_dict)
>>> {}

print(type(capital_dict))
>>> <class 'dict'>
```

The dict() constructor can be used to create python dictionaries from the following options.

  * **keyword arguments**

```python3
capital_dict = dict(India="New Delhi",
		            Pakistan="Islamabad",
		            Nigeria="Abuja",
		            Zambia="Lusaka")
print(capital_dict)
>>> {'India':'New Delhi','Pakistan': 'Islamabad','Nigeria':'Abuja','Zambia': 'Lusaka'}
``` 

  * **Single iterable of key: value pairs**

```python3
# Passing a list into the dict() constructor
capital_dict = dict([("India","New Delhi"),
		             ("Pakistan","Islamabad"),
		             ("Nigeria","Abuja"),
		             ("Zambia","Lusaka")])
print(capital_dict)
>>> {'India': 'New Delhi','Pakistan': 'Islamabad','Nigeria': 'Abuja','Zambia': 'Lusaka'}
```

  * **Single dictionary and keyword arguments**

```python3
capital_dict = dict(
                    {"India":"New Delhi", "Pakistan":"Islamabad"},
		             Nigeria = "Abuja",Zambia= "Lusaka"
                   )
print(capital_dict)
>>> {'India': 'New Delhi','Pakistan': 'Islamabad','Nigeria': 'Abuja','Zambia': 'Lusaka'}
```

  * **Single iterable of key: value pairs and keyword arguments**

```python3
capital_dict = dict([("India","New Delhi"), ("Pakistan","Islamabad")],
		            Zambia = "Lusaka")
print(capital_dict)
>>> {'India': 'New Delhi','Pakistan': 'Islamabad','Zambia': 'Lusaka'}
```

Merging existing dictionaries are only possible if keys are of the string type.

```python3
capital_dict_1 = dict([("India","New Delhi"),
		               ("Pakistan","Islamabad")])
capital_dict_2 = dict(Nigeria = "Abuja",
		              Zambia = "Lusaka")
capital = dict(**capital_dict_1,**capital_dict_2)

print(capital)
>>> {'India': 'New Delhi', 'Pakistan': 'Islamabad', 'Nigeria': 'Abuja', 'Zambia': 'Lusaka'}
```

###### Dictionary comprehension

A dictionary comprehension takes the form `{key:value for (key,value) in iterable}`. Let's look at some examples.

* **From one list:**

```python3
lst = [0,1,2,3,4,5]
dic = {x : x**2 for x in lst}

print(dic)
>>> {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

* **From two parallel lists**

```python3
countries  = ["India", "Pakistan", "Nigeria", "Zambia", "Ghana"]
capitals = ["New Delhi", "Islamabad", "Abuja", "Lukasa", "Accra"]

capital_dict = {key:value for key,value in zip(Countries,Capitals)}
print(capital_dict)
>>> {'India':'New Delhi','Pakistan':'Islamabad','Nigeria':'Abuja','Zambia': 'Lukasa','Ghana':'Accra'}
```

###### Transformation of an existing dictionary to a new dictionary

During transformation of an existing dictionary to a new dictionary, items within the existing dictionary can be conditionally included in the new dictionary and each item can be transformed as needed.

We will take the following dictionary as an example. 
```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5} 
```

**For information**: 
GDP is acronym of Gross domestic Product. GDP is a measure of the value of the total production in  a country, usually in a given year, The ideal GDP growth rate is between 2 and 3%.*

**Example 1:**

```python3
GDP_2017 = {"India": 6.6,"Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_growth_rate = {key:("ideal" if 2 < GDP_2017[key] < 3 else "not ideal")for key in GDP_2017}

print(GDP_growth_rate)
>>> {'India': 'not ideal',
     'Zambia': 'not ideal', 
     'Nigeria': 'not ideal', 
	 'Peru': 'ideal', 
     'Ghana': 'not ideal'}
```

**Example 2:**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_ideal= {key:GDP_2017[key] for key in GDP_2017 \
            if 2 < GDP_2017[key] < 3}

print(GDP_ideal)
>>> {'Peru': 2.5}
```

**Example 3:**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_ideal = {key:GDP_2017[key] for key in GDP_2017 \ 
             if GDP_2017[key] > 2 if GDP_2017[key] < 3}

print(GDP_ideal)
>>> {'Peru': 2.5}
```

**Example 4:**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_not_ideal = {key:GDP_2017[key] for key in GDP_2017 \
                 if GDP_2017[key] < 2 or GDP_2017[key] > 3}

print(GDP_not_ideal)
>>> {'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Ghana': 8.5}
```

#### Accessing dictionaries

When working with a python dictionary, it is sometimes necessary to access dictionary data  such as keys, values and items (key-value pairs). Access to this data can take place in various ways.

The methods below can be applied to access a certain value from a dictionary.

###### Accessing keys

* **Using Square brackets**

To access dictionary elements, you can use square brackets along with the key to obtain its value.

**Example 1:**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}

print(GDP_2017["India"])
>>> 6.6
```

**Example 2:**

If the given key does not exist in the dictionary, Python raises a **Key Error exception**.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}

print(GDP_2017["America"])
>>>	Traceback (most recent call last):
 	File "<input>", line 1, in <module>
    GDP_2017["America"]
	KeyError: 'America'
```  

**Example 3:**

Catching the exception is another way to handle missing keys.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
try:
    GDP_2017["America"]
except KeyError:
    print("No valid key! Please try again....")
    
>>> No valid key! Please try again....
``` 

* **get(key , default ) method**

**Example 1:**

The `get(key)` method returns the associated value for the given key if key is in the dictionary, else it returns the default value. 

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
desired_key = GDP_2017.get("India","No valid key! Please try again....")
print(desired_key)
>>> 6.6

GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
desired_key = GDP_2017.get("America","No valid key! Please try again....")
print(desired_key)
>>> No valid key! Please try again....
```
    
**Example 2:**

If default value is not passed, it returns **None**. Hence this method never raises a **Key Error**.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
desired_key = GDP_2017.get("America")
print(desired_key)
>>> None
```

###### Built in methods 

* **Accessing all values()**

The `values()` method can be used to loop over only values in a dictionary.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
for value in GDP_2017.values():
	print(value)
>>>	6.6
	4.1
	0.8
	2.5
	8.5
```

* **Accessing all keys()**

The `keys()` method can be used to loop over keys in the dictionary.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
for key in GDP_2017.keys():
	print(key)	
>>>	India
	Zambia
	Nigeria
	Peru
	Ghana
```

* **Accessing all items()**

The `items()` method can be used to loop over both the keys and values of a dictionary.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
for key,value in GDP_2017.items():
	print(key,value)
	
>>>	India 6.6
	Zambia 4.1
	Nigeria 0.8
	Peru 2.5
	Ghana 8.5
```

* **Using list comprehension to access all keys**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
key = [key for key in GDP_2017]
print(key)
>>>	['India', 'Zambia', 'Nigeria', 'Peru', 'Ghana']
```

* **Using list comprehension to access all values**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
value = [GDP_2017[key] for key in GDP_2017]
print(value)
>>>	[6.6, 4.1, 0.8, 2.5, 8.5]
```

* **Using list comprehension to access all keys and values**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
item = [(key,GDP_2017[key]) for key in GDP_2017]
print(item)
>>>	[('India', 6.6), ('Zambia', 4.1), ('Nigeria', 0.8), ('Peru', 2.5), ('Ghana', 8.5)]
```


* **Using list comprehension  + dictionary.keys() to access all keys**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
key = [key for key in GDP_2017.keys()]
print(key)
>>>	['India', 'Zambia', 'Nigeria', 'Peru', 'Ghana']
```

* **Using list comprehension + dictionary.values() to access all values**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
value = [value for value in GDP_2017.values()]
print(value)
>>>	[6.6, 4.1, 0.8, 2.5, 8.5]
```

* **Using list comprehension + dictionary.items() to access all keys and values**

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
item = item = [item for item in GDP_2017.items()]
print(item)
>>>	[('India', 6.6), ('Zambia', 4.1), ('Nigeria', 0.8), ('Peru', 2.5), ('Ghana', 8.5)]
```

#### Modifying a dictionary

Python offers a number of methods to modify a dictionary.

###### Removing an item from a dictionary

In Python, there are multiple methods for removing dictionary items.

* **del() method**

The `del` keyword can be used to delete an individual item.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
del GDP_2017["Peru"]
print(GDP_2017)
>>>	{'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Ghana': 8.5}
```

It can also be used to delete an entire dictionary.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
del GDP_2017
print(GDP_2017)
>>>	Traceback (most recent call last):
 	File <input>, line 1, in <module>
    GDP_2017
	NameError: name 'GDP_2017' is not defined
```

* **pop() method**

The `pop()` method removes an item with the provided key and returns the value of that key.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
popped_value = GDP_2017.pop("Peru")
print(popped_value)
>>>	2.5

print(GDP_2017)
>>>	{'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Ghana': 8.5}
```

* **popitem() method**

Since Python3.7, the `popitem()` method removes the last inserted item. In all the previous versions, `popitem()` used to remove a random key-value pair.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
print(GDP_2017.popitem())
>>>	('Ghana', 8.5)

print(GDP_2017)
>>>	{'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5}
```
    
* **clear() method**

The `clear()` method removes all items from a dictionary.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_2017.clear()

print(GDP_2017)
>>>	{}
```

###### Adding new key-values to a dictionary

* **Assignment operator with dictionary key**

Adding an item to a python dictionary is done by using a new index key and assigning a value to it.

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_2017["Pakistan"]= 5.7

print(GDP_2017)
>>>	{'India': 6.6,'Zambia': 4.1,'Nigeria':0.8,'Peru':2.5,'Ghana':8.5, 'Pakistan':5.7}
```

* **update() method**

The `update()` method updates the dictionary with the elements from another dictionary or from an iterable of key-value pairs. 

```python3
GDP_2017 = {"India": 6.6, "Zambia": 4.1}
Other = {"Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_2017.update(Other)

print(GDP_2017)
>>>	{'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
```

If key already exists, then the `update()` method will updates its value.

```python3
GDP_2017 = {"India": 6.6, "Zambia": "????"}
Other = {"Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_2017.update(Other)
print(GDP_2017)
>>>	{'India': 6.6,'Zambia': 4.1,'Nigeria': 0.8,'Peru': 2.5,'Ghana': 8.5}
```


* **Asteristics operator**

The `**` operator merges an old dictionary and new key-value pairs in another dictionary

```python3
GDP_2017 = {"India": 6.6, "Zambia": "????"}
Other = {"Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_NEW = {**GDP_2017,**Other}

print(GDP_NEW)
>>>	{'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
```
    

###### Sorting a dictionary

Sometimes you may wish to sort the dictionary either by key or by value.

* **Sorting by keys**

```python3
GDP_2017 = {'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
GDP_2017_sorted = {k:GDP_2017[k] for k in sorted(GDP_2017.keys())}

print(GDP_2017_sorted)
>>>	{'Ghana': 8.5, 'India': 6.6, 'Nigeria': 0.8, 'Peru': 2.5, 'Zambia': 4.1}
```

* **Sorting by values**

```python3
GDP_2017 = {'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
GDP_2017_sorted = {k:v for k,v in sorted(GDP_2017.items(),key=lambda x: x[1])}

print(GDP_2017_sorted)
>>>	{'Nigeria': 0.8, 'Peru': 2.5, 'Zambia': 4.1, 'India': 6.6, 'Ghana': 8.5}
```

#### Copying a dictionary

There are two methods to make a copy of an existing python dictionary. Both two methods result in an identical dictionary which is a **distinct object**.

* **copy() method**

```python3
GDP_2017 = {'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
GDP_2017_copy = GDP_2017.copy()

print(GDP_2017_copy)
>>>	{'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
print(id(GDP_2017) == id(GDP_2017_copy))
>>>	False
```

* **Passing an existing dictionary to dict() constructor method**

```python3
GDP_2017 = {'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
GDP_2017_copy = dict(GDP_2017)

print(GDP_2017_copy)
>>>	{'India': 6.6, 'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
print(id(GDP_2017) == id(GDP_2017_copy))
>>>	False
```

#### Nested dictionary

In Python, a nested dictionary is a collection of dictionaries within one single dictionary.

###### Creation of a nested  dictionary

```python3
GDP_Africa = {"Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_Asia = {"India": 6.6, "Pakistan": 5.7}

GDP_nested = {"GDP_Africa" :{"Zambia": 4.1,"Nigeria":0.8,"Peru":2.5,"Ghana": 8.5},
                "GDP_Asia" : {"India": 6.6, "Pakistan": 5.7}
             }
```

Nested dictionaries can also be updated by adding or removing an element. To access a key or a dictionary in a nested dictionary, use the `[]` syntax indexing.

###### Adding elements to a nested dictionary

**Example 1:**

```python3
GDP_Africa = {"Zambia": 4.1,"Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5}
GDP_Asia = {"India": 6.6, "Pakistan": 5.7}
GDP_nested = {"GDP_Africa" : GDP_Africa,
                 "GDP_Asia": GDP_Asia}
GDP_nested["GDP_Africa"]["South Africa"] = 1.3

print(GDP_nested)
>>>	{'GDP_Africa': {'Zambia': 4.1, 
                    'Nigeria': 0.8, 
                    'Peru': 2.5,
                    'Ghana': 8.5, 
                    'South Africa': 1.3}, 
     'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}}
```

**Example 2:** 

```python3
GDP_nested = {"GDP_Africa" :{"Zambia": 4.1, "Nigeria": 0.8,"Peru":2.5, "Ghana": 8.5},
                 "GDP_Asia": {"India": 6.6, "Pakistan": 5.7}}
GDP_nested["GDP_America"]={"Peru": 2.5}

print(GDP_nested)
>>>	{'GDP_Africa': {'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}, 
       'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 'GDP_America': {'Peru': 2.5}}
```

###### Accessing elements in a nested dictionary

Let's take the example of the following dictionary.

```python3
GDP_nested = {'GDP_Africa': {'Zambia': 4.1, 
                             'Nigeria': 0.8, 
                             'Peru': 2.5, 
                             'Ghana': 8.5},  
                'GDP_Asia': {'India': 6.6, 
                             'Pakistan': 5.7}, 
             'GDP_America': {'Peru': 2.5}}
```

**Example 1: How to access GDP of Zambia ?**

```python3
GDP_nested = {'GDP_Africa': {'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5},     
                'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 
             'GDP_America': {'Peru': 2.5}}
GDP_Zambia = GDP_nested["GDP_Africa"]["Zambia"]

print(GDP_Zambia)
>>>	4.1
```

**Example 2: How to access GDP_Asia?**

```python3
GDP_nested = {'GDP_Africa': {'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}, 
                'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 
             'GDP_America': {'Peru': 2.5}}
GDP_Asia = GDP_nested["GDP_Asia"]

print(GDP_Asia)
>>>	{'India': 6.6, 'Pakistan': 5.7}
```
###### Deleting elements from a nested dictionary

**Example 1: Delete GDP of Zambia**

To remove an element from a nested dictionary, use the del() method.

```python3
GDP_nested = {'GDP_Africa': {'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}, 
                'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 
             'GDP_America': {'Peru': 2.5}}
del(GDP_nested["GDP_Africa"]["Zambia"])

print(GDP_nested)
>>>	{'GDP_Africa': {'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}, 
       'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 
    'GDP_America': {'Peru': 2.5}}
```

**Example 2: Delete GDP of Africa**

To remove a dictionary from a nested dictionary there are two methods available in python.

  * **del() methode**

  ```python3
  GDP_nested = {'GDP_Africa': {'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}, 
                  'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 
               'GDP_America': {'Peru': 2.5}}

  del(GDP_nested["GDP_Africa"])
  print(GDP_nested)
  >>> {'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 'GDP_America': {'Peru': 2.5}}
  ```


  * **pop() methode**

  ```python3
  GDP_nested = {'GDP_Africa': {'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}, 
                  'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 
               'GDP_America': {'Peru': 2.5}}
  pop_value = GDP_nested.pop("GDP_Africa")

  print(pop_value)
  >>> {'Zambia': 4.1, 'Nigeria': 0.8, 'Peru': 2.5, 'Ghana': 8.5}
  print(GDP_nested)
  >>> {'GDP_Asia': {'India': 6.6, 'Pakistan': 5.7}, 'GDP_America': {'Peru': 2.5}}
  ```

The `pop()` method returns the removed dictionary.

Hope you enjoyed this article on Python dictionaries. If you have any questions, make sure to put them in the comments section.

**Would you like to suggest changes to the article** - Check out our [github repo](https://github.com/pylenin/pylenin-blogs) and create a Pull Request.
