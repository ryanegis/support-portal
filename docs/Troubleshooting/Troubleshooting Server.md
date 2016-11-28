# Troubleshooting Server

## Isolate the Problem
![Layouts Flow](../images/server-troubleshoot.png)

## Solve the Problem 

*  Start with the client and release.  
*  Ensure that all the steps are followed.  
*  Include any information used in troubleshooting logs, release testing etc that may help identifying the issue.  
*  Any error must be accompanied by the corresponding log entry.  
*  Check the knowledge base first.  
*  Ask for help in the Support Room only.  
*  Add knowledge base article.  

## Server logs
There's a web log console at https://my-uat.papertrail.co.za/web/admin/log.html .

## Rules debugging
If you expect some rule to be applied to created/updated/deleted document and it doesn't it's probably because that 
document doesn't get covered by rule's source conditions. To see if that's the case set `com.egis.index.query` to DEBUG 
in `Services -> Logging` PT admin section - then you'll see the SQL queries and their resultset counts in log console.