# Crowdfunding_ETL
Project 2

## Project Goals:
This is a course project assignment from BCS to be completed as a team where the team is tasked to perform the Extract, Transform, and Load (ETL) process using <code>Jupyter Notebook</code>. The team members are <a href="https://github.com/rrrrasha">Ms. Abdalla</a>, <a href="https://github.com/drkrenn">Mr. Krenn</a>, <a href="https://github.com/123noob1">Mr. Ngo</a>, and <a href="https://github.com/yoerisamwel">Mr. Samwel</a>.

## Data Sources Files:
The key files for this project are in three locations within this repository. 
The first location is in the main folder of the repository. The file "ETL_Mini_Project_RAbdalla_DKrenn_KNgo_YSamwel.ipynb" contains all of the syntax used to extract, clean, manage, and analyze the data for this project. 
The second key location is the postgreSQL folder, which contains most of the documents for the final part of the assignment. This folder contains a document for setting up (crowdfunding_db_schema.sql) and checking (crowdfunding_select_queries.sql) the SQL database. There's also "crowdfunding_ERD.png" in this folder which shows the entity relationship diagram (ERD) for the project. 
The final key location is in the "Resources" which contains 5 key excel files for the project. 

## Data Extraction & Cleaning: 
The data were imported from crowdfunding.xlsx. From there, the category & subcategory column was separated into a category column and a subcategory column. Then the unique values from category and subcategory were each exported into their own dataframe, and each item was assigned its own variable ID. The dataframes were then exported to separate excel files. 
In the next portion of the assignment, the main excel file, crowdfunding.xlsx, was cleaned and updated. A few variables were renamed with cleaner column headers. For a few of the columns, data types were updated, including the reformatting some columns as dates. The category and subcategory IDs were then imported in from the prevously created excel files. Columns that weren't needed were dropped, and the resulting dataframe was reexported to crowdfunding.xlsx. 
In the next portion of the assignment, a new dataframe was created to hold data on contacts. The original contacts spreadsheet had the data formatted as json. So the json data was imported and converted into a multicolumn dataframe. The dataframe was then cleaned and expored back into an excel file. Even though we were only required to do this processes using one of two approaches, we ultimately completed this portion using both techniques. 
The final portion of the project ties all of the previously created spreadsheets together. In order to make sense of all the data collectively, an ERD was created to show the cross-over constructs amongst all of the excel files. A database schema was created for SQL, and the data were loaded into a database named crowdfunding_db.

### Database Creation & Running Instructions:
#### Creating employees_db and tables:
Create a new database named <code>crowdfunding_db</code> then open and run the <code>crowdfunding_db_schema.sql</code> to create the following tables:
- contacts
- category
- subcategory
- campaign

#### Importing:
Start by importing the <code>csv</code> files that do not have any dependencies in the following order:
1) <code>contacts.csv</code> to <code>contacts</code> table
2) <code>category.csv</code> to <code>category</code> table
3) <code>subcategory.csv</code> to <code>subcategory</code> table

Once the above files have been imported, the following <code>csv</code> file can be imported into their tables in any order:
- <code>campaign.csv</code> to <code>campaign</code> table

#### Querying:
Open and run each query for each question from the <code>crowdfunding_select_queries.sql</code> file.
