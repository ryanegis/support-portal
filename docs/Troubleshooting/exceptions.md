 `java.io.IOException: Cannot run program "pg\_dump": CreateProcess
error=2`  
 The system cannot find the file specified
Add the Postgresql/bin directory to the System PATH environment
variable


`java.io.IOException: Cannot run program "mysql\_dump"`  
  The system cannot find the file specified 
Add the MySQL/bin directory to the System PATH environment variable\
  
`JDBCExceptionReporter [:] Cannot get a connection, pool error Timeout
waiting for idle object Database connection pool is exhausted,`  
  - Check for database connection leak warning messages in the log files
beforehand  
  - Check database lookup configurations  
  
`failed <SocketConnector@0.0.0.0>:80:
[java.net](http://java.net/).BindException: Permission denied`

 To run PaperTrail on port 80 you need to be root, change
http.port=8080\
  
