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
## Query Cache
Cache is **not used** when:
   * Underlying table(s) updated
   * Deterministic queries used, e.g. CURRENT_TIMESTAMP()
   * Cache can be disabled in *Show Options*
## Creating Logical Views
We may want to store results in a view. But what is a view? It is a saved SQL query, or think of it as a virtual table.  
The underlying query is re-ran each time the view is queried. Why do we need to use a view? Sometimes we want a selected  
few to have access to our views, and thus authorized views allow control over which CURRENT_USER() sees what rows in the table.
There is a big difference between a permanent table and a logical view, which is that a view lacks the *Preview* feature where you  
can see an overview of your table columns and data values.  

Let's discuss two use cases involving logical views: 
   1. Say there are two teams (marketing and analytics) that will access your Google Cloud Platform project, and you want to give the marketing team access to fewer records of a particular dataset. Through views, you can filter out users, based on their log-in information (e.g. email), with the use of SESSION_USER().
   2. Maybe your underlying data source is constantly changing, and you have to query that dataset frequently and regularly without re-running your query to create a permanent table. With views, you can avoid that and you get updated results at the moment you query your view.


