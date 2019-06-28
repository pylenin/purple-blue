---
title: "Python Web Scraping with Beautiful Soup (With Examples)"
description: "A complete python tutorial on performing web scraping with the Beautifulsoup library."
date: 2019-06-18T22:20:42+02:00
draft: true
image: /img/beautifulsoup/web-scraping-bs4.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

In this blog you will learn to perform Web Scraping using the Beautiful Soup library in Python 3.

**How will you learn?**

You are going to scrape the [Hacker News](https://news.ycombinator.com/) website in order to get a list of all articles on the front page with their respective author names and their upvote scores.

1) Installing Beautiful Soup
2) Writing your first scraper.
2) Understanding parsers
3) Creating a Soup
4) Understanding Beautiful Soup objects
5) Parsing the child elements
6) Parsing parent elements
7) Parsing siblings
8) Navigating trees through filters
9) find_all
10) 

##### Installing Beautiful Soup

Beautiful Soup helps you ectract relevant information from **HTML** and **XML** files. We are goign to work with the latest version of this library - **Beautiful Soup 4**.

1. Linux/Ubuntu users

   If your operating system is Linux or Ubuntu, you could install Beautiful Soup through the system package manager **apt-get**.

   ```bash
   sudo apt-get install python3-bs4
   ```

   If this doesn't work for you, you could also install it through **easy_install** or **pip**

   ```bash
   sudo easy_install beautifulsoup4

   OR

   pip install beautifulsoup4
   ```

2. Windows/Mac users

   If you are using Windows or Mac, you are probably used to installing all your packages through **pip**. You will use the same to install the Beautiful Soup 4 library.

   ```bash
   pip install beautifulsoup4
   ```
   
   If you have both Python 2 and 3 installed on your machine, use `pip3` to download the Python 3 compatible version.
   
   ```bash
   pip3 install beautifulsoup4
   ```

   There is no more point working with Python 2. Check out this [article](https://www.pylenin.com/blogs/10-benefits-of-switching-to-python-3/) to learn the benefits of switching from Python 3 to 2.


##### Writing your first scraper

Now that you have Beautiful Soup installed, it is time to write your first scrapper. We will make a `GET` request call to the Hacker News website using the **Requests** library in Python 3.

```python3
# first_scrapper.py

import requests

web_url = "https://news.ycombinator.com/"
r = requests.get(web_url)

print(r.status_code)
```

If you get `200` as the status code, it means your `GET` request call was successful. 

Let's now read the content that we parsed through this `GET` call. There are 2 ways to do this. We can use `r.text` or `r.content`. Now what is the difference between the 2? 

When you make a `GET`

When you print `r.text`, it will show you all the elements that have been scraped from the Hacker News page. Now don't get overwhelmed on seeing the result. You are scraping the whole page. It contains a lot of html elements. It is for the same reasons, I am not putting the entire result up here. But it looks somewhat like this.

```html
<html op="news"><head>Something ... Something</head>
```




