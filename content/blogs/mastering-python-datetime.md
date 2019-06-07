---
title: "Mastering Python Datetime"
description: "A simple guide to working with datetime objects and timezones in Python"
date: 2019-06-06T12:47:00+02:00
draft: true
---
<a href="https://twitter.com/pylenin?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large" data-show-screen-name="false" data-show-count="false">Follow @pylenin</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Python Datetime module is the second topic in the [#Python30](https://github.com/pylenin/Python30) course. If you prefer videos over text, [click here]() to check out my youtube video on Mastering Python Datetime.

##### Sections covered
1. [Introduction](#introduction)
2. [Getting current date and time](#getting-current-date-and-time)
3. [Splitting date and time into its components](#splitting-date-and-time-into-its-components)
4. [Timedelta](#timedelta)
5. [datetime.strftime()](#datetime-strftime)
6. [datetime.strptime()]()
7. [Timestamp to datetime and vice-versa]()
8. [Dealing with timezones]()

##### Introduction
As a Data Engineer, I tend to work with datetime objects every day of my life. For example, filtering data between particular dates, extracting data from certain APIs everyday at 6 AM for the last complete day and so on. Conveniently, Python provides the **datetime** module for dealing with date and time objects. It is simple to learn and easy to implement. In this blog I am going to walk you through the various concepts of this amazing library with simple yet effective examples to improve your understanding in this matter.

##### Getting current date and time

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
print(f"Current seconds is {curr_sec}")
```
When we execute the above snippet we get the following results.

```bash
The current date time is 2019-06-07 00:29:06.288003
The year is 2019
The month is 6
The day is 7
Current hour of the day is 0
Current minute of the day is 29
Current seconds is 6
```

##### Timedelta
A `timedelta` object provides the difference between two dates or times.
