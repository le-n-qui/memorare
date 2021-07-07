# Ingesting New Data into BigQuery
## Loading Data into BigQuery
  1. Create a permanent table and ingest data from Google Cloud Storage (e.g. CSV file)
  2. Create a permanent table, ingest data from GCS, and indicate *External table* on **Table type** (External Data Connection)
      * We are creating something like a pointer because data is not actually being stored inside BigQuery.
      * We cannot preview the table (Method 1 allows us to preview) because the data does not live in BigQuery. Though a configuration of data location is stored in BigQuery.
      * We will query directly from the data source on GCS.
      * We will lose performance benefits of BigQuery because we are not able to cache the data (Cannot cache data that is not natively stored in BigQuery). Also, without having BigQuery manage data storage, we do not have auto-optimization of our query execution path and certain wildcard functions are disabled. More importantly, data consistency is not guaranteed if the data values in the source are changed while querying.
      * Use case: Need a one-tine extract transform load (ETL) process (We connect to the external data source directly, perform preprocessing in SQL, and then ultimately store the result).
  3. Create a permanent table, ingest data from Google Sheets, and **Table type** automatically says *External table*
      * It may take longer because it has to run through Google Drive API to reach out and get the data
  4. Create a permanent table, ingest data locally, and **Table type** automatically says *Native table*
## Notes
  * When we create a new table for our dataset via external data source, there will not be a load job in *Job history* because no data is ingested.
  * If we specify a relative project pathname, such as *ecommerce.products* instead of *project_id.ecommerce.products*, BigQuery will assume the current project.
