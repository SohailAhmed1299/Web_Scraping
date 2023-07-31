# Amazon Product wen Scraping

First i created various metohds to scrape the data but beacause of 505 erorr in the website request, I had to opt for different method where I use individual Html parser of a single sheet to crete the output in this project the libraries, I used were **BeautifulSoup4**,**openpyxl** and **os**

![Import](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/308b2ce9-a977-469e-9c3a-c403e64ff6b3)

Use of the Libraries:-

**BeautifulSoup (bs4):**

BeautifulSoup is a Python library that allows parsing and navigating HTML or XML documents.
It is used in this code to extract data from an HTML file obtained from the Amazon.in website.
The BeautifulSoup function is used to create a BeautifulSoup object to parse the HTML content.
The find_all method is used to locate all div elements with a specific class attribute. These div elements contain the relevant information about the products on the webpage.

![BS4](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/58eeaf35-5bb1-44f5-9e72-1ef6ebb87dbb)

**openpyxl:**

openpyxl is a Python library for reading and writing Excel files (xlsx).
It is used to create an Excel workbook, write data to it, and save the workbook as an Excel file.
The Workbook class is used to create a new Excel workbook or load an existing one.
The active property of the workbook is used to select the active sheet to write the data.
The append method is used to add headers to the sheet (if it's empty) and to add product data to the sheet.
The cell method is used to access specific cells in the sheet and write data to those cells.

![Xly](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/443c9e97-50bd-475e-bda6-5c2bda456e1a)

**os:**

The os library provides a way to interact with the operating system's file system.
The getcwd method is used to get the current working directory.
The isfile method is used to check if the specified file exists in the current directory.
This allows the code to check if the HTML file "Amazon.in _ gardening 7.html" exists before proceeding with parsing and scraping.
The overall use of these libraries in the code is to:

![OS](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/e44250c5-990b-43c7-b946-824559718a3b)

Read the HTML file from the local directory.
Parse the HTML content using BeautifulSoup to extract relevant information like product names, prices, reviews, users, and previous monthly records from specific HTML elements (divs and spans).
Store the extracted data in Python lists for further processing and writing to an Excel file.
Use openpyxl to handle Excel workbook and sheet operations.
Check if the output Excel file already exists and load it if present, or create a new workbook if not.
Append the extracted data to the existing Excel sheet or create a new sheet if the file is empty.
Finally, save the data in an Excel file named "Amazon_product.xlsx".
