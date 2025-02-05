This project involves building a data ingestion pipeline for travel bookings while implementing Slowly Changing Dimension Type 2 (SCD2) for customer data. The goal is to efficiently process and store historical changes while ensuring data quality.

Tech Stack
1) Databricks
2) Apache Spark (PySpark)
3) Google Cloud Storage
4) Delta Lake
5) Databricks Workflows
6) PyDeequ



Key Features & Implementation

Create Delta Tables




![image](https://github.com/user-attachments/assets/1460be7e-9e3f-4d07-a926-c76edaf834f5)


Define bookings_fact and customers_dim Delta tables for storing processed data.



![image](https://github.com/user-attachments/assets/7ac82db4-9a9c-44fb-90c2-87a2c38b6b64)

Read Daily Bookings & Customers Data

Load daily CSV files (user-provided date) into Spark DataFrames.

Perform Data Quality Checks

Use PyDeequ to validate bookings and customers data.

Stop or continue pipeline execution based on validation success/failure.




![image](https://github.com/user-attachments/assets/80a650c7-08f4-415a-8365-feafd6a9801d)





![image](https://github.com/user-attachments/assets/53c03909-66dd-4311-ab09-01bc77d45223)





![image](https://github.com/user-attachments/assets/b789b916-9e0b-4252-978f-4aa6a072c4ab)

Aggregate and Merge Bookings Data

Run aggregations on bookings DataFrame.

Update final aggregated results into bookings_fact using Merge query.


![image](https://github.com/user-attachments/assets/b9323ae8-39c9-4aca-a193-9067af7ab0a6)

Implement SCD2 Merge for Customer Data

Maintain historical changes in customers_dim by applying SCD2 Merge query.



![image](https://github.com/user-attachments/assets/80b6fa90-cb56-42fe-8fe6-d91292552da3)


Automate Pipeline Execution

Set up a Databricks Workflow.

Configure an input key-value parameter to manually pass the processing date.




