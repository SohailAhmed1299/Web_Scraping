# Amazon Product wen Scraping

First, I created various methods to scrape the data but because of 505 errors in the website request, I had to opt for a different method where I used individual Html parsers of a single sheet to create the output in this project the libraries, I used were **BeautifulSoup4**,**openpyxl** and **os**

![Import](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/308b2ce9-a977-469e-9c3a-c403e64ff6b3)

Use of the Libraries:-

**BeautifulSoup (bs4):**

BeautifulSoup is a Python library that allows parsing and navigating HTML or XML documents.
It is used in this code to extract data from an HTML file obtained from the Amazon website.
The BeautifulSoup function is used to create a BeautifulSoup object to parse the HTML content.
The find_all method is used to locate all div elements with a specific class attribute. These div elements contain relevant information about the products on the webpage.

![BS4](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/58eeaf35-5bb1-44f5-9e72-1ef6ebb87dbb)

**openpyxl:**

openpyxl is a Python library for reading and writing Excel files (xlsx).
It is used to create an Excel workbook, write data, and save it as an Excel file.
The Workbook class is used to create a new Excel workbook or load an existing one.
The active property of the workbook is used to select the active sheet to write the data.
The append method is used to add headers to the sheet (if it's empty) and to add product data to the sheet.
The cell method is used to access specific cells in the sheet and write data to those cells.

![Xly](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/443c9e97-50bd-475e-bda6-5c2bda456e1a)

**os:**

The os library provides a way to interact with the operating system's file system.
The getcwd method is used to get the current working directory.
The file method is used to check if the specified file exists in the current directory.
This allows the code to check if the HTML file "Amazon.in _ gardening 7.html" exists before proceeding with parsing and scraping.
The overall use of these libraries in the code is to:

![OS](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/e44250c5-990b-43c7-b946-824559718a3b)

Read the HTML file from the local directory.
Parse the HTML content using BeautifulSoup to extract relevant information like product names, prices, reviews, users, and previous monthly records from specific HTML elements (divs and spans).
Store the extracted data in Python lists for further processing and writing to an Excel file.
Use openpyxl to handle Excel workbook and sheet operations.
Check if the output Excel file exists and load it if present, or create a new workbook.
Append the extracted data to the existing Excel sheet or create a new sheet if the file is empty.
Finally, save the data in an Excel file named "Amazon_product.xlsx".

# Overall Code

1. Import the required libraries: BeautifulSoup from bs4, openpyxl, and os.

2. Get the current working directory using os.getcwd().

3. Check if the HTML file named "Amazon.in _ gardening 7.html" exists in the current directory.

4. Read the HTML content from the file and parse it using BeautifulSoup.

5. Find all div elements with the class "s-card-container s-overflow-hidden aok-relative puis-wide-grid-style puis-wide-grid-style-t2 puis-expand-height puis-include-content-margin puis puis-vnjufzhntlqm11zjo2xc51q7r1 s-latency-cf-section s-card-border".

6. If no div elements are found, print "No data found. Check if the HTML structure or class names have changed."

![OV 1](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/b0bc993b-fc6e-44dc-87cb-86ab3ab52e01)


7. Prepare lists to store product information: product_names, product_prices, product_reviews, product_users, and previous_monthly_records.

8. Loop through each div element and extract the following information:
   Product Name: Find the span element with class "a-size-base-plus a-color-base a-text-normal".
   Product Price: Find the span element with class "a-price-whole" and then find the nested span with class "a-offscreen" to get the price value.
   Product Reviews: Find the span element with class "a-icon-alt" to get the review text.

9. Users: Find the span element with class "a-size-base s-underline-text" to get the user text.
   Previous Monthly Record: Find the span element with class "a-size-base a-color-secondary" to get the previous monthly record text.

![OV2](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/3422e8ef-af06-4b43-b7f0-3b2ccdece60d)

10. Load the existing Excel file named "Amazon_product.xlsx" if it exists, else create a new workbook.

11. Select the active sheet in the workbook.

12. Get the row count of the sheet to determine the next empty row for appending data.

13. If the sheet is empty, add headers: "Product Name", "Product Price", "Product Reviews", "Users", and "Previous Monthly Record".

14. Write the data to the sheet using a for loop and zip function to combine data from the lists.

15. Save the Excel file.

16. If any error occurs during the process, print the error message. Otherwise, print "Data has been extracted and appended to 'Amazon_product.xlsx'."

![OV3](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/edfbd475-dd7d-4938-b316-dd9ebdbcce0f)


# Output

![Capture](https://github.com/SohailAhmed1299/Web_Scraping/assets/90980952/3802a9da-aa96-458e-80e8-58074f29ec0b)



