---
title: "A Step-by-Step guide to Python Logging"
description: "A beginner guide to understanding the advantages and usage of Python Logging module"
date: 2019-06-05T13:23:24+02:00
draft: false
image: /img/loggingmeta.png
aliases: [/posts/python-logging-guide/]
---
<a href="https://twitter.com/pylenin?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large" data-show-screen-name="false" data-show-count="false">Follow @pylenin</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Python Logging is the first topic in the [#Python30](https://github.com/pylenin/Python30) course. If you prefer videos over text, [click here](https://youtu.be/HJIz1PTMmuE) to check out my youtube video on Python Logging. However if blogs are your thing, here is a step-by-step guide to understanding the **python logging module** and why they should be preferred over **print**.

##### Sections covered
1. [Introduction to Python Logging](#introduction-to-python-logging)
2. [Can we not achieve the same with print statements?](#can-we-not-achieve-the-same-with-print-statements)
3. [Why is Printing not sufficient for Logging?](#why-is-printing-not-sufficient-for-logging)
4. [Advantages of using Python Logging module](#advantages-of-using-python-logging-module)
5. [Levels of Logging](#levels-of-logging)
6. [A simple example of Logging](#a-simple-example-of-logging)
7. [Formatting our logs to have more information](#formatting-our-logs-to-have-more-information)
8. [Logging to a file](#logging-to-a-file)
9. [Logging from multiple modules](#logging-from-multiple-modules)
10. [Root Logger](#root-logger)
11. [Configuring a Main Logger](#configuring-a-main-logger)
12. [Some logging scenarios](#some-logging-scenarios)
13. [Advantages of configuring a Main Logger](#advantages-of-configuring-a-main-logger)

##### Introduction to Python Logging
In general, Logging is an important activity in any non-trivial software development application. It informs you about the flow of events in your entire application with other useful metadata like the time at which an event occurred, the severity of the event, the line no. on which the event was logged, the function or the module in which the event triggered and so on. You can easily control the type of information you decide to include in our log files and also the way it shows up.

##### Can we not achieve the same with print statements?

Printing out stuff is definitely useful. It will certainly qualify as one of the most widely used function in any programming language. It is a great tool for conveying relevant information to programmers during the execution of a program. It is also a great debugging tool. Let’s see an example.

```python
# printing.py

print(1/0)
```
When you run the above code, you should get the following output.
```bash
Traceback (most recent call last):
  File printing.py, line 1, in <module>
    print(1/0)
ZeroDivisionError: division by zero
```
There is a ton of information here. We have the line no. in which the python interpreter detected an error, the python statement that created the error and also the nature of the error. In the case above, it is a **ZeroDivisionError**.

Let’s say you don’t want to raise a traceback error. In that case you can can use a **try** statement with an **except** clause.
```python
# printing.py

try:
    1/0
except Exception as e:
    print(e)
```
When you execute the above piece of code, it is going to print **division by zero**. Usually it is recommended to handle exceptions in your code using try and except rather than letting it fail. Why? So that the flow of program does not crash because of the exception encountered. But now we are missing relevant details that are useful for debugging the error. We are missing the file name and the line no. at which the error occurred. To solve this problem, we can use the traceback library to catch various other details about the exception.

```python
# printing.py

import traceback

try:
    1/0
except:
    traceback.print_exc()
```
This way we not only receive the traceback information but also allow our code flow to successfully end without crashing.

Inspite of all the obvious benefits, Printing is still not the best tool for logging.
##### Why is Printing not sufficient for Logging?
Below are the 4 reasons that make print unsuitable.

1. **Printing does not provide us with the timestamp of an error**

    One of the important information that print misses out on is the timestamp at which a particular error occurred. This can prove to be a big factor while debugging our application. It may not be important for small pieces of code that we run and test in real time. But for larger applications, lack of timestamp for an error will certainly have a huge impact. Sure we can use the datetime module to add that extra piece of information. But then we would just be making our codebase messier by adding irrelevant pieces of code to make up for the missing information instead of using something that already addresses everything we need (logging).

2. **Printing to console is bad practice for large scale applications**

    Imagine this! You have written a Python library that others are now using for solving a certain purpose. You are very generous with using the print function in your codebase. So the user will see different kinds of print statements that he/she won’t likely recognize. This is very bad practice and therefore should be avoided.

3. **Its not possible to save print messages to every kind of file**

    When you print messages, it is first converted to text strings. You can use the file argument in print to save your messages to a file. However, it must be an object with a **write(string)** method. Therefore it is not possible to write message to binary files.

4. **Difficult to categorize print statements**

    Imagine a log file containing all sorts of print statements. Once your application has gone through various stages of development and finally in production, it is going to become very difficult to categorize and debug those print statements. You might argue that you can modify your print statements to suit the various stages and provide more information. But that would be adding junk to your codebase to make up for something that print is not suitable and was not even built for.

##### Advantages of using Python Logging module
The logging module in Python provides a solution for all the above problems.

1. You can easily control the **format of the messages** you log. The module comes with a lot of useful attributes that you can decide to include in your log.

2. You can log messages with different levels of **urgency/warning/information**. This allows you to categorize log messages easily and makes your debugging life way easier.

3. You can set the destination of your logs to pretty much anything. **Even to sockets**.

4. Doesn’t tamper with the **user experience** if your module is being imported by other users.

So let’s dive into the world of logging in Python.

##### Levels of Logging
Now the logging module is already included in your default python installation. So just import logging and we are good to go. By default, you will find that there are 5 standard levels that indicates the severity of events. They are

1. debug (Level 10)
2. info (Level 20)
3. warning (Level 30)
4. error (Level 40)
5. critical (Level 50)

##### A simple example of Logging
Let’ see a basic implementation of Logging.
```python
# logging_guide.py
import logging

logging.debug("This is a debug message")
logging.info("This is an informational message")
logging.warning("Careful! Something does not look right")
logging.error("You have encountered an error")
logging.critical("You are in trouble")
```
When we run the above code, we get something like this.
```bash
WARNING:root:Careful! Something does not look right
ERROR:root:You have encountered an error
CRITICAL:root:You are in trouble
```
Notice how logs with **debug** and **info** didn’t get logged. This is because **warning** is the default level of logging. Any severity below warning is going to be ignored, unless we override the default level. To achieve that, we have to use the **basicconfig()** method in logging. In that method, we have to pass an argument called as level and set it to the **level** on which we would like to see our logs.
```python
# logging_guide.py
import logging

logging.basicConfig(level='DEBUG')

logging.debug("This is a debug message")
logging.info("This is an informational message")
logging.warning("Careful! Something does not look right")
logging.error("You have encountered an error")
logging.critical("You are in trouble")
```
When you run the above script, you will see that all the messages with severity level of debug and above are being logged. **Its that simple!**

##### Formatting our logs to have more information
Now the amount of information here is not sufficient. Didn’t I brag about the magical attributes of the logging module earlier? Well it is all true. If you check the [log record attributes page](https://docs.python.org/3/library/logging.html#logrecord-attributes) you can find a table of all the attribute names with their usable formats and descriptions that you can include in your logs. Let’s try to pick some of the important ones.

Let’s assume we are interested in having our logs with the following details.

1. The log message
2. Severity of the log message
3. Timestamp at which the message was logged
4. Name of the module where the event occured
5. Line no. of the module that registered the log

Let’s write a snippet to include these information. I am creating a variable called `log_format` and assigning it a string representation of how my log should look.
```python
# logging_guide.py
import logging

log_format = "%(asctime)s::%(levelname)s::%(name)s::"\
             "%(filename)s::%(lineno)d::%(message)s"
logging.basicConfig(level='DEBUG', format=log_format)

logging.debug("This is a debug message")
logging.info("This is an informational message")
logging.warning("Careful! Something does not look right")
logging.error("You have encountered an error")
logging.critical("You are in trouble")
```
The above snippet is going to return us all the attributes that we are interested to receive. The logs would look something like this.
```bash
2019-06-04 21:49:37,735::DEBUG::root::logging_guide.py::6::This is a debug message
2019-06-04 21:49:37,735::INFO::root::logging_guide.py::7::This is an informational message
2019-06-04 21:49:37,735::WARNING::root::logging_guide.py::8::Careful! Something does not look right
2019-06-04 21:49:37,735::ERROR::root::logging_guide.py::9::You have encountered an error
2019-06-04 21:49:37,735::CRITICAL::root::logging_guide.py::10::You are in trouble
```

All this time, have you been wondering what does `root` mean in the logs? Stay with that thought for a while, we will discuss it very soon.

##### Logging to a file
Usually logs have little purpose being printed to the console. You would ideally want to store them in a file. To do that you have to use the filename argument and set it to the filename or complete path of the filename of our choice. Everytime you run your application, the new logs are appended to the file.
```python
# logging_guide.py
import logging

log_format = "%(asctime)s::%(levelname)s::%(name)s::"\
             "%(filename)s::%(lineno)d::%(message)s"
logging.basicConfig(filename='mylogs.log', level='DEBUG', format=log_format)

logging.debug("This is a debug message")
logging.info("This is an informational message")
logging.warning("Careful! Something does not look right")
logging.error("You have encountered an error")
logging.critical("You are in trouble")
```
If you only want to have the latest logs in your logfile, you can use the **filemode** argument as well. That way new logs overwrite the existing logs everytime.
```python
# logging_guide.py
import logging

log_format = "%(asctime)s::%(levelname)s::%(name)s::"\
             "%(filename)s::%(lineno)d::%(message)s"
logging.basicConfig(filename='mylogs.log', filemode='w', level='DEBUG', format=log_format)

logging.debug("This is a debug message")
logging.info("This is an informational message")
logging.warning("Careful! Something does not look right")
logging.error("You have encountered an error")
logging.critical("You are in trouble")
```

##### Logging from multiple modules
Let’s say you are working on a project `project.py` and importing another module called `helper.py`. Both the files look something like this.
```python
# project.py

import logging
import helper

logging.basicConfig(level='DEBUG')

logging.debug("I am a debug log from project")
```
```python
# helper.py

import logging

logging.basicConfig(level='DEBUG')

logging.debug("I am a debug log from helper")
```

If you run `project.py`, you will notice the messages being logged in this way.
```bash
DEBUG:root:I am a debug log from helper
DEBUG:root:I am a debug log from project
```
Why in this order? Because when we import the `helper` module, we are running the code present inside it. The basicConfig method inside the helper module gets called first. The debug message is logged to the console and then the script inside `project.py` is executed.

Let’s try another experiment. Now in `project.py`, we would be adding the filename argument to log our messages to a file instead of console. `helper.py` remains the same.
```python
# project.py

import logging
import helper

logging.basicConfig(level='DEBUG', filename='mylogs.log')

logging.debug("I am a debug log from project")
```
Now we would expect the message from ```helper.py``` to to be logged to the console and the message from ```project.py``` to be logged to the file. But when you run the script, both the messages are logged to the console.
```bash
DEBUG:root:I am a debug log from helper
DEBUG:root:I am a debug log from project
```
This is because, when you import the helper module, the **basicConfig** method gets registered. Once the basicConfig method gets registered, it cannot be changed. You can confirm this by running two basicConfig methods in a python script.
```python
import logging

logging.basicConfig(level='DEBUG')
logging.basicConfig(level='DEBUG', filename='mylogs.log')

logging.debug("I won't be logged to any file")
```

So this is a problem. We are unable to log messages from two different modules to two different places. How can we solve it? 

Probably now is a good time to talk about the `root` aka **Root logger**. 
##### Root Logger

Python logging module has a hierarchy. **Root Logger** is at the top of the hierarchy. When you are using the `basicConfig` method, you are basically initalizing the Root logger. When you use the `name` logging attribute and it returns `root`, it means you are using the root logger. Once the root logger is initialized, you can not add any other logging method to your module. As we can see from the above example, it is not really a good idea to directly log against the Root logger. Instead we should create and configure logging entities that serve the logging requirements for every specific module. We can do that by configuring a **Main Logger**.

##### Configuring a Main Logger

Let's understand configuring a separate logger in general. We can configure a new logger by using the `getLogger(name)` method. The method expects a name for the logger, else it is going to take the root logger's name. It is always good practice to give it the modular name by using the `__name__` variable. This way the configured logger is always going to track the name of the module that creates a log and therefore easier to analyze later.
```python
# logging_guide.py

import logging

logger = logging.getLogger(__name__)

logger.debug("Trying to run this")
logger.warning("I am a separate Logger")
```

When you run the above snippet, you get result like this.
```bash
I am a separate Logger
```
By default, loggers have a severity level of **0**. So they always use the log level of the first parent logger unless the level is set specifically for the logger. The parent logger for the above configure logger is the **Root Logger**. So the debug level message doesn't get logged. 
But how come no other information is being shown? Where are the message level, logger name, timestamp and other relevant attributes? May be you also want to change the default logging level from warning to debug. How to do that?

With the `basicConfig()` method, the level name, the logger name and the message are shown as default to the user. However with configuring your own logger, you have to manually set these parameters. You do that through the **Handler** and **Formatter** objects. 

**Handler** objects are repsonsible for sending your logging message to the right destination. You can find a list of different types of available handlers [here](https://docs.python.org/3/howto/logging.html#useful-handlers). **Formatter** objects configure the structure and format of your log messages.

##### Some logging scenarios 
1. **Logging messages to file using FileHandler()**

    ```python
    # logging_guide.py

    import logging

    log_format = '%(asctime)s - %(name)s - %(levelname)s - %(message)s'
    logger = logging.getLogger(__name__)

    # To override the default severity of logging
    logger.setLevel('DEBUG')

    # Use FileHandler() to log to a file
    file_handler = logging.FileHandler("mylogs.log")
    formatter = logging.Formatter(log_format)
    file_handler.setFormatter(formatter)

    # Don't forget to add the file handler
    logger.addHandler(file_handler)
    logger.info("I am a separate Logger")
    ```
    Now you will se a log in `mylogs.log` like this.
    ```bash
    2019-06-05 17:43:07,889 - __main__ - INFO - I am a separate Logger
    ```

2. **Logging messages to the console using StreamHandler()**

    ```python
    # logging_guide.py

    import logging

    log_format = '%(asctime)s - %(name)s - %(levelname)s - %(message)s'
    logger = logging.getLogger(__name__)

    # To override the default severity of logging
    logger.setLevel('DEBUG')

    # Use FileHandler() to log to a file
    file_handler = logging.StreamHandler()
    formatter = logging.Formatter(log_format)
    file_handler.setFormatter(formatter)

    # Don't forget to add the file handler
    logger.addHandler(file_handler)
    logger.info("I am a separate Logger")
    ```
    Now you will see your log message being printed to the console. 

</ol>


##### Advantages of configuring a Main Logger
There is a huge advantage to configuring a Main Logger instead of using the Root Logger. Let us see that through an example. Let's go back to our old example of `project.py` and `helper.py`. However this time, instead of using the `basicConfig()` method, we will configure main loggers for both the files. This time also, we want to log the message from `project.py` to a file and the message from `helper.py` to the console.

```python
# project.py

import logging
import helper

log_format = '%(asctime)s - %(name)s - %(levelname)s - %(message)s'
logger = logging.getLogger(__name__)

# To override the default severity of logging
logger.setLevel('DEBUG')

# Use FileHandler() to log to a file
file_handler = logging.FileHandler("mylogs.log")
formatter = logging.Formatter(log_format)
file_handler.setFormatter(formatter)

# Don't forget to add the file handler
logger.addHandler(file_handler)
logger.info("I am a log from project")
```

```python
# helper.py

import logging

log_format = '%(asctime)s - %(name)s - %(levelname)s - %(message)s'
logger = logging.getLogger(__name__)

# To override the default severity of logging
logger.setLevel('DEBUG')

# Use FileHandler() to log to a file
file_handler = logging.StreamHandler()
formatter = logging.Formatter(log_format)
file_handler.setFormatter(formatter)

# Don't forget to add the file handler
logger.addHandler(file_handler)
logger.info("I am a log from helper")
```
When you execute `project.py`, only the log message from the helper module is logged to the console. The log from `project.py` is logged to the file you wanted to. Hurray !! 

Also notice one more thing! Look at the message logged from `helper.py`.
```bash
2019-06-05 18:02:32,901 - helper - INFO - I am a log from helper
```
The **name** attribute returns the actual file name from which the message was logged. Isn't that amazing? This will be super useful for debugging purposes as you can easily sort, filter and analyze your logs based on file names.

I hope you enjoyed this blog about the Python Logging module. It does need a learning curve to get used to the norms and functionalities. But once you understand the concept, this will be one of the most useful libraries that you know about.

If you have any questions, concerns, criticisms or opinions - **tweet to me @pylenin**
