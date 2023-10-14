# Project-3-Semi-Structure-Data-Analytics

In this project, I will be working on a sample data from MongoDB called "sample_supplies"

The tasks that I was given was to display top 10 products sales, top 3 products sales by store, the rankings of each store, purchased method by gender table and lastly the monthly total sales. These can be obtained by filtering out, downloading and compiling the product name, quantity, gender, price, store location , purchase method and sale date. 

Now I will be showing a walkthrough on my workings. 

The very first step it to load sample_supplies from mongoDB to my Visual Studio Code with the help of an extension called "MongoDB for VS Code" This extension allows you to connect to MongoDB and Atlas directly from your VS Code environment, navigate your databases and collections, inspect your schema and use playgrounds to prototype queries and aggregations. 

Once I have installed the extension and connect the data samples, I have to obtain the connection string in order to download the data into my computer. In order to download the sample data, I have install the database tool provided by mongoDB (https://www.mongodb.com/docs/database-tools/installation/installation-windows/). After installing the tool, I must run this code in the terminal "mongoexport --uri="mongodb+srv://new-user1:new-user1@bda.6whad1f.mongodb.net/sample_supplies" --collection="sales" --out=sales.csv --type=csv --fields=customer,items,purchaseMethod,saleDate,storeLocation" This command line basically gets the string of my connection, the file selected, file type and the fields which must be downloaded. 

The file itself is called "sales.csv" which can be found on the location on where I have run the command line. The csv file contains customer, items, purchaseMethod, saleDate and storeLocation in the rows. In the customer field, I must extract gender. This can be done in excel with the following line "=MID(A2, FIND("gender", A2) + 9, 1)" Now I will have to extract the product name, price and quantity from the row items which will be done in jupyter notebook. Sale date has the sales time included but only the columns in YYYY-MM-DD format is needed so I used this line in excel to remove it "=TEXT(DATEVALUE(LEFT(D2, 10)), "yyyy-mm-dd")" 
