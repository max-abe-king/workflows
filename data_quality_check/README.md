Data Quality Check
======

This Treasure Data workflow is intended to prevent new columns being added to data tables due to changing inputs. It assums that new data is first going to a staging table before being transfered to a final data table. This workflow will mitigate the risk of exposing PII as well as give greater control to admins and project leaders who need to ensure data loads contain only specified columns.

This workflow will warn you of a new column when either there is:  

...1. A new column name, or  

...2. The same column name with different data type.

## Requirements

1. A Treasure Data Account that uses staging tables to update final data tables within the same database.
...* A table in your database with the columns 'final_table' and 'staging_table' that maps one to the other.

2. The Data_Quality_Check.dig file to copy/paste into a new workflow


## Set Up

1. Create a new workflow in your [Treasure Data Console](https://console.treasuredata.com/app/workflows/ "Treasure Data").

2. Copy and paste the entire Data_Quality_Check.dig file into the workflow.

3. Add a project file called 'sql/each_table_named.sql' __(NAME MUST BE EXACT, ELSE CHANGED IN THE WORKFLOW REFERENCE)__ and paste the following query into the file:

```
SELECT staging_table, final_table FROM ${td.tablemap_table}
```

4. Adjust the variables in the _export step of the workflow to configure your database, tablemap_table, and email_warnings reciepients.

5. Test it out!
