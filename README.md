# SSIS-DataMigration-Excel-To-SQL-
This project provides a complete ETL (Extract, Transform, Load) pipeline for transferring data from Excel files to SQL Server databases using SQL Server Integration Services (SSIS). This Project is designed to automate data migration, ensure data integrity, and optimize performance for large datasets.

# Technologies Used:
  - SSIS (SQL Server Integration Services): ETL tool for designing and automating data workflows.
  - SQL Server Management Studio (SSMS): For database management and SQL queries.
  - Excel: Data source for input files.
  - T-SQL Scripts: For custom transformations and validations during data processing.

# Fact Table Pipeline Workflow:
   # Data Sources:
Extracts data from Orders, Order Details, Products, Customers, Suppliers, and Shippers.
   # Transformations:
Derived Columns: Converts data types (e.g., string to integer).
Sorting and Merging: Ensures data is sorted and merged correctly for further processing.
Lookups: Matches keys against dimension tables (e.g., ProductPK, CustomerPK).
Calculations: Computes Total Cost as a measure for the Fact Table.
   # Loading:
Inserts the final dataset into the Sales_Fact Destination table in the Data Warehouse.

# Dimensions Data Migration Pipeline Steps:
 - Extract Data Sources:
   1- Reads data from source (CSV files).
   2- Uses tasks like OLE DB Source and Flat File Source for data extraction.
 - Transform Data:
   1- Derived Columns: Converts data types, formats dates, and calculates derived values.
   2- Lookups: Ensures referential integrity by validating keys against master records.
   3- Sorting and Merging: Combines data from different sources for unified processing.
 - Load Dimension Tables:
   1- Loads transformed data into dimension tables such as Orders, Products, Suppliers, and Regions using OLE DB Destination Tasks.
   2- Maintains Slowly Changing Dimensions (SCD) if required, ensuring data history tracking.
   
# Workflow for Data Migration:
 - Pipeline Steps:
   1- Source Connection:
     -  Extracts data from the source database using OLE DB Source.
     -  Filters data based on specific conditions (e.g., active records only).
   2- Data Transformation:
     - Sort Task: Ensures records are ordered before merging or processing.
     - Removes duplicates or incorrect records based on key columns.
   3- Load into Destination Database:
     - Transfers processed data to the target database using OLE DB Destination.
     - Optimizes performance by batching inserts and using indexes.
  
# Contributions:
Contributions are welcome! Fork the repository, add your enhancements, and submit pull requests.

# Contact:
For questions, issues, or feature requests, please contact via GitHub Issues or email.



