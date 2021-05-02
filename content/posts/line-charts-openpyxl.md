---
title: "Openpyxl - Plotting Line Charts in Excel"
description: "Learn to plot Line Charts in Excel with Openpyxl module in Python 3."
date: 2021-01-30T10:50:32+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Data Engineering with Python']
categories_weight: 5
tags: ["python excel", "openpyxl"]
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Prerequisites**

1. [Reading Excel data with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#reading-data-from-excel-using-openpyxl)
2. [Writing to Excel with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#writing-data-to-cells-in-excel-with-openpyxl)

#### Example 1

Consider the data shown in the below image.

![MS Excel file - wb2.xlsx](/img/excel-with-python/line-chart-1.png)

Let's plot the value of each stock against the date provided.

**Code**

```python3
import openpyxl
from openpyxl.chart import Reference, LineChart, Series

wb = openpyxl.load_workbook('wb2.xlsx')
sheet = wb.active

# Data for plotting
# Choose all the data from Column 2 to 4
values = Reference(sheet,
                   min_col=2,
                   max_col=4,
                   min_row=1,
                   max_row=11)

# Create object of LineChart class
chart = LineChart()
chart.add_data(values, titles_from_data=True)
# set the title of the chart
chart.title = "Analysis Stock prices"
# set the title of the x-axis
chart.x_axis.title = "Date"

# set the title of the y-axis
chart.y_axis.title = "Stock Value"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb2.xlsx")
```

**Output**

![Line Charts in Excel with Openpyxl](/img/excel-with-python/line-chart-2.png)



You won't be able to see dates in the X axis. 
In order to see the dates, you have to use the `DateAxis` class 
from `openpyxl.chart.axis` submodule.

**Code**

```python3
import openpyxl
from openpyxl.chart import Reference, LineChart
from openpyxl.chart.axis import DateAxis

wb = openpyxl.load_workbook('wb2.xlsx')
sheet = wb.active

# Data for plotting
values = Reference(sheet,
                   min_col=2,
                   max_col=4,
                   min_row=1,
                   max_row=11)

# Create object of LineChart class
chart = LineChart()
chart.add_data(values, titles_from_data=True)
dates = Reference(sheet, min_col=1, min_row=2, max_row=11)
chart.set_categories(dates)
chart.y_axis.crossAx = 500

# Use DateAxis class for X axis 
chart.x_axis = DateAxis(crossAx=100)
chart.x_axis.number_format = 'd-mmm'
chart.x_axis.majorTimeUnit = "days"

# set the title of the chart
chart.title = "Analysis Stock prices"
# set the title of the x-axis
chart.x_axis.title = "Date"


# set the title of the y-axis
chart.y_axis.title = "Stock Value"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb2.xlsx")
```

**Output**

![Line Charts in Excel with Openpyxl](/img/excel-with-python/line-chart-3.png)



#### Example 2 - Adding markers and different styles to Line Charts

In order to add markers and other styling options (like dotted line), 
you have to exploit various attributes of the `LineChart` class
 like `marker.symbol` and `graphicalProperties.line`.

**Code**

```python3
import openpyxl
from openpyxl.chart import Reference, LineChart, Series

wb = openpyxl.load_workbook('wb2.xlsx')
sheet = wb.active

# Data for plotting
# Choose all the data from Column 2 to 4
values = Reference(sheet,
                   min_col=2,
                   max_col=4,
                   min_row=1,
                   max_row=11)

# Create object of LineChart class
chart = LineChart()
chart.add_data(values, titles_from_data=True)

# Create marker and style for 1st series
s1 = chart.series[0]
s1.marker.symbol = "triangle"
s1.marker.graphicalProperties.solidFill = "FF0000" # Marker filling
s1.marker.graphicalProperties.line.solidFill = "FF0000" # Marker outline

# Create marker and style for 2nd series
s2 = chart.series[1]
s2.graphicalProperties.line.solidFill = "00AAAA"
s2.graphicalProperties.line.dashStyle = "sysDot"
s2.graphicalProperties.line.width = 100050 # width in EMUs

# Create marker and style for 3rd series
s3 = chart.series[2]
s3.smooth = True

# set the title of the chart
chart.title = "Analysis Stock prices"
# set the title of the x-axis
chart.x_axis.title = "Date"

# set the title of the y-axis
chart.y_axis.title = "Stock Value"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb2.xlsx")
```

**Output**

![Adding Markers and styling to Line Charts with Openpyxl](/img/excel-with-python/line-chart-4.png)



#### Example 3 - Line Chart 3D

To plot line charts in 3D, you need to use `LineChart3D` class in Openpyxl.

**Code**

```python3
from openpyxl import load_workbook
from openpyxl.chart import (
    LineChart3D,
    Reference,
)
from openpyxl.chart.axis import DateAxis

wb = load_workbook('wb2.xlsx')
sheet = wb.active

# Data for plotting
# Choose all the data from Column 2 to 4
values = Reference(sheet,
                   min_col=2,
                   max_col=4,
                   min_row=1,
                   max_row=11)

# Create object of LineChart3D class
chart = LineChart3D()
chart.add_data(values, titles_from_data=True)

# set the title of the chart
chart.title = "Analysis Stock prices"
# set the title of the x-axis
chart.x_axis.title = "Date"

# set the title of the y-axis
chart.y_axis.title = "Stock Value"

# the top-left corner of the chart
# is anchored to cell F2 .
sheet.add_chart(chart,"F2")

# save the file 
wb.save("wb2.xlsx")
```



**Output**

![3D Line Charts in Excel with Openpyxl](/img/excel-with-python/line-chart-5.png)

#### Related Reading

1. [Openpyxl Tutorial: Handling Excel sheets in Python](https://www.pylenin.com/blogs/excel-with-python/)
2. [Combining multiple Excel sheets into one in Python](https://www.pylenin.com/blogs/combining-workbooks-to-sheets/)
3. [Openpyxl - Plotting Bubble Charts in Excel](https://www.pylenin.com/blogs/bubble-charts-openpyxl/)
4. [Openpyxl - Plotting Bar Charts in Excel](https://www.pylenin.com/blogs/bar-charts-openpyxl/)
5. [Openpyxl - Adding hyperlinks to cells in Excel](https://www.pylenin.com/blogs/adding-hyperlink-openpyxl/)