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
- 
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Dim_customer.png">
<img src = "https://github.com/Ahmed800363/Building-DWH-Using-SSIS/blob/main/Task%20ETL(SSIS%20'Adventure%20Work%20')/Images/Dim_customer2.png">


