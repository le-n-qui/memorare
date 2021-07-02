# Creating Permanent Tables
## How to create a new permanent table:
1. Write SQL query
2. Click **Show Options**
3. Specify the **Destination Table** (can be existing)
4. Choose **Write Preference** (if table already exists):
    * Write if empty
    * Append records
    * Overwrite table
5. Run query 
## Importing JSON data
We can ingest a JSON file that has a parent-child relationship of fields directly into BigQuery.  
First, we create a dataset within our project. Then, once our dataset is present, we click  
on our dataset name and we should see a page opening up. Look for the plus (+) icon to create  
a new table. Click on the icon and we will have *Create table* page where we see *Source*   
at the top of the page. Click on the drop down menu to choose a method to create our table.  
We will use *Upload*. Then we see the page wants to know what file format we will use and  
so we choose JSON. Finally, we browse for our file under *Select file*. Once that's done, give  
your table a name and click *Create table*.
## Temporary Tables and Query Results
* All query results are saved to either a temporary or permanent table.
* If we specify a destination table then that table becomes permanent; otherwise, it's a new temporary table.
* Temporary tables are the basis of query cached results.
* Temporary tables last 24 hours only.
