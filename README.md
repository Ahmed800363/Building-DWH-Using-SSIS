# Building-DWH-Using-SSIS
End-to-End Data Warehouse project using SSIS. Includes ETL pipelines for extracting, transforming, and loading data into a dimensional data warehouse schema to support business intelligence and analytics.

## Tools Used

- SQL Server
- SSIS (SQL Server Integration Services)
- Data Warehouse
- ETL
## Design Pipeline
- Source Systems (SQL Server)
-    |
-    v
- SSIS ETL (ETL)
-    |
-    v
- Data Warehouse (Fact & Dimension Tables)
-    |
-    v
- Destination Source (SQL Server)
## Design Diagram 
##### This Diagram of DWH 
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Design%20Diagram.png">

# ETL For SSIS
- Built ETL pipelines using SSIS to extract data from source databases, apply transformation logic, and load the processed data into the Data Warehouse.
The ETL process includes data extraction, data cleansing, transformation, and loading into fact and dimension tables.
Data is extracted from SQL Server source, transformed using SSIS transformations, and loaded into a structured Data Warehouse schema.
# Dim_Customer
## DFL- Dim_Customer --> To create Data Flow 
- Customer-source --> to connection data from source
- DC-Source-System-Code --> To Add column
- Custmoer-info --> to doing Lookup
- Slowly Changing Dimension -- > Implemented Slowly Changing Dimension to track historical changes in dimension data while pressving past records .
- Insert Destination --> To load data in Destination Source 
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Dim_customer.png">
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Dim_customer2.png">

# Dim_Product
## DFT-Dim-product --> To create Data Flow 
- Product Table --> to connection data from source
- LKP-product model and LKP-product sub-cat --> Used Lookup to match and retrive related data from referene tables during the Data Flow
- Dd-Col-Replace NULL --> Used Derived Column  to Replace null values with default values or calculated expressions during the Data Flow
- Slowly Changing Dimension -- > Implemented Slowly Changing Dimension to track historical changes in dimension data while pressving past records .
- Insert Destination --> To load data in Destination Source 
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Dim_Product.png">
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Dim_Product2.png">

# Dim_Date
## DFT-Dim-Date --> To create Data Flow 
- Excel Source --> to connection data from Excel source
- Data Conversion --> Used Data Conversion to change the data type of column to match the destination schema during the Data Flow 
- OLE DB Destination --> To load data in Destination Source 
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Dim_Date.png">


# Dim_Territory
## DFT-Dim-territory --> To create Data Flow 
- Territory --> to connection data from source
- Lookup --> Used Lookup to match and retrive related data from referene tables during the Data Flow
- Derived Column --> Used Derived column to create IS-CURRENT AND START DATE fields for tracking the current version of records
- OLE DB Destination --> To load data in Destination Source 
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Dim_Territory.png">


# Fact_Sales 
## truncate fact_sales --> to truncate all data from table befora Laod new data ,then laod all data from first 
## Data Flow Task --> To create Data Flow 
- Sales Order Header --> to connection data from source
- Sales Order Details --> to connection data from source
- Merge Join --> to merge join between 'Sales Order Header' & 'Sales Order Details'
- LKP-Custmoer --> Used Lookup to match and retrive related data from referene tables during the Data Flow
- LKP-Product --> Used Lookup to match and retrive related data from referene tables during the Data Flow
- LKP-Territory --> Used Lookup to match and retrive related data from referene tables during the Data Flow
- LKP-Date --> Used Lookup to match and retrive related data from referene tables during the Data Flow
- DC- Replace Nulls --> Used Derived Column  to Replace null values with default values or calculated expressions during the Data Flow
- Insert Destination --> To load data in Destination Source 
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Fact_Sales_Full%20Load.png">
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Fact_Sales_Full%20Load%202.png">

