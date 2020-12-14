---
title: "Web Scraping Wikipedia tables with Beautiful Soup"
description: "Use requests and Beautiful soup to extract data from wikipedia tables."
date: 2020-12-14T02:57:35+05:30
draft: false
image: /img/beautifulsoup/web-scraping-bs4.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

In this blog you will learn to perform Web Scraping using the Beautiful Soup and Requests in Python 3.

**How will you learn?**

You are going to scrape a Wikipedia table in order to fetch all the information, filter it(if necessary) and store them in a csv.

**Contents of this article**

1. [Benefits of Web Scraping](#benefits-of-web-scraping)
2. [Beautiful Soup vs Selenium vs Scrapy](#beautiful-soup-vs-selenium-vs-scrapy)
3. [Importance of DOM in Web Scraping](#importance-of-dom-in-web-scraping)
4. [Parsing HTML Table with Beautiful Soup](#parsing-html-table-with-beautiful-soup)
5. [Parsing headers from Wikipedia table](#parsing-headers-from-wikipedia-table)
6. [Parsing rows of data from Wikipedia table](#parsing-rows-of-data-from-wikipedia-table)
7. [Converting data into CSV](#converting-data-into-csv)
8. [Conclusion](#conclusion)

#### Benefits of Web Scraping

21st century is the age of Data. Every organization depends on minute analysis of various data sources in order to grow their business. 

With web scraping, one can accumulate tons of relevant data from various sources with a lot of ease, therefore, skipping on the manual effort. Real Estate Listings, Job listings, price tracking on ecommerce websites, stock market trends and many more - Web Scraping has become a go to tool for each of these objectives and much more.

#### Beautiful Soup vs Selenium vs Scrapy

When it comes to using Python for web scraping, there are 3 libraries that developers consider for their scraping pipeline.
They are **Beautiful Soup, Selenium or Scrapy**.

Each of these libraries has its pro and cons of its own. One should shoose the library that is best suited for their requirement.

The pros and cons of each of these libraries are described below.

<div align="center"><blockquote class="instagram-media" data-instgrm-captioned data-instgrm-permalink="https://www.instagram.com/p/CIudJTrguB7/?utm_source=ig_embed&amp;utm_campaign=loading" data-instgrm-version="13" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:540px; min-width:326px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:16px;"> <a href="https://www.instagram.com/p/CIudJTrguB7/?utm_source=ig_embed&amp;utm_campaign=loading" style=" background:#FFFFFF; line-height:0; padding:0 0; text-align:center; text-decoration:none; width:100%;" target="_blank"> <div style=" display: flex; flex-direction: row; align-items: center;"> <div style="background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 40px; margin-right: 14px; width: 40px;"></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 100px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 60px;"></div></div></div><div style="padding: 19% 0;"></div> <div style="display:block; height:50px; margin:0 auto 12px; width:50px;"><svg width="50px" height="50px" viewBox="0 0 60 60" version="1.1" xmlns="https://www.w3.org/2000/svg" xmlns:xlink="https://www.w3.org/1999/xlink"><g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"><g transform="translate(-511.000000, -20.000000)" fill="#000000"><g><path d="M556.869,30.41 C554.814,30.41 553.148,32.076 553.148,34.131 C553.148,36.186 554.814,37.852 556.869,37.852 C558.924,37.852 560.59,36.186 560.59,34.131 C560.59,32.076 558.924,30.41 556.869,30.41 M541,60.657 C535.114,60.657 530.342,55.887 530.342,50 C530.342,44.114 535.114,39.342 541,39.342 C546.887,39.342 551.658,44.114 551.658,50 C551.658,55.887 546.887,60.657 541,60.657 M541,33.886 C532.1,33.886 524.886,41.1 524.886,50 C524.886,58.899 532.1,66.113 541,66.113 C549.9,66.113 557.115,58.899 557.115,50 C557.115,41.1 549.9,33.886 541,33.886 M565.378,62.101 C565.244,65.022 564.756,66.606 564.346,67.663 C563.803,69.06 563.154,70.057 562.106,71.106 C561.058,72.155 560.06,72.803 558.662,73.347 C557.607,73.757 556.021,74.244 553.102,74.378 C549.944,74.521 548.997,74.552 541,74.552 C533.003,74.552 532.056,74.521 528.898,74.378 C525.979,74.244 524.393,73.757 523.338,73.347 C521.94,72.803 520.942,72.155 519.894,71.106 C518.846,70.057 518.197,69.06 517.654,67.663 C517.244,66.606 516.755,65.022 516.623,62.101 C516.479,58.943 516.448,57.996 516.448,50 C516.448,42.003 516.479,41.056 516.623,37.899 C516.755,34.978 517.244,33.391 517.654,32.338 C518.197,30.938 518.846,29.942 519.894,28.894 C520.942,27.846 521.94,27.196 523.338,26.654 C524.393,26.244 525.979,25.756 528.898,25.623 C532.057,25.479 533.004,25.448 541,25.448 C548.997,25.448 549.943,25.479 553.102,25.623 C556.021,25.756 557.607,26.244 558.662,26.654 C560.06,27.196 561.058,27.846 562.106,28.894 C563.154,29.942 563.803,30.938 564.346,32.338 C564.756,33.391 565.244,34.978 565.378,37.899 C565.522,41.056 565.552,42.003 565.552,50 C565.552,57.996 565.522,58.943 565.378,62.101 M570.82,37.631 C570.674,34.438 570.167,32.258 569.425,30.349 C568.659,28.377 567.633,26.702 565.965,25.035 C564.297,23.368 562.623,22.342 560.652,21.575 C558.743,20.834 556.562,20.326 553.369,20.18 C550.169,20.033 549.148,20 541,20 C532.853,20 531.831,20.033 528.631,20.18 C525.438,20.326 523.257,20.834 521.349,21.575 C519.376,22.342 517.703,23.368 516.035,25.035 C514.368,26.702 513.342,28.377 512.574,30.349 C511.834,32.258 511.326,34.438 511.181,37.631 C511.035,40.831 511,41.851 511,50 C511,58.147 511.035,59.17 511.181,62.369 C511.326,65.562 511.834,67.743 512.574,69.651 C513.342,71.625 514.368,73.296 516.035,74.965 C517.703,76.634 519.376,77.658 521.349,78.425 C523.257,79.167 525.438,79.673 528.631,79.82 C531.831,79.965 532.853,80.001 541,80.001 C549.148,80.001 550.169,79.965 553.369,79.82 C556.562,79.673 558.743,79.167 560.652,78.425 C562.623,77.658 564.297,76.634 565.965,74.965 C567.633,73.296 568.659,71.625 569.425,69.651 C570.167,67.743 570.674,65.562 570.82,62.369 C570.966,59.17 571,58.147 571,50 C571,41.851 570.966,40.831 570.82,37.631"></path></g></g></g></svg></div><div style="padding-top: 8px;"> <div style=" color:#3897f0; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:550; line-height:18px;"> View this post on Instagram</div></div><div style="padding: 12.5% 0;"></div> <div style="display: flex; flex-direction: row; margin-bottom: 14px; align-items: center;"><div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(0px) translateY(7px);"></div> <div style="background-color: #F4F4F4; height: 12.5px; transform: rotate(-45deg) translateX(3px) translateY(1px); width: 12.5px; flex-grow: 0; margin-right: 14px; margin-left: 2px;"></div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(9px) translateY(-18px);"></div></div><div style="margin-left: 8px;"> <div style=" background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 20px; width: 20px;"></div> <div style=" width: 0; height: 0; border-top: 2px solid transparent; border-left: 6px solid #f4f4f4; border-bottom: 2px solid transparent; transform: translateX(16px) translateY(-4px) rotate(30deg)"></div></div><div style="margin-left: auto;"> <div style=" width: 0px; border-top: 8px solid #F4F4F4; border-right: 8px solid transparent; transform: translateY(16px);"></div> <div style=" background-color: #F4F4F4; flex-grow: 0; height: 12px; width: 16px; transform: translateY(-4px);"></div> <div style=" width: 0; height: 0; border-top: 8px solid #F4F4F4; border-left: 8px solid transparent; transform: translateY(-4px) translateX(8px);"></div></div></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center; margin-bottom: 24px;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 224px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 144px;"></div></div></a><p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;"><a href="https://www.instagram.com/p/CIudJTrguB7/?utm_source=ig_embed&amp;utm_campaign=loading" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none;" target="_blank">A post shared by Pylenin (@pylenin)</a></p></div></blockquote> <script async src="//www.instagram.com/embed.js"></script></div>

#### Importance of DOM in Web Scraping

In order to scrape the necessary content, it is imperative that you understand **HTML DOM** properly.

The HTML DOM is an Object Model for HTML. It defines:

* HTML elements as objects
* Properties for all HTML elements
* Methods for all HTML elements
* Events for all HTML elements

When a web page is loaded, the browser creates a Document Object Model of the page.

An HTML page consists of different tags - `head`,`body`, `div`, `img`, `table` etc. We are interested in scraping the `table` tag of an HTML.

Let's dig deeper into the componenets of a `table` tag in HTML.

```html
<table>
  <thead>
    <tr>
      <th>Month</th>
      <th>Savings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>January</td>
      <td>$100</td>
    </tr>
    <tr>
      <td>February</td>
      <td>$80</td>
    </tr>
  </tbody>
</table>
```  

The above HTML code will generate the following table.

![Simple HTML Table](/img/beautifulsoup/HTML-table.PNG)

**Observe the following:-**

1. The entire table is defined within `<table>` tag.
2. Header resides in `<thead>` tag.
3. Data resides in `<tbody>` tag.
4. Each table row is defined within a `<tr>` tag.
5. Each table header is defined with a `<th>` tag. 
6. Each table data/cell is defined with a `<td>` tag.

Now using the above information, we can scrape our wikipedia tables.

#### Parsing HTML Table with Beautiful Soup

The first step involves scraping an entire Wikipedia page and then identifying the table that we would like to store as csv.

For this article, we will scrape all the [Tropical Cyclones of January, 2020](https://en.wikipedia.org/wiki/Tropical_cyclones_in_2020).

![Tropical Cyclones of January, 2020](/img/beautifulsoup/tropical-cyclones-january-2020.PNG)

**Step 1** - Make a `GET` request to the Wikipedia page and fetch all the content.

```python3
import requests as r

wiki_page_request = r.get("https://en.wikipedia.org/wiki/Tropical_cyclones_in_2020")
wiki_page_text = wiki_page_request.text
```

The `wiki_page_text` variable contains the content from the page.

**Step 2**

We will pass the content through Beautiful Soup. This should give us a BeautifulSoup object, which represents the document as a nested data structure.

```python3
from bs4 import BeautifulSoup
import requests as r

wiki_page_request = r.get("https://en.wikipedia.org/wiki/Tropical_cyclones_in_2020")
wiki_page_text = wiki_page_request.text

# New code below
soup = BeautifulSoup(wiki_page_text, 'html.parser')
```

Let's experiment with the `soup` variable which is a BeautifulSoup object.

```python3
soup.title
# <title>Tropical cyclones in 2020 - Wikipedia</title>

soup.title.name
# 'title'

soup.title.string
# 'Tropical cyclones in 2020 - Wikipedia'

soup.a
# <a id="top"></a>
```

This way you can interact with various elements of HTML using the Beautiful Soup object.

**Let's find our table that we want to scrape.**

```python3
"""This returns a list containing all
the tables in the HTML"""
soup.find_all('table')

""" How many tables are there in this HTML?"""
len(soup.find_all('table'))
#18
```

We are interested in the table with the caption `Tropical cyclones formed in January 2020`. Let's read that particular table.

```python3
# First remove Falsey values(None) if present
table_soup = soup.find_all('table')
filtered_table_soup = [table for table in table_soup if table.caption is not None]

required_table = None

for table in filtered_table_soup:
    if str(table.caption.string).strip() == 'Tropical cyclones formed in February 2020':
        required_table = table
        break    
```

We should be able to see the HTML for just the **Tropical Cyclones formed in 1 January, 2020** table in our `required_table` variable.

```html
<table class="wikitable sortable">
    <caption>Tropical cyclones formed in February 2020
    </caption>
    <tbody>
    <tr>
        <th width="5%">Storm name
        </th>
        <th width="15%">Dates active
        </th>
        <th width="10%">Max wind<br/>km/h (mph)
        </th>
        <th width="5%">Pressure<br/>(hPa)
        </th>
        <th width="30%">Areas affected
        </th>
        <th width="10%">Damage<br/>(<a class="mw-redirect" href="/wiki/USD" title="USD">USD</a>)
        </th>
        <th width="5%">Deaths
        </th>
        <th width="5%">Refs
        </th>
    </tr>
    <tr>
        <td><a class="mw-redirect" href="/wiki/2019-20_Australian_region_cyclone_season#Severe_Tropical_Cyclone_Damien"
               title="2019-20 Australian region cyclone season">Damien</a>
        </td>
        <td>February 2 ? 11
        </td>
        <td>165 (105)
        </td>
        <td>955
        </td>
        <td><a href="/wiki/Northern_Australia" title="Northern Australia">Northern Australia</a>, <a
                href="/wiki/Kimberley_(Western_Australia)" title="Kimberley (Western Australia)">Kimberley</a>
        </td>
        <td>$4.3 million
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_South_Pacific_cyclone_season#Severe_Tropical_Cyclone_Uesi"
               title="2019?20 South Pacific cyclone season">Uesi</a>
        </td>
        <td>February 3 ? 15
        </td>
        <td>120 (75)
        </td>
        <td>970
        </td>
        <td><a href="/wiki/Solomon_Islands" title="Solomon Islands">Solomon Islands</a>, <a href="/wiki/Vanuatu"
                                                                                            title="Vanuatu">Vanuatu</a>,
            <a href="/wiki/New_Caledonia" title="New Caledonia">New Caledonia</a>, <a href="/wiki/Lord_Howe_Island"
                                                                                      title="Lord Howe Island">Lord Howe
                Island</a>, <a href="/wiki/New_Zealand" title="New Zealand">New Zealand</a>, <a
                    href="/wiki/New_South_Wales" title="New South Wales">New South Wales</a>, <a
                    href="/wiki/South_East_Queensland" title="South East Queensland">South East Queensland</a>
        </td>
        <td>Minor
        </td>
        <td>1
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_South-West_Indian_Ocean_cyclone_season#Moderate_Tropical_Storm_Francisco"
               title="2019?20 South-West Indian Ocean cyclone season">Francisco</a>
        </td>
        <td>February 3 ? 15
        </td>
        <td>80 (50)
        </td>
        <td>994
        </td>
        <td><a href="/wiki/Madagascar" title="Madagascar">Madagascar</a>
        </td>
        <td>Minor
        </td>
        <td>1
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_Australian_region_cyclone_season#Tropical_Low_3"
               title="2019?20 Australian region cyclone season">TL</a>
        </td>
        <td>February 6 ? 8
        </td>
        <td>Unspecified
        </td>
        <td>1007
        </td>
        <td><a class="mw-redirect" href="/wiki/Cocos_Islands" title="Cocos Islands">Cocos Islands</a>
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_Australian_region_cyclone_season#Tropical_Low_4"
               title="2019?20 Australian region cyclone season">TL</a>
        </td>
        <td>February 13
        </td>
        <td>Unspecified
        </td>
        <td>1009
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_South-West_Indian_Ocean_cyclone_season#Intense_Tropical_Cyclone_Gabekile"
               title="2019?20 South-West Indian Ocean cyclone season">Gabekile</a>
        </td>
        <td>February 13 ? 17
        </td>
        <td>165 (105)
        </td>
        <td>950
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_South_Pacific_cyclone_season#Tropical_Disturbance_07F"
               title="2019?20 South Pacific cyclone season">07F</a>
        </td>
        <td>February 14 ? 21
        </td>
        <td>Unspecified
        </td>
        <td>998
        </td>
        <td><a href="/wiki/Tuvalu" title="Tuvalu">Tuvalu</a>, <a href="/wiki/American_Samoa" title="American Samoa">American
            Samoa</a>, <a href="/wiki/Tokelau" title="Tokelau">Tokelau</a>
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_Australian_region_cyclone_season#Tropical_Low_5"
               title="2019?20 Australian region cyclone season">TL</a>
        </td>
        <td>February 15 ? 17
        </td>
        <td>Unspecified
        </td>
        <td>1002
        </td>
        <td><a href="/wiki/Solomon_Islands" title="Solomon Islands">Solomon Islands</a>
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_South_Pacific_cyclone_season#Tropical_Disturbance_08F"
               title="2019?20 South Pacific cyclone season">08F</a>
        </td>
        <td>February 17 ? 18
        </td>
        <td>65 (40)
        </td>
        <td>994
        </td>
        <td><a href="/wiki/American_Samoa" title="American Samoa">American Samoa</a>, <a href="/wiki/Niue" title="Niue">Niue</a>
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_South_Pacific_cyclone_season#Tropical_Cyclone_Vicky"
               title="2019?20 South Pacific cyclone season">Vicky</a>
        </td>
        <td>February 19?22
        </td>
        <td>85 (50)
        </td>
        <td>988
        </td>
        <td><a href="/wiki/Samoan_Islands" title="Samoan Islands">Samoan Islands</a>, <a href="/wiki/Niue" title="Niue">Niue</a>
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_South_Pacific_cyclone_season#Tropical_Cyclone_Wasi"
               title="2019?20 South Pacific cyclone season">Wasi</a>
        </td>
        <td>February 21 ? 23
        </td>
        <td>85 (50)
        </td>
        <td>990
        </td>
        <td><a href="/wiki/Wallis_and_Futuna" title="Wallis and Futuna">Wallis and Futuna</a>, <a
                href="/wiki/Samoan_Islands" title="Samoan Islands">Samoan Islands</a>
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a href="/wiki/2019%E2%80%9320_Australian_region_cyclone_season#Tropical_Cyclone_Esther"
               title="2019?20 Australian region cyclone season">Esther</a>
        </td>
        <td>February 21 - March 5
        </td>
        <td>75 (45)
        </td>
        <td>988
        </td>
        <td><a href="/wiki/Far_North_Queensland" title="Far North Queensland">Far North Queensland</a>, <a
                href="/wiki/Northern_Territory" title="Northern Territory">Northern Territory</a>, <a
                href="/wiki/Kimberley_(Western_Australia)" title="Kimberley (Western Australia)">Kimberley</a>
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td><a class="mw-redirect"
               href="/wiki/2019-20_Australian_region_cyclone_season#Severe_Tropical_Cyclone_Ferdinand"
               title="2019-20 Australian region cyclone season">Ferdinand</a>
        </td>
        <td>February 22 ? March 4
        </td>
        <td>155 (100)
        </td>
        <td>960
        </td>
        <td><a href="/wiki/Lesser_Sunda_Islands" title="Lesser Sunda Islands">Lesser Sunda Islands</a>
        </td>
        <td>None
        </td>
        <td>None
        </td>
        <td>
        </td>
    </tr>
    </tbody>
</table>
```

#### Parsing headers from Wikipedia table

Let's move on to parsing the headers of the table.

As we had discussed earlier, each table header is defined with a `th` tag. So, we could just look up all the `th` elements within the `required_table`.

```python3
headers = [header.text.strip() for header in required_table.find_all('th')]
# ['Storm name', 'Dates active',
# 'Max windkm/h (mph)', 'Pressure(hPa)',
# 'Areas affected', 'Damage(USD)', 'Deaths', 'Refs']
```

Our variable `headers` is now a list containing all the header names.

#### Parsing rows of data from Wikipedia table

Let's now parse the rows containing the data. As discussed above, Each table data/cell is defined with a `<td>` tag and the entire row resides within a `tr` tag.

Now, we want to store every row as a list, so that it can be easily converted to a csv file. For this purpose, we will parse the `tr` tags and loop through each `tr` tag to find the `td` tag.

```python3
rows = []

# Find all `tr` tags
data_rows = required_table.find_all('tr')

for row in data_rows:
    value = row.find_all('td')
    beautified_value = [ele.text.strip() for ele in value]
    # Remove data arrays that are empty
    if len(beautified_value) == 0:
        continue
    rows.append(beautified_value)
```

Now our variable `rows` contains all the rows of the tables in a list format.

#### Converting data into CSV

Now that we have both our headers and the data rows, the only task that remains is to convert them to a CSV file.

```python3
import csv

with open('world_cyclones.csv', 'w', newline="") as output:
    writer = csv.writer(output)
    writer.writerow(headers)
    writer.writerows(rows)
```

#### Conclusion

Beautiful Soup has a lot of useful functionality to parse HTML data. It is user-friendly and has a well explained documentation. In fact, Beautiful Soup could help you with most of your parsing of the static websites.

In this article, you have learned how to scrape Wikipedia tables using Python, requests, and Beautiful Soup. You learned how to:

1. Inspect the DOM structure of Wikipedia tools.
2. Download the page HTML content using Python requests library with a `GET` request.
3. Parse the downloaded HTML with Beautiful Soup to extract relevant information.

To learn more about Python HTTP Methods, check out our [blog](https://www.pylenin.com/python-http-methods-tutorial).