**Milestone1 - Supply Chain Visibility And Optimization**

**Objective**:
Improve supply chain visibility by tracking orders, shipping, and inventory.
Identify inefficiencies in the supply chain process.
Build a structured data model with fact and dimension tables.
Enable reporting and dashboards in Power BI for better decision-making.
Provide insights that help optimize logistics, reduce delays, and improve customer satisfaction.

**Dataset Source:**
Download dataset from Kaggle (Supply Chain dataset).
The dataset includes information such as:
Orders (Order ID, Order Date, Shipping Date).
Customers (Customer ID, Customer Name, Location).
Products (Product ID, Product Name, Category).
Shipping details (Carrier, Mode, Cost).
Locations and Departments.
Use this dataset as the foundation for building fact and dimension tables in Power BI.

**Data Cleaning and Transformation Steps:**

**Step 1:** Load Dataset
Import the Kaggle dataset into Power BI (via Power Query Editor).
Verify column names and data types.

**Step 2:** Create Fact Table
Rename the main table as Fact_Table.
Remove sensitive columns:
Customer Email
Customer Password
Order Zipcode
Keep only relevant transactional fields (Order ID, Product ID, Customer ID, Shipping details, etc.).

**Step 3:** Create Dimension Tables
Duplicate Fact_Table to create dimension tables.
Select only required columns for each dimension:
Dim_Customer → Customer_ID, Customer_Name, etc.
Dim_Product → Product_ID, Product_Name, etc.
Dim_Category → Category_ID, Category_Name.
Dim_Shipping → Shipping details.
Dim_Location → Location details.
Dim_Department → Department_ID, Department_Name.

**Step 4:** Remove Duplicates
For each dimension table, remove duplicate rows based on key columns:
Customer_ID
Product_ID
Category_ID
Department_ID

**Step 5:** Add Index Columns
Add index columns to uniquely identify records:
Dim_Shipping → Shipping_ID
Dim_Location → Location_ID

**Step 6:** Create Dim_Date Table
Use DAX Calendar Function to generate a date table.
Base it on the minimum Order Date and maximum Shipping Date from Fact_Table.
Add calculated columns:
Year
Month Number
Month Name
Quarter
Week Number
Day Number
Day Name

**Step 7:** Merge Dimensions Back into Fact Table
Merge Dim_Shipping and Dim_Location into Fact_Table using Left Outer Joins.
Expand only the new ID columns (Shipping_ID, Location_ID).

**Step 8:** Define Relationships
Create relationships between Fact_Table and Dimension Tables:
One-to-Many cardinality.
Active relationship: Order Date → Dim_Date.
Inactive relationship: Shipping Date → Dim_Date.

**Step 9**: Finalize Changes
Save transformations frequently.
Click Close & Apply in Power Query Editor to load the cleaned and transformed data model into Power BI.

**Data Model Overview:**
Fact_Table → Stores transactional data (orders, shipping, product IDs, customer IDs).
Dimension Tables → Provide descriptive attributes:
Dim_Customer → Customer details.
Dim_Product → Product details.
Dim_Category → Product categories.
Dim_Shipping → Shipping details with Shipping_ID.
Dim_Location → Location details with Location_ID.
Dim_Department → Department details.
Dim_Date → Calendar table with Year, Month, Quarter, Week, Day.
Relationships:
Fact_Table connects to each dimension via IDs.
Dim_Date connects to Fact_Table on Order Date (active) and Shipping Date (inactive).
This star schema enables clear reporting and efficient queries.

**Tools Used:**
Power BI → For data cleaning, transformation, modeling, and visualization.
Power Query Editor → For removing duplicates, creating dimension tables, and merging data.
DAX (Data Analysis Expressions) → For creating Dim_Date table and calculated columns.
SQL Server → For validating data consistency between source and Power BI.
Kaggle Dataset → As the primary data source for supply chain operations.
