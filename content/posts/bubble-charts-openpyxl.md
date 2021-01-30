---
title: "Openpyxl - Plotting Bubble Charts in Excel"
description: "Learn to plot Bubble Charts in Excel with Openpyxl module in Python 3."
date: 2021-01-30T08:51:57+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Data Engineering with Python']
categories_weight: 4
tags: ["python excel", "openpyxl"]
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Prerequisites**

1. [Reading Excel data with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#reading-data-from-excel-using-openpyxl)
2. [Writing to Excel with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#writing-data-to-cells-in-excel-with-openpyxl)

A Bubble chart is similar a Scatter chart **except**, 
the data points are replaced with bubbles 
and an additional dimension of the data is represented 
in the size of the bubbles.

Consider the data shown in the below image.

![MS Excel file - wb1.xlsx](/img/excel-with-python/bubble-chart-1.png)

Let's plot the `Total Cost` per product with `cost per unit` as the size of the Bubble.

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

**Code**

```python3
import openpyxl
from openpyxl.chart import Reference, BubbleChart, Series

wb = openpyxl.load_workbook('wb1.xlsx')
sheet = wb.active

# Data for plotting
# Just take the data from last column
xvalues = Reference(sheet,
                   min_col=2,
                   max_col=2,
                   min_row=2,
                   max_row=11)
yvalues = Reference(sheet,
                   min_col=5,
                   max_col=5,
                   min_row=2,
                   max_row=11)

size = Reference(sheet,
                 min_col=3,
                 max_col=3,
                 min_row=2,
                 max_row=11)

# Create object of BarChart class
chart = BubbleChart()
series = Series(values=yvalues, xvalues=xvalues, zvalues=size)
chart.series.append(series)
# set the title of the chart
chart.title = "Cost Analysis of Products"
chart.style = 18 # use a preset style
# set the title of the x-axis
chart.x_axis.title = "Products"

# set the title of the y-axis
chart.y_axis.title = "Total Cost Per Product"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb1.xlsx")
```

**Output**

![Bubble Chart in Excel with Openpyxl](/img/excel-with-python/bubble-chart-2.png)

Since the type of x and y axis is declared `NumericType` in the `BubbleChart` class, **you cannot set the product name (or any Text based label) for any axis.**

#### Related Reading

1. [Openpyxl Tutorial: Handling Excel sheets in Python](https://www.pylenin.com/blogs/excel-with-python/)
2. [Combining multiple Excel sheets into one in Python](https://www.pylenin.com/blogs/combining-workbooks-to-sheets/)
3. [Openpyxl - Plotting Bar Charts in Excel](https://www.pylenin.com/blogs/bar-charts-openpyxl/)
