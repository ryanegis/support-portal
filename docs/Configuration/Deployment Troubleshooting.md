Deployment Troubleshooting

## Diagnostics and Logging

Navigating to:

*  [http://localhost:8080/snapshot](http://localhost:8080/snapshot) will produce a zip file suitable for support diagnosis

*  [http://localhost:8080/web/admin/log.html](http://localhost:8080/web/admin/log.html) to review the current logs. This will also update with new entries.

*  [http://localhost:8080/snapshot/threads](http://localhost:8080/snapshot/threads) to review thread info and CPU usage.

*  [http://localhost:8080/health](http://localhost:8080/health) to check general health.

## Log Levels

To increase the log levels, navigate to  __Services -> Properties -> Logging__  


*  Select the __appropriate log level__ and click __Update__.  
*  Select the log level: `TRACE = highest amount of information`, `ERROR = Lowest amount of info`.  
*  Select whether the increased logging level should remain after restart.It is recommended to not keep DEBUG and TRACE levels for extended period.  
*  Click __Update__.  

Here is a reference for Loggers :   

| Loggers | Description 
| -------- | ---------
| com.egis.index | Info about updates to the search index
| com.egis.index.query | SQL and Search index queries
| com.egis.storage | File operations
| com.egis.kernel.messaging | All messages. (Useful to see what is occurring as a whole)
| com.egis.web.WebErrorHandlerImpl | Show validation errors
| com.egis.conversion | Issues with converting files to PDF and Flash
| com.egis.web.ActionResource | All user actions with parameters

If the loggers are not included in the list, click the **Add button** to add them.

## Rebuilding Indexes

To rebuild all indexes, Navigate to __Services -> Tasks -> Indexing__  

*  Run a __Repair all indexes__ when the indexes are mostly complete and there is only some out of date data.  
*  Run a __Rebuild all indexes__, when there is no index data.  

## Message Queues

To clear / restart message queues:  

*  Navigate to __Services->Messaging__. Select the __message queue__ and
*  Click __Reprocess Failed/Dead__ to reprocess messages.  
*  Click __Clear All__ to clear any messages out of the queue.  

> WARNING: this may produce unexpected results e.g. partial email delivery, failed conversions not being retried etc.

| Loggers | Description 
| -------- | ---------
| IndexUpdate.replicate | Index replications queue
| IndexUpdater.update | Updates to the search indexes
| EmailNotifierImpl.sendQueued | Queued email messages
| Rule.generatePdf | Office -> PDF and Flash conversions
| Rule.* | Any asynchronous rule invocation
| replicate | Data replication
| <store>.write | File replications and online cloud backups

## Debug Mode

To start PaperTrail in Debug Mode in Windows:   
  *  Start the **console_debug.exe** command line app.  

 
 
To start PaperTrail in Debug Mode in Linux:   
  *  Add the following to the **run.sh** just after the java command:   

```javascript
-Xdebug  
-Xrunjdwp:transport=dt_socket,address=8787,server=y,suspend=n  
// Ex : java -Xdebug -Xrunjdwp:transport=dt_socket,address=8787,server=y,suspend=n -Xms512m -Xmx512m -XX:MaxPermSize=196m -classpath $(echo ../build/*.jar ../libs/*.jar . | sed 's/ /:/g'):conf com.egis.Startup
```


## Running Jobs

Any long running job will be listed under **Services -> Jobs**. These include:  

*  Scheduled Rules.  
*  Index Repairs / Rebuilds.  
*  File Store Repairs.  
*  Database Backups / Restores.  

## Failure to Start

If PaperTrail fails to start, follow these steps :  

*   Check that __Java is installed__ and no other service is listening on the default port.  
*   Verify that the __database is up__ and __accepting connections from the configured user/password__.  
*   Verify that user, service run as user __has appropriate permissions to read and write to all directories__ in the installation directory.  
*   Review the log files under logs - specifically **error.log, output.log, server.log**.  

## Low Performance 

*  Check the **memory usage**. Take a snapshot and review the vminfo.txt file, the total GC time should be below 1% of uptime. If the total GC time is higher, it indicates that the heap space should be increased.  
*  If running on a **virtualization platform**, ensure the host has enough resources.  
*  Check to ensure that there is enough **IO capacity for the application**.  
*  Verify that **3rd party application** is not utilizing CPU, RAM and IO resources.  
*  Verify that the Database has **enough RAM and IO capacity**.  
*  Verify that **database indexes are created** and statistics are up to date.  
*  Review thread dump at [http://host:8080/snapshot/threads](http://host:8080/snapshot/threads) for threads with high CPU usage.  
*  Verify best practices.  

## Checking log files

*  Go to [http://host:8080/web/admin/log.html](http://host:8080/web/admin/log.html).  
*  Take a snapshot [http://host/snapshot](http://host/snapshot).  
