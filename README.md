# INTRODUCTION

Cleaning data is indeed a crucial step in data analysis to ensure the accuracy and reliability of your results. 
Excel is a widely used tool for data cleaning, and it offers various functions and features to help you clean and organize your data effectively. 

This article will showcase the step-by-step process I followed to clean up a messy dataset discovered on the internet.

The disorganized dataset was downloaded from ForsightBI using the provided link. It contains customer details that are jumbled together in a single cell within the spreadsheet. The information includes customer names, addresses, ages, and genders.

![THE dataset](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/799790a7-6f7d-4f63-8577-a461298cd1f0)


The primary goal of this data cleaning exercise is to extract and organize the customer details into separate columns, ensuring that each piece of information such as customer names, addresses, ages, and genders occupies its designated column for a well-structured dataset.

During the data cleaning process, the following Excel functions and tools were employed:

1. **TEXT-TO-COLUMNS**: This tool is used to split the contents of a single cell into multiple columns based on a specified delimiter. It was utilized to separate the jumbled customer details in the spreadsheet into individual columns for customer name, address, age, and gender.

2. **TEXTAFTER()**: This function extracts the text after a specified character or string in a cell. It was used to isolate relevant information from the customer details that came after a particular delimiter or keyword.

3. **TEXTBEFORE()**: This function extracts the text before a specified character or string in a cell. It helped in extracting pertinent data from the customer details that came before a specific delimiter or keyword.

4. **TEXTJOIN()**:  This function allows you to combine or join the contents of multiple cells into a single cell.

5. **LEFT()**: This function extracts a specified number of characters from the beginning (leftmost) side of a cell. It was utilized to obtain necessary data from the customer details, such as names or partial addresses.

7. **TRIM()**: This function is used to remove any leading or trailing spaces from the contents of a cell. It is particularly helpful in cleaning up data where extra spaces have been inadvertently added, which can lead to inconsistencies in the dataset. TRIM() ensures that the data is cleaned of unnecessary spaces, making it more uniform and consistent for further analysis.

By employing these Excel functions and tools, the data cleaning process was facilitated, enabling the extraction and organization of customer details into separate columns, resulting in a well-structured dataset.



# DATA CLEANING PROCESSES

## EXTRACTING THE CUSTOMERS NAME AND ADDRESS DETAILS

In order to retrieve the customer's name and address, utilized the TEXTBEFORE() function with the delimiter set as " Age" The formula used in cell B2 is: =TEXTBEFORE(A2, " Age").

![textbefore](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/e135c432-7d5e-457a-bb65-924292a67f97)


This formula allows us to extract the text from cell A2 up to (but not including) the first occurrence of "Age". 

Proceed to copy the contents of column B, and subsequently, re-paste them as values. This action will convert the content of Column B into fixed, unchanging values, thereby eliminating any previous formula references present in column B.

To copy the contents of column B and re-paste them as values, follow these steps:

1. Select the entire column B by clicking on the column header "B" at the top.
2. Right-click on the selected column, and from the context menu, choose "Copy" or press Ctrl + C.

3. Right-click on the same column B again, and this time, choose "Paste Special" from the context menu.

4. In the "Paste Special" dialog box, select "Values" from the available options.

6. Click on the "OK" button to apply the paste operation. The contents of column B will now be pasted as values, replacing any formulas with their resulting values.

![paste special](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/da66d11e-e963-41bd-a3cd-dddf92d2f9ab)


The outcome in column B is not as intended. The column still combines the customer's name and address in a single cell, necessitating the need to separate them into individual columns.

To rectify the issue, we can utilize the "Text-to-Columns" feature in Excel. This tool allows us to split the contents of each row in column B into separate columns based on a specified delimiter. Here's how to use the "Text-to-Columns" feature:

1. Select the entire column B by clicking on the column header "B" at the top.
2. Go to the "Data" tab in Excel's ribbon.
3. Click on the "Text-to-Columns" button in the "Data Tools" group. This will open the "Convert Text to Columns Wizard."

![TEX-COL](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/2cc0893a-a954-4206-b704-c08b5c13528e)

4. In the wizard, select the "Delimited" option and click "Next."
5. Choose the delimiter that separates the customer name and address in column B. In this case, it appears to be space. Check the "space” checkbox and ensure that other delimiters are unchecked. You can also see a preview of how the data will be split below the delimiter options.

![DELIMETER](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/2d4b8bc3-905c-46c8-a826-23d7457eec12)


6. Click "Next."
7. Choose the destination cell in this case cell C1.
8. If there are any other advanced settings required, you can make those adjustments on this screen. Otherwise, click "Finish."
Excel will now separate the content in each row of column B into separate columns.

![textcolumn outcome](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/fb0a0b69-2306-4791-a5f8-b863b101e371)

After using the "Text-to-Columns" feature to separate the customer names and addresses into separate columns, follow these steps to further clean up the dataset:

1. Select the entire contents of column E by clicking on the column header "E" at the top. Press the "Delete" key to remove the contents of column E.

2. In the same way, select the entire contents of column C and press the "Delete" key to clear the contents of column C.

3. Now, we no longer need the column B with the combined customer names and addresses. To delete column B, right-click on the column header "B" and choose "Delete" from the context menu.

4. In row 1, rename the column header in cell B1 as "Name" to indicate that this column contains customer names.

5. Similarly, rename the column header in cell E1 as "Address" to indicate that this column contains customer addresses.

After completing these steps, you will have a cleaned dataset with customer names in column B, customer addresses in column E, and the unnecessary columns removed. 

Now;
1. In column B (Name), you can combine the contents of columns C and D using the "Flash Fill" feature in Excel:
   - In cell B2, manually type the first combination of the customer name (e.g., "John Smith").
   - In cell B3, start typing the next name (e.g., "Jane Doe").
   - Excel will recognize the pattern and display suggestions in a pop-up. Press "Enter" to accept the suggestion, and Excel will automatically fill the remaining names by combining columns C and D.

![Screenshot (388)](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/91657cfb-7ada-4fe1-aeed-82692d921d56)


2. Now that the names are correctly combined in column B, you can delete columns C and D:
   - Select the entire contents of column C by clicking on the column header "C" and press the "Delete" key to remove the column.
   - Similarly, delete column D in the same way.

3. In column E (Address), you can use the TEXTJOIN() function to combine the contents of columns F, G, H, I, J, and K using a space as the delimiter:
   - In cell E2, enter the formula `=TEXTJOIN(" ",,F2:K2)`.
   - Press "Enter" to get the combined address for the first row.
   - Drag the fill handle (a small square at the bottom-right corner of the cell) down to apply the formula to the entire column.

![TEXTJOIN](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/ed876c65-642e-4b89-8906-f254b2310fb1)


4. Copy the contents of column E and re-paste them as values

5. Finally, delete columns F, G, H, I, J, and K:
   - Select the entire contents of any of these columns by clicking on the column header (e.g., "F").
   - Press the "Delete" key to remove the columns.

By following these steps, you will have a cleaned dataset with customer names and addresses properly combined and organized, and unnecessary columns removed.

![name and address](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/85ca13d5-3a7a-479d-82e4-9506e6a1ebe8)


## EXTRACTING THE CUSTOMER AGE AND GENDER DETAILS

1. Name column D as "Age" and column E as "Gender" to provide clear labels for the data in these columns.

2. In column D (Age), use the formula `=TRIM(LEFT(TEXTAFTER(A2, "Age"), 3))` to extract the age number:
   - This formula first uses the TEXTAFTER() function to extract the text after "Age" in cell A2, which will be something like " 17, Gender Male" (assuming the age is two digits).
   - Then, the LEFT() function takes the leftmost 3 characters from the extracted text, which will be " 30" in this case (including the leading space).
   - Finally, the TRIM() function removes any leading or trailing spaces, resulting in the extracted age value "17"

![age](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/96632a6e-6aed-4be6-9a56-460cf8f66e16)

3. In column E (Gender), use the formula `=TRIM(TEXTAFTER(A2, "Gender"))` to extract the gender:
   - This formula uses the TEXTAFTER() function to extract the text after "Gender" in cell A2, which will be something like " Male" or " Female."
   - The TRIM() function removes any leading or trailing spaces, giving you the extracted gender, such as "Male" or "Female"

![gender](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/5cb6fdb4-683c-42b3-8644-802f0fe11c58)


After applying these formulas to the entire columns D and E, you will have the age and gender information extracted and displayed accurately in the respective columns. The dataset is now cleaned and properly organized, ready for further analysis or use. Don't forget to save your cleaned dataset for future reference.

Click here to access an easier method for cleaning the same dataset.

   ![thanks-for-reading](https://github.com/dannieRope/Cleaning-Jumbled-Up-Customers-Details-in-Excel--APPROACH-1/assets/132214828/b0b81e12-f91d-4177-beba-e5e2badfc79c)

  







