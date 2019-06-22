---
title: "Mastering Python Datetime (With Examples)"
description: "A simple guide to working with python datetime objects and timezones in Python"
date: 2019-06-06T12:47:00+02:00
draft: false
image: /img/datetimemeta.png
---
<a href="https://twitter.com/pylenin?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large" data-show-screen-name="false" data-show-count="false">Follow @pylenin</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

![python-datetime-image](/img/datetimeblog.png)

Python Datetime module is the second and third topic in the [#Python30](https://github.com/pylenin/Python30) course. If you prefer videos over text, [click here](https://youtu.be/B4X1gidJzTs) to check out my youtube videos on Mastering Python datetime.

##### Sections covered
1. [Introduction](#introduction)
2. [Getting current datetime](#getting-current-datetime)
3. [Splitting date and time into its components](#splitting-date-and-time-into-its-components)
4. [Creating manual date and time objects](#creating-manual-date-and-time-objects)
5. [Timedelta](#timedelta)
6. [datetime.strftime()](#datetime-strftime)
7. [datetime.strptime()](#datetime-strptime)
8. [Datetime to Unix timestamp and vice-versa](#datetime-to-unix-timestamp-and-vice-versa)
9. [Dealing with timezones](#dealing-with-timezones)

##### Introduction
As a Data Engineer, I tend to work with datetime objects every day of my life. For example, filtering data between particular dates, extracting data from certain APIs everyday at 6 AM for the last complete day and so on. One of my regular tasks is to maintain an AWS Lambda function that runs every hour and collects the WLM statistics of our Redshift cluster.  The logs are outputted to an S3 bucket. I have a python script that extracts data from the logs every one hour and plots the irregularities in Looker. This task also requires playing with datetime objects. Regarding outputting efficient log files, I have written a blog about using the **Python Logging** module with various examples and case scenarios that can be used in applications like the above. You can check the blog [here](https://www.pylenin.com/blogs/python-logging-guide/).

Conveniently, Python provides the **datetime** module for dealing with date and time objects. It is simple to learn and easy to implement. In this blog I am going to walk you through the various concepts of this amazing library with simple yet effective examples to improve your understanding in this matter.

##### Getting current datetime

To get the current date and time, we can use the **datetime** class.
```python
# curr_date_time.py

from datetime import datetime

curr_datetime = datetime.now()
curr_date = curr_datetime.date()
curr_time = curr_datetime.time()

print(f"The current date time is {curr_datetime}")
print(f"Today's date is {curr_date}")
print(f"Current time is {curr_time}")
```

`datetime.now()` provides the current local date and time. When we use it with both the `date()` and `time()` methods, it returns us the current date and time respectively. Here is the output of the above snippet.

```bash
The current date time is 2019-06-06 23:53:00.676558
Today's date is 2019-06-06
Current time is 23:53:00.676558
```

##### Splitting date and time into its components
We can use the `datetime` object's class attributes for splitting a timestamp into its constituent components like year, month, day, hour, minute and seconds.
```python
# curr_date_time.py

from datetime import datetime

curr_datetime = datetime.now()

curr_year = curr_datetime.year
curr_month = curr_datetime.month
curr_day = curr_datetime.day

curr_hour = curr_datetime.hour
curr_min = curr_datetime.minute
curr_sec = curr_datetime.second

print(f"The current date time is {curr_datetime}")

print(f"The year is {curr_year}")
print(f"The month is {curr_month}")
print(f"The day is {curr_day}")

print(f"Current hour of the day is {curr_hour}")
print(f"Current minute of the day is {curr_min}")
print(f"Current seconds are {curr_sec}")
```
When we execute the above snippet we get the following results.

```bash
The current date time is 2019-06-07 00:29:06.288003
The year is 2019
The month is 6
The day is 7
Current hour of the day is 0
Current minute of the day is 29
Current seconds are 6
```

##### Creating manual date and time objects
We can create manual date and time object in our python applications using the python datetime module. Lets say we want to create a date object for `January 1 2017`. To do that we can make use of the `date` class in the datetime module. We have to pass in the `year`, `month` and `day` arguments.
```python
# new_date_time.py

from datetime import date

req_date = date(year=2017,
                month=1,
                day=1)

print(req_date)
```
On executing the above piece of code, we get our required date object.
```bash
2017-01-01
```

We can also use the `datetime` class in our datetime module to create the above date object. However, the datetime class consists of information for both the date and time object. This is how a datetime class looks like.
```python
class datetime.datetime(year, month, day, hour=0, minute=0, second=0, microsecond=0, tzinfo=None, *, fold=0)
```
The `year`, `month` and `day` arguments are mandatory. The rest of the arguments are optional.
```python
# new_date_time.py

from datetime import datetime

req_date = datetime(year=2017,
                month=1,
                day=1)

print(req_date)
```
If we create a date object this way, we are also going to get the default time information which is going to be set to **0000 hours** or **12 midnight**.
```bash
2017-01-01 00:00:00
```
Let's say we want the time of the day to be **9:30:36 AM**. To add that information, we also have to supply the `hour`, `minute` and `second` information.
```python
# new_date_time.py

from datetime import datetime

req_date = datetime(year=2017,
                month=1,
                day=1,
                hour=9,
                minute=30,
                second=36)

print(req_date)
```
The above snippet produces the following result.
```bash
2017-01-01 09:30:36
```
Using the above logic, we can also create a time object by using the `time` class in the python datetime module. In that case we just have to provide the `hour`, `minute` and `second` details. Note that all of these are optional. If you don't provide any arguments, you will receive a time object pointing to **0000 hours** or **12 AM**.
```python
# new_time.py
from datetime import time


req_time = time(
                hour=9,
                minute=30,
                second=36)

null_time = time()

print(req_time)
print(null_time)
```
When you run the above snippet of code, you get the following results.
```bash
09:30:36 # req_time
00:00:00 # null_time
```
##### Timedelta
A `timedelta` object provides the difference between two dates or times. The general syntax looks like this.
```bash
class datetime.timedelta(days=0, seconds=0, microseconds=0, milliseconds=0, minutes=0, hours=0, weeks=0)
```
All the arguments are optional and default to **0**. You can pass in both **positive and negative values**. This is a great tool to possess while dealing with python datetime objects. 

Let's understand how to use it with some examples.

1. **What is the date and time 2 days 3 hours and 15 minutes ahead from now?**
    ```python
    # new_date_time.py

    from datetime import datetime,timedelta

    # Get the current date and time
    curr_date_time = datetime.now()
    print(curr_date_time)


    time_diff = timedelta(days=2,
                        hours=3,
                        minutes=15)

    # Add time diff to the current time
    req_date_time = curr_date_time + time_diff

    print(req_date_time)
    ```
    When you run the above code, you will get the required date and time you want.
    ```bash
    2019-06-07 22:52:03.014472 # curr_date_time
    2019-06-10 02:07:03.014472 # req_date_time
    ```
    We can also use negative values in there to go backwards in time.

2. **What is the date and time 1 week and 3 days before 2019 June 1, 9 AM?**
    ```python
    # new_date_time.py

    from datetime import datetime,timedelta

    # Get the base date and time
    base_date_time = datetime(year=2019,
                            month=6,
                            day=1,
                            hour=9)
    print(base_date_time)


    time_diff = timedelta(weeks=-1,
                        days=-3)

    # Subtract time diff to the current time
    req_date_time = base_date_time + time_diff

    print(req_date_time)
    ```
    When you run the above code, it should work like a charm.
    ```bash
    2019-06-01 09:00:00 # base_date_time
    2019-05-22 09:00:00 # req_date_time
    ```

These examples should get you going regarding any questions related to timedelta.

##### datetime.strftime()
Ever had to to copy date and time to JSON? Or may be named a log file using the date and time as suffix? In order to carry on those tasks, you need to convert a python datetime object to its relevant and usable string representation. The `strftime` method from the datetime class allows you to create a string representation of a datetime object. In order to do that you are supposed to provide two arguments.

1. **A datetime object**
2. **An explicit formatting string**

To check the complete list of formatting strings, [click here](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-behavior).

Let's use this method to convert current date and time to different formats like:

1. Print the date in the format of **January 1, 1970**
2. Print the **day of the week** with time in **AM/PM**

```python
# new_date_time.py

from datetime import datetime

# Get the base date and time
base_date_time = datetime.now()
print(base_date_time)

# Format it to January 1, 1970
print(datetime.strftime(base_date_time, "%B %d, %Y"))

# Print the day of the week with time in AM/PM
print(datetime.strftime(base_date_time, "%A, %I:%M:%S %p"))
```
The above code produces the following result.
```bash
2019-06-07 23:25:23.764530
June 07, 2019
Friday, 11:25:23 PM
```
Isn't it very simple to use?

**One extra Tip**

Does the leading 0 in `June 07` bother you? You can remove the leading 0 by using a `-` in your formatting strings.

```python
# new_date_time.py

from datetime import datetime

# Get the base date and time
base_date_time = datetime.now()

# Format it to January 1, 1970
print(datetime.strftime(base_date_time, "%B %-d, %Y"))
```
The above code produces the following result.
```bash
June 7, 2019

##### datetime.strptime()
The `strptime` method does exactly the opposite of `strftime`. It converts a string to a datetime object. In order to do that, we need to provide two kinds of arguments.

1. **A string representating date and time**
2. **String formatting code that is equivalent to the string**

Let's convert a datetime string to a datetime object.

```python
# new_date_time.py

from datetime import datetime

dt_string = "January 1, 2019"

dt_object = datetime.strptime(dt_string, "%B %d, %Y")
print(dt_object)
```

Remember to use the formatting exactly as your string is built. If the string and the formatting don't match, python will return you a `ValueError`. The above snippet returns the following result.
```bash
2019-01-01 00:00:00
```

##### Datetime to Unix timestamp and vice-versa

The Unix timestamp is the number of seconds since the **epoch** until any date and time. Epoch is the generic term used for **January 1, 1970**. We can use the python datetime module to convert any datetime object to its Unix timestamp counterpart and back.

```python
# new_date_time.py

from datetime import datetime

# convert current datetime object to timestamp
tstamp = datetime.now().timestamp()
print(tstamp)

# convert timestamp back to datetime object
dt_object = datetime.fromtimestamp(tstamp)
print(dt_object)
```
You can use this method on any datetime object of your choice. When you execute the above code, you will get the results like this.
```bash
1559979096.440111
2019-06-08 09:31:36.440111
```

##### Dealing with timezones

So far we have been dealing with **naive** datetime objects. What are naive datetime objects? It doesn't have any information about the timezone. You can easily check if a datetime object is naive or not using `tzinfo`. If it is a naive datetime object, the code below should return you `None`.
```python
# new_date_time.py

from datetime import datetime

dt_object = datetime(year=2019,
                     month=1,
                     day=1)

print(dt_object.tzinfo)
``` 
This is one of the **drawbacks** of the python datetime module. There is no way to make the datetime object aware of timezones using any class or method from the python datetime module. That doesn't mean that you can't achieve it. You can use the `pytz` library to add timezone information to your application.

So how to figure out the correct timezone name?

1. You can refer [here](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) for a list of all the timezone database names.
2. You can also use the `pytz` library to produce a list of all the timezones.

```python
# tz_list.py

import pytz

print(pytz.all_timezones)
```
Any of the above methods should help you select the correct timezone for your requirement. Once you have the name of the timezone, you can include it in your application.

```python
# tz_info.py

from datetime import datetime
import pytz

dt = datetime.now()
readable_dt = datetime.strftime(dt, "%d/%m/%Y, %H:%M:%S")
print(readable_dt)

tz_India = pytz.timezone("Asia/Calcutta")
dt_India = datetime.now(tz_India)
readable_dt_India = datetime.strftime(dt_India, "%d/%m/%Y, %H:%M:%S")
print(readable_dt_India)
```
When you execute the above snippet of code you can see the difference between your current datetime and the current datetime in India.

This blog is very basic and to the point. But believe me when I say this, it is going to be very crucial. Using date and time objects efficiently in your application is of paramount importance and the above examples will get you through maximum (if not all) of the issues you might deal with using datetime objects in your application. 
I hope you enjoyed this blog. If you have any questions or criticisms, do put them down in the comments section below.

**Would you like to suggest changes to the article** - Check out our [github repo](https://github.com/pylenin/pylenin-blogs) and create a Pull Request.

