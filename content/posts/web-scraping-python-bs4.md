---
title: "Web Scraping Wikipedia tables with Beautiful Soup"
description: "Use requests and Beautiful soup to extract data from wikipedia tables."
date: 2020-12-12T19:57:35+05:30
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

When it comes to using Python for web scraping, there are 3 libraries that developers consider to develop their scraping pipeline.
They are **Beautiful Soup, Selenium or Scrapy**.

Each of these libraries has pro and cons of its own. One should shoose the library that is best suited for their requirement.

The pros and cons of each of these libraries are described below.

![Beautiful Soup vs Selenium vs Scrapy](/img/beautifulsoup/web-scraping-options.png)

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
data_rows = table_body.find_all('tr')

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
with open('world_cyclones.csv', 'w', newline="") as output:
    writer = csv.writer(output)
    writer.writerow(headers)
    writer.writerows(rows)
```

#### Conclusion

Beautiful Soup has a lot of useful functionality to parse HTML data. It’s user-friendly and has a well explained documentation. In fact, Beautiful Soup could help you with most of your parsing of the static websites.

In this article, you’ve learned how to scrape Wikipedia tables using Python, requests, and Beautiful Soup. You learned how to:

1. Inspect the DOM structure of Wikipedia tools.
2. Download the page’s HTML content using Python’s requests library with a `GET` request.
3. Parse the downloaded HTML with Beautiful Soup to extract relevant information.

To learn more about Python HTTP Methods, check out our [blog](https://www.pylenin.com/python-http-methods-tutorial).