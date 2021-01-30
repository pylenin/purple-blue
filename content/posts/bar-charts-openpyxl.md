---
title: "Openpyxl - Plotting Bar Charts in Excel"
description: "Learn to plot Bar Charts in Excel with Openpyxl module in Python 3."
date: 2021-01-29T23:03:12+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Data Engineering with Python']
categories_weight: 3
tags: ["python excel", "openpyxl"]
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Prerequisites**
1. [Reading Excel data with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#reading-data-from-excel-using-openpyxl)
2. [Writing to Excel with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#writing-data-to-cells-in-excel-with-openpyxl)

Consider the data shown in the below image.

![MS Excel file - wb1.xlsx](/img/excel-with-python/wb1.png)

For plotting a Bar Chart on an Excel sheet, 
you have to use `BarChart` class from `openpyxl.chart` submodule.

#### Example 1 - Vertical Bar Charts

Vertical Bar charts are also kown as **Column Charts**.
Let's plot a Vertical Bar Chart for the quantities listed for every product.

**Code**

```python3
import openpyxl
from openpyxl.chart import BarChart, Reference

wb = openpyxl.load_workbook('wb1.xlsx')
sheet = wb.active

# Data for plotting
# Just take the data from last column
values = Reference(sheet,
                   min_col=4,
                   max_col=4,
                   min_row=1,
                   max_row=11)

cats = Reference(sheet, min_col=2, max_col=2, min_row=2, max_row=11)

# Create object of BarChart class
chart = BarChart()
chart.add_data(values, titles_from_data=True)
chart.set_categories(cats)

# set the title of the chart
chart.title = "Total Inventory"

# set the title of the x-axis
chart.x_axis.title = "Products"

# set the title of the y-axis
chart.y_axis.title = "Inventory per product"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb1.xlsx")
```

**Output**

![Bar Chat with Openpyxl](/img/excel-with-python/bar-chart-1.png)

By default, the size is 15 x 7.5 cm (approximately 5 columns by 14 rows). This can be changed by setting the anchor width and height properties of the chart.

```python3
import openpyxl
from openpyxl.chart import BarChart, Reference

wb = openpyxl.load_workbook('wb1.xlsx')
sheet = wb.active

# Data for plotting
# Just take the data from last column
values = Reference(sheet,
                   min_col=4,
                   max_col=4,
                   min_row=1,
                   max_row=11)

cats = Reference(sheet, min_col=2, max_col=2, min_row=2, max_row=11)

# Create object of BarChart class
chart = BarChart()
chart.height = 20
chart.width = 30
chart.add_data(values, titles_from_data=True)
chart.set_categories(cats)

# set the title of the chart
chart.title = "Total Inventory"

# set the title of the x-axis
chart.x_axis.title = "Products"

# set the title of the y-axis
chart.y_axis.title = "Inventory per product"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb1.xlsx")
```

![Bar Chat with Openpyxl](/img/excel-with-python/bar-chart-2.png)

#### Example 2 - Horiontal Bar Charts

You can switch between vertical and horizontal bar charts 
by setting `chart.type` to `col` or `bar` respectively. 
By default, it is set to `col` for vertical Bar Charts.

**Code**

```python3
import openpyxl
from openpyxl.chart import BarChart, Reference

wb = openpyxl.load_workbook('wb1.xlsx')
sheet = wb.active

# Data for plotting
# Just take the data from last column
values = Reference(sheet,
                   min_col=4,
                   max_col=4,
                   min_row=1,
                   max_row=11)

cats = Reference(sheet, min_col=2, max_col=2, min_row=2, max_row=11)

# Create object of BarChart class
chart = BarChart()
chart.type = 'bar'
chart.add_data(values, titles_from_data=True)
chart.set_categories(cats)

# set the title of the chart
chart.title = "Total Inventory"

# set the title of the x-axis
chart.x_axis.title = "Products"

# set the title of the y-axis
chart.y_axis.title = "Inventory per product"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb1.xlsx")
```

**Output**

![Horizontal Bar Chat with Openpyxl](/img/excel-with-python/bar-chart-3.png)

#### Example 3 - Stacked Bar Chart

Let's add one more row to our data - `Quantity Sold`.

![New Sales Data in Excel](/img/excel-with-python/bar-chart-4.png)

To create a stacked Bar chart, the overlap needs to be set to **100**.

**Code**

```python3
import openpyxl
from openpyxl.chart import BarChart, Reference

wb = openpyxl.load_workbook('wb1.xlsx')
sheet = wb.active

# Data for plotting
# Just take the data from last column
values = Reference(sheet,
                   min_col=4,
                   max_col=5,
                   min_row=1,
                   max_row=11)

cats = Reference(sheet, min_col=2, max_col=2, min_row=2, max_row=11)

# Create object of BarChart class
chart = BarChart()
chart.type = 'col'
chart.grouping = "stacked"
chart.overlap = 100
chart.add_data(values, titles_from_data=True)
chart.set_categories(cats)

# set the title of the chart
chart.title = "Total Inventory/Sales - Stacked"

# set the title of the x-axis
chart.x_axis.title = "Products"

# set the title of the y-axis
chart.y_axis.title = "Inventory/Sales data per product"

# the top-left corner of the chart
# is anchored to cell G2 .
sheet.add_chart(chart,"G2")

# save the file 
wb.save("wb1.xlsx")
```

**Output**

![Stacked Bar Chat with Openpyxl](/img/excel-with-python/bar-chart-5.png)

#### Example 4 - Percent Stacked Bar Chart

To draw Percentage Stacked Bar Charts with Openpyxl, use `percentStacked` grouping for your chart.

**Code**

```python3
import openpyxl
from openpyxl.chart import BarChart, Reference

wb = openpyxl.load_workbook('wb1.xlsx')
sheet = wb.active

# Data for plotting
# Just take the data from last column
values = Reference(sheet,
                   min_col=4,
                   max_col=5,
                   min_row=1,
                   max_row=11)

cats = Reference(sheet, min_col=2, max_col=2, min_row=2, max_row=11)

# Create object of BarChart class
chart = BarChart()
chart.type = 'col'
chart.grouping = "percentStacked"
chart.overlap = 100
chart.add_data(values, titles_from_data=True)
chart.set_categories(cats)

# set the title of the chart
chart.title = "Total Inventory/Sales - Stacked"

# set the title of the x-axis
chart.x_axis.title = "Products"

# set the title of the y-axis
chart.y_axis.title = "Inventory/Sales data per product"

# the top-left corner of the chart
# is anchored to cell G2 .
sheet.add_chart(chart,"G2")

# save the file 
wb.save("wb1.xlsx")
```

**Output**

![Percentage Stacked Bar Chat with Openpyxl](/img/excel-with-python/bar-chart-6.png)

#### Example 4 - 3D Bar Charts

To convert your Bar charts from 2D to **3D**, 
you need to use the `BarChart3D` class from 
`openpyxl.chart` submodule.

**Code**

```python3
import openpyxl
from openpyxl.chart import Reference, BarChart3D

wb = openpyxl.load_workbook('wb1.xlsx')
sheet = wb.active

# Data for plotting
# Just take the data from last column
values = Reference(sheet,
                   min_col=4,
                   max_col=4,
                   min_row=1,
                   max_row=11)

cats = Reference(sheet, min_col=2, max_col=2, min_row=2, max_row=11)

# Create object of BarChart class
chart = BarChart3D()

chart.add_data(values, titles_from_data=True)
chart.set_categories(cats)

# set the title of the chart
chart.title = "Total Inventory"

# set the title of the x-axis
chart.x_axis.title = "Products"

# set the title of the y-axis
chart.y_axis.title = "Inventory per product"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb1.xlsx")
```

**Output**

![3D Bar Chat with Openpyxl](/img/excel-with-python/bar-chart-7.png)

#### Related Reading

1. [Openpyxl Tutorial: Handling Excel sheets in Python](https://www.pylenin.com/blogs/excel-with-python/)
2. [Combining multiple Excel sheets into one in Python](https://www.pylenin.com/blogs/combining-workbooks-to-sheets/)