# Build_ETL_Pipeline

Extract data from AdventureWorksDW2019 and AdventureWorks2022

Here are more details on the specific source data extracted and transformed in my ETL pipeline: From the AdventureWorksDW2019 database, I extracted the DimProductSubcategory table and filtered to only pull data for two product subcategory types - "EnglishProductSubcategoryName" and "SpanishProductSubcategoryName". This provided product hierarchy data just for these two relevant subcategories for my analytics purposes.

In my Python ETL code, I queried this filtered DimProductSubcategory extract from SQL Server and loaded it into a Pandas dataframe.

From the AdventureWorks2022 database, I extracted the PersonContactType table and applied a similar filter to only extract the contact types of "Name" and ModifiedDate". This provided me targeted customer/contact data.

I extracted this filtered data from SQL Server into "sql" file, that I could then load into another Pandas dataframe in my ETL process.

By filtering the data during the extract phase, I can narrow down the data I load and work with to the data that is relevant to my analytical output. This reduces data volume and processing requirements.

In the transformation phase, I cleaned up both Pandas dataframes, such as tidying up the dates on the PersonContactType data. it focuses on preparing the data.

Finally in the load phase I add both of these cleaned data sources into the target output PostgreSQL database in my normalized analytical schema design. Unify focused extracts from two systems into a single display of information for analysis

<img width="960" alt="Screenshot 2023-12-08 035320" src="https://github.com/saifulanwar30/Build_ETL_Pipeline/assets/117976868/ed8d824f-fd4f-464b-bbca-239f8082ca14">

You can download AdventureWorks data at https://learn.microsoft.com/id-id/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms
