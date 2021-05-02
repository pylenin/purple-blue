---
title: "Combining multiple Excel sheets into one in Python"
description: "Combine multiple Excel files into one using Openpyxl module in Python 3."
date: 2021-01-29T20:07:53+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Data Engineering with Python']
categories_weight: 2
tags: ["python excel", "openpyxl"]
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Prerequisites**

1. [Reading Excel data with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#reading-data-from-excel-using-openpyxl)
2. [Writing to Excel with Openpyxl](https://www.pylenin.com/blogs/excel-with-python/#writing-data-to-cells-in-excel-with-openpyxl)

Let's say you have a directory with multiple Excel files containing sales data of every month.

![A directory containing multiple Excel files](/img/excel-with-python/combining-wb-1.png)

**Objective** - You would like to store all those separate Excel files as separate sheets in one Excel sheet 
named **"yearly_sales.csv"**.

**Steps to achieve the objective**

1. Find the absolute path of the Excel files.
2. Iterate through each file and create a sheet of the same name in your destination file **"yearly_sales.xlsx"**.
3. Copy the data from the Excel file to the sheet.



#### Step 1 - Finding the absolute path of the Excel files

[There are multiple ways to find the absolute path of files in a directory in Python.](https://www.pylenin.com/python-examples/file-path-python/) For this article, we will use `os.walk()` function.

**Code**

```python3
import os

dir_containing_files = "C:\\Users\\91824\\PycharmProjects\\pythonProject\\sales_2020"

for root, dir, filenames in os.walk(dir_containing_files):
    for file in filenames:
        file_name = file.split('.')[0]
        # Absolute Path for Excel files
        file_path = os.path.abspath(os.path.join(root, file))
```



#### Step 2 - Creating sheets

First you need to create an Excel workbook - **"yearly_sales.xlsx"**.
Use the `file_name` from the above step to create new sheets in **"yearly_sales.xlsx"**.

**Code**

```python3
import os
#=====New Code====#
from openpyxl import Workbook
#=================#

dir_containing_files = "C:\\Users\\91824\\PycharmProjects\\pythonProject\\sales_2020"

#=====New Code====#
dest_wb = Workbook()
#=================#

for root, dir, filenames in os.walk(dir_containing_files):
    for file in filenames:
        file_name = file.split('.')[0]
        # Absolute Path for Excel files
        file_path = os.path.abspath(os.path.join(root, file))

        #=====New Code====#

        # Create new sheet in destination Workbook
        dest_wb.create_sheet(file_name)
        dest_ws = dest_wb[file_name]
        #=================#

#=====New Code====#
dest_wb.save("yearly_sales.xlsx")
#=================#
```



![Excel file containing all the sheets](/img/excel-with-python/combining-wb-2.png)

#### Step 3 - Copying data to sheets

The final step is to copy data from each of those Excel files 
to the newly created sheets in **"yearly_sales.xlsx"**.

**Code**

```python3
import os
from openpyxl import Workbook

#=====New Code====#
from openpyxl import load_workbook
#=================#

dir_containing_files = "C:\\Users\\91824\\PycharmProjects\\pythonProject\\sales_2020"

dest_wb = Workbook()

for root, dir, filenames in os.walk(dir_containing_files):
    for file in filenames:
        file_name = file.split('.')[0]
        # Absolute Path for Excel files
        file_path = os.path.abspath(os.path.join(root, file))

        # Create new sheet in destination Workbook
        dest_wb.create_sheet(file_name)
        dest_ws = dest_wb[file_name]

        # =====New Code====#

        # Read source data
        source_wb = load_workbook(file_path)
        source_sheet = source_wb.active
        for row in source_sheet.rows:
            for cell in row:
                dest_ws[cell.coordinate] = cell.value
        # =================#

dest_wb.save("yearly_sales.xlsx")
```

All the data should be copied to the sheets in **"yearly_sales.xlsx"**.



#### Related Reading

1. [Openpyxl Tutorial: Handling Excel sheets in Python](https://www.pylenin.com/blogs/excel-with-python/)
2. [Openpyxl - Plotting Bar Charts in Excel](https://www.pylenin.com/blogs/bar-charts-openpyxl)
3. [Openpyxl - Plotting Line Charts in Excel](https://www.pylenin.com/blogs/line-charts-openpyxl/)
4. [Openpyxl - Plotting Bubble Charts in Excel](https://www.pylenin.com/blogs/bubble-charts-openpyxl/)
5. [Openpyxl - Adding hyperlinks to cells in Excel](https://www.pylenin.com/blogs/adding-hyperlink-openpyxl/)