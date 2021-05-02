---
title: "Openpyxl - Adding hyperlinks to cells in Excel"
description: "Learn to add hyperlinks to cells in Excel using Openpyxl module in Python 3."
date: 2021-01-30T17:00:17+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Data Engineering with Python']
categories_weight: 6
tags: ["python excel", "openpyxl"]
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Prerequisites**

1. [Reading Excel data with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#reading-data-from-excel-using-openpyxl)
2. [Writing to Excel with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#writing-data-to-cells-in-excel-with-openpyxl)

Let's say you want to add a **hyperlink** to a certain cell in Excel. There are multiple ways to do that.

#### Method 1 - Excel built-in function

```bash
ws.cell(row=1, column=1).value = '=HYPERLINK("{}", "{}")'.format(link, "Link Name")

link - The url link to point
Link Name - The string to display
```

**Code**

```python3
from openpyxl import Workbook

wb = Workbook()
sheet = wb.active

# Add a hyperlink
sheet.cell(row=1, column=1).value = '=HYPERLINK("{}", "{}")'.format("https://www.google.com", "Check Google")

wb.save("hyperlink_example.xlsx")
```

**Output**

![Add Hyperlink with Openpyxl](/img/excel-with-python/hyperlink1.png)



#### Method 2 - Using `hyperlink` attribute

**Code**

```python3
from openpyxl import Workbook

wb = Workbook()
sheet = wb.active

# Add a hyperlink
sheet.cell(row=1, column=1).value = '=HYPERLINK("{}", "{}")'.format("https://www.google.com", "Check Google")

sheet.cell(row=2, column=1).hyperlink = "https://www.youtube.com/pylenin"
sheet.cell(row=2, column=1).value = "Pylenin Youtube Channel"
sheet.cell(row=2, column=1).style = "Hyperlink"

wb.save("hyperlink_example.xlsx")
```

**Output**

![Add Hyperlink with Openpyxl](/img/excel-with-python/hyperlink2.png)

You can see the difference between the 1st and 2nd Method. Setting the `style` attribute to `Hyperlink` has styled the cell in a way that **it appears like a link**.



#### Method 3 - Hyperlinking to a different Excel sheet in same Workbook

Assuming you have an Excel file named `hyperlink_example.xlsx` 
with two sheets named `Sheet1` and `Sheet2`.
You want to create an internal link from cell(A1) of `Sheet1` to another cell(A1) of `Sheet2` using Openpyxl.

Excel uses the `#` for same file links. You can use it to hyperlink to any cell of any sheet,

**Code**

```python3
from openpyxl import load_workbook

file_name = "hyperlink_example.xlsx"
wb = load_workbook(file_name) 
ws1 = wb.get_sheet_by_name("Sheet1")

# Create hyperlink to relevant cell
link = file_name+"#Sheet2!A1"

ws1.cell(row=1, column=1).hyperlink = link
ws1.cell(row=1, column=1).value = "Refer to Sheet 2 - Cell A1"
ws1.cell(row=1, column=1).style = "Hyperlink"

wb.save(file_name)
```

**Output**

![Add Hyperlink to another sheet with Openpyxl](/img/excel-with-python/hyperlink3.png)



#### Related Reading

1. [Openpyxl Tutorial: Handling Excel sheets in Python](https://www.pylenin.com/blogs/excel-with-python/)
2. [Openpyxl - Plotting Bar Charts in Excel](https://www.pylenin.com/blogs/bar-charts-openpyxl)
3. [Openpyxl - Plotting Line Charts in Excel](https://www.pylenin.com/blogs/line-charts-openpyxl/)
4. [Openpyxl - Plotting Bubble Charts in Excel](https://www.pylenin.com/blogs/bubble-charts-openpyxl/)
5. [Combining multiple Excel sheets into one in Python](https://www.pylenin.com/blogs/combining-workbooks-to-sheets/)