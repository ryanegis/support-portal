# Database JDBC Configs


### Microsoft SQL Server​

`jdbc:sqlserver://[serverName[\instanceName][:portNumber]];databaseName=<databaseName>[;property=value[;property=value]] `

`jdbc:sqlserver://host;databaseName=test123`

### MYSQL ​

`jdbc:mysql://<database server>:<ports>/<database names>`

### PostgreSQL 

`jdbc:postgresql://<database server>:<port>/<databaseName>`

## SQL
  
SELECT Statement : To Fetch records from an external database to PaperTrail records.  

Format : 
```javascript
   **SELECT \<COLUMNS\> FROM \<TABLENAME\> WHERE
   \<DATABASE INDEX\> = \${\<PAPERTRAIL INDEX\>}**
```

```javascript
   SELECT No_ AS Invoice_No, 
     LEFT(CONVERT(date, "Posting Date"),10) 
     AS Invoice_Date,"Order No_" 
     AS Internal_Order, "Sell-to Customer No_" 
     AS Customer_No,"External Document No_" 
     AS Customer_Order_No, "Shipment Method Code" 
     AS Delivery_Method 
   FROM "SAFINTRA JHB$Sales Invoice Header" 
   WHERE No_ = '${invoice_no}
```

UPDATE Statement : To Update records from an external database to PaperTrail records.  

```javascript
**FORMAT**: **UPDATE \<TABLE NAME\> SET \<DATABASE INDEX\> =
'\<VALUE\>' WHERE \<DATABASE INDEX\> = \${\<PAPERTRAIL
INDEX\>}**
```

```javascript
UPDATE test 
SET Index1 = 'asdf' 
WHERE Invoice_Number = ${Invoice_Number}
```

## Rules for SQL statements

-   Column headers and index values must match index values in
    PaperTrail, otherwise give columns aliases by using the “AS”
    function.
-   All native SQL commands and functions can be used in the statement.
-   Separate columns in SELECT statements by commas.
-   If column names contain spaces, double quotes (“ “) should be used
    to surround the name in order to concatenate the name.

 

## Event 

When to run the SQL Lookup or Update.

