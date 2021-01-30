---
title: "Openpyxl tutorial: Handling Excel sheets in Python"
description: "Automate your Excel workflow by using Openpyxl module in Python 3."
date: 2021-01-24T20:27:00+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Data Engineering with Python']
categories_weight: 1
tags: ["python excel", "openpyxl"]
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

**Microsoft Excel** is probably one of the highly used data storage applications. A huge proportion of small to medium size businesses fulfill their analytics requirement using Excel.

However, analyzing huge amount of data in Excel can become highly tedious and time-consuming. You could build customized data processing and analytics application using **Visual Basic(VBA)**, the language that powers the Excel sheets. However, learning VBA could be difficult and perhaps, not worth it.

However, if you have a little knowledge of Python, you could build highly professional Business Intelligence using Excel data, without the need of a database. Using Python with Excel could be a game changer for your business.

### Sections Covered

1. [Basic Information about Excel](#basic-information-about-excel)
2. [What is Openpyxl and how to install it?](#what-is-openpyxl-and-how-to-install-it)
3. [Reading data from Excel using Openpyxl](#reading-data-from-excel-using-openpyxl)
4. [Reading multiple cells from Excel](#reading-multiple-cells-from-excel)
5. [Find the max row and column number with Openpyxl](#find-the-max-row-and-column-number-with-openpyxl)
5. [iter_rows() and iter_cols() in Openpyxl](#iter_rows-and-iter_cols-in-openpyxl)
6. [Create a new Excel file with Openpyxl](#create-a-new-excel-file-with-openpyxl)
7. [Writing data to cells in Excel with Openpyxl](#writing-data-to-cells-in-excel-with-openpyxl)
8. [Appending data to Excel with Openpyxl](#appending-data-to-excel-with-openpyxl)   
9. [Manipulating Sheets in Openpyxl](#manipulating-sheets-in-openpyxl)
10. [Practical usage example of Openpyxl](#practical-usage-example-of-openpyxl)

### Basic Information about Excel

Before beginning this Openpyxl tutorial, you need to keep the following details in mind.

1. Excel files are called **Workbooks**.
2. Each Workbook can contain **multiple sheets**.
3. Every sheet consists of rows starting from **1** and columns starting from **A**.
4. Rows and columns together make up a **cell**. 
5. Any type of data can be stored.

### What is Openpyxl and how to install it?

The Openpyxl module in Python is used to handle Excel files 
without involving third-party Microsoft application software. Openpyxl is arguably, the best python excel library that allows you to perform various Excel operations and automate excel reports using Python.
You can perform all kinds of tasks using Openpyxl like:-

1. Reading data 
2. Writing data 
3. Editing Excel files 
4. Drawing graphs and charts 
5. Working with multiple sheets
6. Sheet Styling etc.

You can install Openpyxl module by using the following command.

```bash
pip install openpyxl
```

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

### Reading data from Excel using Openpyxl

Let's import an Excel file named `wb1.xlsx` in Python using Openpyxl module~~~~. It has the following data as shown in the image below.

![MS Excel file - wb1.xlsx](/img/excel-with-python/wb1.png)

1. Import the `load_workbook` method from Openpyxl.

   ```python3
   from openpyxl import load_workbook
   ```
   
2. Provide the file location for the Excel file you want to open in Python.

   ```python3
   wb = load_workbook('wb1.xlsx')
   ```
   In this example, **the Excel file is present in the same directory as the python file**. Hence, there is no need to provide to entire file location.

3. Choose the first active sheet present in the workbook using `wb.active` attribute.

   ```python3
   sheet = wb.active
   ```
   
The above points are a standard way of accessing Excel sheets using Python. You will see them being used multiple times through out this article.

**Let's read all the data present in Row 1(header row).**

#### Method 1 - Reading data through cell name in Excel

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

print(sheet["A1"].value)
print(sheet["B1"].value)
print(sheet["C1"].value)
print(sheet["D1"].value)
```

**Output**

```bash
ProductId
ProductName
Cost per Unit
Quantity
```

#### Method 2 - Reading data from Excel using `cell()` method

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

print(sheet.cell(row=1, column=1).value)
print(sheet.cell(row=1, column=2).value)
print(sheet.cell(row=1, column=3).value)
print(sheet.cell(row=1, column=4).value)
```

**Output**

```bash
ProductId
ProductName
Cost per Unit
Quantity
```

### Reading Multiple Cells from Excel

You can also read multiple cells from an Excel workbook.
Let's understand this through various examples. 
Refer to the image of the `wb1.xlsx` file above for clarity.

#### Method 1 - Reading a range of cells in Excel using cell names

To read the data from a specific range of cells in your Excel sheet, you need to slice your sheet object through both the cells.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all cells from A1 to D11
print(sheet["A1:D11"])
```

**Output**

```bash
((<Cell 'Sheet1'.A1>, <Cell 'Sheet1'.B1>, <Cell 'Sheet1'.C1>, <Cell 'Sheet1'.D1>), 
 (<Cell 'Sheet1'.A2>, <Cell 'Sheet1'.B2>, <Cell 'Sheet1'.C2>, <Cell 'Sheet1'.D2>), 
 (<Cell 'Sheet1'.A3>, <Cell 'Sheet1'.B3>, <Cell 'Sheet1'.C3>, <Cell 'Sheet1'.D3>), 
 (<Cell 'Sheet1'.A4>, <Cell 'Sheet1'.B4>, <Cell 'Sheet1'.C4>, <Cell 'Sheet1'.D4>), 
 (<Cell 'Sheet1'.A5>, <Cell 'Sheet1'.B5>, <Cell 'Sheet1'.C5>, <Cell 'Sheet1'.D5>), 
 (<Cell 'Sheet1'.A6>, <Cell 'Sheet1'.B6>, <Cell 'Sheet1'.C6>, <Cell 'Sheet1'.D6>), 
 (<Cell 'Sheet1'.A7>, <Cell 'Sheet1'.B7>, <Cell 'Sheet1'.C7>, <Cell 'Sheet1'.D7>), 
 (<Cell 'Sheet1'.A8>, <Cell 'Sheet1'.B8>, <Cell 'Sheet1'.C8>, <Cell 'Sheet1'.D8>), 
 (<Cell 'Sheet1'.A9>, <Cell 'Sheet1'.B9>, <Cell 'Sheet1'.C9>, <Cell 'Sheet1'.D9>), 
 (<Cell 'Sheet1'.A10>, <Cell 'Sheet1'.B10>, <Cell 'Sheet1'.C10>, <Cell 'Sheet1'.D10>), 
 (<Cell 'Sheet1'.A11>, <Cell 'Sheet1'.B11>, <Cell 'Sheet1'.C11>, <Cell 'Sheet1'.D11>))
```

You can see that by slicing the `sheet` data from `A1:D11`, it returned us tuples of row data inside a tuple. In order to read the values of every cell returned, you can iterate over each row and use `.value`.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all cells from A1 to D11
for row in sheet["A1:D11"]:
    print ([x.value for x in row])
```

**Output**

```bash
['ProductId', 'ProductName', 'Cost per Unit', 'Quantity']
[1, 'Pencil', '$0.5', 200]
[2, 'Pen', '$1', 500]
[3, 'Eraser', '$0.25', 100]
[4, 'Sharpner', '$0.75', 100]
[5, 'Files', '$3', 50]
[6, 'A4 Size Paper', '$9', 10]
[7, 'Pencil Box', '$12', 20]
[8, 'Pen Stand', '$5.5', 10]
[9, 'Notebook', '$2', 50]
[10, 'Marker', '$1', 75]
```

#### Method 2 - Reading a single row in Excel using cell name

To read a single row in your Excel sheet, just access the single row number from your `sheet` object.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all cells in row 1
for data in sheet["1"]:
    print(data.value)
```

**Output**

```bash
ProductId
ProductName
Cost per Unit
Quantity
```

#### Method 3 - Reading all rows in Excel using `rows` attribute

To read all the rows, use `sheet.rows` to iterate over rows with Openpyxl. You receive a tuple element per row by using the `sheet.rows` attribute.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all cells in row 1
for row in sheet.rows:
    print([data.value for data in row])
```

**Output**

```bash
['ProductId', 'ProductName', 'Cost per Unit', 'Quantity']
[1, 'Pencil', '$0.5', 200]
[2, 'Pen', '$1', 500]
[3, 'Eraser', '$0.25', 100]
[4, 'Sharpner', '$0.75', 100]
[5, 'Files', '$3', 50]
[6, 'A4 Size Paper', '$9', 10]
[7, 'Pencil Box', '$12', 20]
[8, 'Pen Stand', '$5.5', 10]
[9, 'Notebook', '$2', 50]
[10, 'Marker', '$1', 75]
```

#### Method 4 - Reading a single column in Excel using cell name

Similar to reading a single row, you can read the data in a single column of your Excel sheet by its alphabet.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all cells in column A
for data in sheet["A"]:
    print(data.value)
```

**Output**

```bash
ProductId
1
2
3
4
5
6
7
8
9
10
```

#### Method 5 - Reading all the columns in Excel using `columns` attribute

To read all the data as a tuple of the columns in your Excel sheet, use `sheet.columns` attribute to iterate over all columns with Openpyxl.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all columns
for col in sheet.columns:
    print([data.value for data in col])
```

**Output**

```bash
['ProductId', 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
['ProductName', 'Pencil', 'Pen', 'Eraser', 'Sharpner', 'Files', 'A4 Size Paper', 'Pencil Box', 'Pen Stand', 'Notebook', 'Marker']
['Cost per Unit', '$0.5', '$1', '$0.25', '$0.75', '$3', '$9', '$12', '$5.5', '$2', '$1']
['Quantity', 200, 500, 100, 100, 50, 10, 20, 10, 50, 75]
```

#### Method 6 - Reading all the data in Excel

To read **all the data** present in your Excel sheet, you don't need to index the `sheet` object. You can just iterate over it.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all cells in Excel
for row in sheet:
    print([data.value for data in row])
```

**Output**

```bash
['ProductId', 'ProductName', 'Cost per Unit', 'Quantity']
[1, 'Pencil', '$0.5', 200]
[2, 'Pen', '$1', 500]
[3, 'Eraser', '$0.25', 100]
[4, 'Sharpner', '$0.75', 100]
[5, 'Files', '$3', 50]
[6, 'A4 Size Paper', '$9', 10]
[7, 'Pencil Box', '$12', 20]
[8, 'Pen Stand', '$5.5', 10]
[9, 'Notebook', '$2', 50]
[10, 'Marker', '$1', 75]
```

### Find the max row and column number with Openpyxl

To find the max row and column number in your Excel sheet, use `sheet.max_row` and `sheet.max_column` attributes.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

print(f"Max row in the active sheet is {sheet.max_row}")
print(f"Max column in the active sheet is {sheet.max_column}")
```

**Output**

```bash
Max row in the active sheet is 11
Max column in the active sheet is 4
```

**Note** - If you update a cell wih a value, the `sheet.max_row` and `sheet.max_column` values also change, even though you haven't saved your changes.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('pylenin.xlsx')

sheet = wb.active

sheet["A1"].value = "Lenin"
print(sheet.max_row)

sheet["A2"].value = "Mishra"
print(sheet.max_row)

# wb.save('pylenin.xlsx')
```

**Output**

```bash
1
2
```

### iter_rows() and iter_cols() in Openpyxl

Openpyxl offers two commonly used methods to iterate over rows and column.

1. `iter_rows()` - Returns one tuple element **per row selected**.
2. `iter_cols()` - Returns one tuple element **per column selected**.

Both the above mentioned methods can receive the following arguments for setting boundaries for iteration:

* min_row
* max_row
* min_col
* max_col

#### Example 1 - `iter_rows()`

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all cells from between 
# "Row 1 and Row 2" and "Column 1 and Column 3"
for row in sheet.iter_rows(min_row=1,
                           max_row=2,
                           min_col=1,
                           max_col=3):
    print([data.value for data in row])
```

**Output**

```bash
['ProductId', 'ProductName', 'Cost per Unit']
[1, 'Pencil', '$0.5']
```

As you can see, only the first 3 columns of the first 2 rows are returned. **The tuples are row based.**

**You can also choose to not pass in some or any arguments in `iter_rows` method.**

**Code** - Not passing min_col and max_col

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# min_col and max_col arguments are not provided
for row in sheet.iter_rows(min_row=1,
                           max_row=2):
    print([data.value for data in row])
```

**Output**

```bash
['ProductId', 'ProductName', 'Cost per Unit', 'Quantity']
[1, 'Pencil', '$0.5', 200]
```

All the columns from the first 2 rows are being printed.

> **What happens if you don't pass in any arguments? Comment below.**

#### Example 2 - `iter_cols()`

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Access all cells from A1 to D11
for row in sheet.iter_cols(min_row=1,
                           max_row=2,
                           min_col=1,
                           max_col=3):
    print([data.value for data in row])
```

**Output**

```bash
['ProductId', 1]
['ProductName', 'Pencil']
['Cost per Unit', '$0.5']
```

**The tuples returned are column based on using `iter_cols()` method.**

**You can also choose to not pass in some or any arguments in `iter_cols()` method.** 

**Code** - Not passing any argument

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# min_col and max_col arguments are not provided
for row in sheet.iter_cols():
    print([data.value for data in row])
```

**Output**

```bash
['ProductId', 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
['ProductName', 'Pencil', 'Pen', 'Eraser', 'Sharpner', 'Files', 'A4 Size Paper', 'Pencil Box', 'Pen Stand', 'Notebook', 'Marker']
['Cost per Unit', '$0.5', '$1', '$0.25', '$0.75', '$3', '$9', '$12', '$5.5', '$2', '$1']
['Quantity', 200, 500, 100, 100, 50, 10, 20, 10, 50, 75]
```

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

### Create a new Excel file with Openpyxl

To create a new Excel file with Openpyxl, you need to import the `Workbook` class.

**Code**

```python3
from openpyxl import Workbook

wb = Workbook()
sheet = wb.active

sheet['A1'] = "Pylenin"
sheet['B1'] = "loves"
sheet['C1'] = "Python"

wb.save("pylenin.xlsx")
```

This should create a new Excel workbook called `pylenin.xlsx` with the provided data.

![Create new Excel file with Openpyxl](/img/excel-with-python/wb2-pylenin.png)

### Writing data to cells in Excel with Openpyxl

There are multiple ways to write data to an Excel file using Openpyxl.

#### Method 1 - Writing data to Excel using cell names

**Code**

```python3
from openpyxl import Workbook

wb = Workbook()
sheet = wb.active

sheet['A1'] = "Pylenin"
sheet['B1'] = "loves"
sheet['C1'] = "Python"

wb.save("pylenin.xlsx")
```

**Output**

![Writing data to Excel with Openpyxl - Method 1](/img/excel-with-python/wb2-pylenin.png)

#### Method 2 - Writing data to Excel using the `cell()` method

**Code**

```python3
from openpyxl import Workbook

wb = Workbook()
sheet = wb.active

sheet.cell(row=1, column=1).value = "Pylenin"
sheet.cell(row=1, column=2).value = "loves"
sheet.cell(row=1, column=3).value = "Python"

wb.save("pylenin.xlsx")
```

**Output**

![Writing data to Excel with Openpyxl - Method 1](/img/excel-with-python/wb2-pylenin.png)

#### Method 3 - Writing data to Excel by iterating over rows

**Code - Example 1**

```python3
from openpyxl import Workbook

wb = Workbook()
sheet = wb.active

for row in sheet["A1:D3"]:
    row[0].value = "Pylenin"
    row[1].value = "loves"
    row[2].value = "Python"

wb.save("pylenin.xlsx")
```

**Output**

![Writing data to Excel with Openpyxl through iteration - Example 1](/img/excel-with-python/wb3-pylenin.png)

You can also use methods like `iter_rows()` and `iter_cols()` to write data to Excel.

**Code - Example 2 - using `iter_rows()` method**

```python3
from openpyxl import Workbook

wb = Workbook()
sheet = wb.active

for row in sheet.iter_rows(min_row=1,
                           max_row=3,
                           min_col=1,
                           max_col=3):
    row[0].value = "Pylenin"
    row[1].value = "loves"
    row[2].value = "Python"

wb.save("pylenin.xlsx")
```

**Output**

![Writing data to Excel with Openpyxl through iteration - Example 2](/img/excel-with-python/wb3-pylenin.png)

**Code - Example 3 - using `iter_cols()` method**

```python3
from openpyxl import Workbook

wb = Workbook()
sheet = wb.active

for col in sheet.iter_cols(min_row=1,
                           max_row=3,
                           min_col=1,
                           max_col=3):
    col[0].value = "Pylenin"
    col[1].value = "loves"
    col[2].value = "Python"

wb.save("pylenin.xlsx")
```

**Output**

![Writing data to Excel with Openpyxl through iteration - Example 3](/img/excel-with-python/wb4-pylenin.png)

### Appending data to Excel with Openpyxl

Openpyxl also provides an `append()` method. 
This is used to append values to an existing Excel sheet. 

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('pylenin.xlsx')
sheet = wb.active

data = (
    ("Pylenin", "likes", "icecream"),
    ("Pylenin", "likes", "Cricket")
)

for row in data:
    sheet.append(row)
wb.save('pylenin.xlsx')
```

**Output**

![Appending data to Excel with Openpyxl](/img/excel-with-python/wb5-pylenin.png)

### Manipulating Sheets in Openpyxl

Each Excel workbook can contain multiple sheets.
To get a list of all the sheet names in an Excel workbook, you can use the `wb.sheetnames`.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('pylenin.xlsx')
print(wb.sheetnames)
```

**Output**

```bash
['Sheet']
```

As you can see, `pylenin.xlsx` has only one sheet.

**To create a new sheet**, use the `create_sheet()` method provided by Openpyxl.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('pylenin.xlsx')
wb.create_sheet('Pylenin')

wb.save('pylenin.xlsx')
```

**Output**

![Create a new sheet in Excel workbook with Openpyxl](/img/excel-with-python/wb6-pylenin.png)

You can also create sheets at different positions in the Excel Workbook.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('pylenin.xlsx')

# insert sheet at 2nd to last position
wb.create_sheet('Lenin Mishra', -1)

wb.save('pylenin.xlsx')
```

**Output**

![Inserting sheets at different positions in Excel workbook with Openpyxl](/img/excel-with-python/wb9-pylenin.png)

If your Excel workbook contains multiple sheets and you want to work with a particular sheet, you can refer the title of that sheet in your workbook object.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('pylenin.xlsx')
ws = wb["Pylenin"]

ws["A1"].value = "Pylenin"
ws["A2"].value = "loves"
ws["A3"].value = "Python"

wb.save('pylenin.xlsx')
```

**Output**

![Working with a particular sheet in Excel workbook with Openpyxl](/img/excel-with-python/wb7-pylenin.png)

### Practical usage example of Openpyxl

Let's perform some data analysis with `wb1.xlsx` file as shown in the first image.

**Objective**

1. Add a new column showing `Total Price per Product`.
2. Calculate the `Total Cost` of all the items bought.

The resulting Excel sheet should look like the below image.

![Perform Data Analysis with Excel in Openpyxl](/img/excel-with-python/wb10-pylenin.png)

#### Step 1 - Find the max row and max column of the Excel sheet

As mentioned before, you can use the `sheet.max_row` and `sheet.max_column` attributes 
to find the max row and max column for any Excel sheet with Openpyxl.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

print(f"Max row in the active sheet is {sheet.max_row}")
print(f"Max column in the active sheet is {sheet.max_column}")
```

**Output**

```bash
Max row in the active sheet is 11
Max column in the active sheet is 4
```

![Max row and Max column in Excel with Openpyxl](/img/excel-with-python/wb11-pylenin.png)

#### Step 2 - Add an extra column in Excel with Openpyxl

![Add an extra column in Excel with Openpyxl](/img/excel-with-python/wb12-pylenin.png)

To add an extra column in the active Excel sheet, with calculations, you need to first create a new column header in the first empty cell and then iterate over all rows to multiply `Quantity` with `Cost per Unit`.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Add new column header

sheet.cell(row=1, column=sheet.max_column+1).value = "Total Price per Product"

wb.save("wb1.xlsx")
```

**Output**

![Add an extra column in Excel with Openpyxl](/img/excel-with-python/wb13-pylenin.png)

Now that an extra column header has been created, the `sheet.max_column` value will change to 5.

Now you can calculate the `Total Price per Product` using `iter_rows()` method.

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

# Calculate Total Price per Product

for id, row in enumerate(sheet.iter_rows(min_row=2,
                                         max_row = sheet.max_row)):

    row_number = id + 2 # index for enumerate will start at 0
    product_name = row[1].value
    cost_per_unit = row[2].value
    quantity = row[3].value
    print(f"Total cost for {product_name} is {cost_per_unit*quantity}")

    # Update cell value in the last column
    current_cell = sheet.cell(row=row_number, column=sheet.max_column)
    current_cell.value = cost_per_unit*quantity

    # Format cell from number to $ currency
    current_cell.number_format = '$#,#0.0'

print("\nSuccesfully updated Excel")
wb.save('wb1.xlsx')
```

**Output**

```bash
Total cost for Pencil is 100.0
Total cost for Pen is 500
Total cost for Eraser is 25.0
Total cost for Sharpner is 75.0
Total cost for Files is 150
Total cost for A4 Size Paper is 90
Total cost for Pencil Box is 240
Total cost for Pen Stand is 55.0
Total cost for Notebook is 100
Total cost for Marker is 75

Succesfully updated Excel
```

![Add an extra column in Excel with Openpyxl](/img/excel-with-python/wb14-pylenin.png)

#### Step 3 - Calculate sum of a column in Excel with Openpyxl

The last step is to calculate the `Total Cost` of the last column in the Excel file.

1. **Access the last column and add up all the cost.**

    You can read the last column by accessing the `sheet.columns` attribute.
    Since it returns a generator, you first convert it to a `python list` and access the last column.
   
    ```python3
    last_column_data = list(sheet.columns)[-1]
    # Ignore header cell 
    total_cost = sum([x.value for x in last_column_data[1:]])
    ```
   
2. **Create a new row 2 places down from the max_row and fill in `Total Cost`.**

    ```python3
    max_row = sheet.max_row
    
    total_cost_descr_cell = sheet.cell(row = max_row +2, column = sheet.max_column -1)
    total_cost_descr_cell.value = "Total Cost"
     
    total_cost_cell =  sheet.cell(row = max_row +2, column = sheet.max_column)
    total_cost_cell.value = total_cost
    ```
   
3. **Import `Font` class from `openpyxl.styles` to make the last row Bold.**

    ```python3
    # Import the Font class from Openpyxl
    from openpyxl.styles import Font
    
    bold_font = Font(bold=True)
    total_cost_descr_cell.font = bold_font
    total_cost_cell.font = bold_font
    
    total_cost_cell.number_format = "$#,#0.0"
    ```

**Final Code looks like the below.**

**Code**

```python3
from openpyxl import load_workbook

wb = load_workbook('wb1.xlsx')

sheet = wb.active

last_column_data = list(sheet.columns)[-1]
# Ignore header cell 
total_cost = sum([x.value for x in last_column_data[1:]])

max_row = sheet.max_row

total_cost_descr_cell = sheet.cell(row = max_row + 2, column = sheet.max_column -1)
total_cost_descr_cell.value = "Total Cost"

total_cost_cell =  sheet.cell(row = max_row + 2, column = sheet.max_column)
total_cost_cell.value = total_cost

# Import the Font class from Openpyxl
from openpyxl.styles import Font

bold_font = Font(bold=True)
total_cost_descr_cell.font = bold_font
total_cost_cell.font = bold_font

total_cost_cell.number_format = "$#,#0.0"

print("\nSuccesfully updated Excel")
wb.save('wb1.xlsx')
```

When you run the above code, you should see all the relevant updates to your Excel sheet.

![Data Analysis in Excel sheets with Openpyxl](/img/excel-with-python/wb15-pylenin.png)

In this Openpyxl tutorial, we learnt about various ways to handle Excel files in Python. If you have any doubts, post your doubts in the comment section below. 

#### Related Reading

1. [Combining multiple Excel sheets into one in Python](https://www.pylenin.com/blogs/combining-workbooks-to-sheets/)
2. [Openpyxl - Plotting Bar Charts in Excel](https://www.pylenin.com/blogs/bar-charts-openpyxl)
3. [Openpyxl - Plotting Bar Charts in Excel](https://www.pylenin.com/blogs/bar-charts-openpyxl/)
4. [Openpyxl - Plotting Bubble Charts in Excel](https://www.pylenin.com/blogs/bubble-charts-openpyxl/)