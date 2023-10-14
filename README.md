# Project-3-Semi-Structure-Data-Analytics

In this project, I will work with sample data from MongoDB, which is called "sample_supplies." My tasks include displaying the top 10 product sales, the top 3 product sales by store, ranking each store, creating a table showing the purchased method by gender, and calculating the monthly total sales. To accomplish this, I need to filter, download, and compile information such as product name, quantity, gender, price, store location, purchase method, and sale date.

Let's walk through the steps I followed:

**Step 1: Loading Data from MongoDB to Visual Studio Code**
I used the "MongoDB for VS Code" extension to connect to MongoDB directly from Visual Studio Code. This extension allows me to navigate databases and collections, inspect schemas, and prototype queries and aggregations.

**Step 2: Obtaining the Connection String**
After connecting to the data samples, I needed to obtain the connection string to download the data to my computer.

**Step 3: Downloading the Sample Data**
To download the sample data, I installed the MongoDB database tool provided by MongoDB. You can find it here: [link](https://www.mongodb.com/docs/database-tools/installation/installation-windows/). I ran the following command in the terminal:


mongoexport --uri="mongodb+srv://new-user1:new-user1@bda.6whad1f.mongodb.net/sample_supplies" --collection="sales" --out=sales.csv --type=csv --fields=customer,items,purchaseMethod,saleDate,storeLocation

This command specifies the connection string, output file, file type, and the fields to download. The resulting file, "sales.csv," contains customer, items, purchaseMethod, saleDate, and storeLocation in its rows.

**Step 4: Extracting Gender from Customer Field**
In the customer field, I needed to extract gender. I achieved this in Excel with the following formula:

=MID(A2, FIND("gender", A2) + 9, 1)

**Step 5: Extracting Product Name, Price, and Quantity**
To extract the product name, price, and quantity from the "items" column, I used Jupyter Notebook.

**Step 6: Formatting Sale Date**
The sale date contains the sales time, but I only needed the date in the "YYYY-MM-DD" format. I used the following Excel formula to achieve this:

=TEXT(DATEVALUE(LEFT(D2, 10)), "yyyy-mm-dd")

These steps will allow me to work with the data more effectively and perform the required tasks.
