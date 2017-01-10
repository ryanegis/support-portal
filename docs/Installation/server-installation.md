# Installation and Configuration

## Installation
To install PaperTrail you will first need to install the prerequisites:

* Java 8 SDK
* PostgreSQL, MySQL or MS SQL on localhost or remote server (You will require the IP address of the database server, the TCP port that the server is listening on as well as administrative credentials to the database)
* LibreOffice

Once you have the prerequisites : 

1.  Create a new database (e.g. `papertrail`) within the installed database application on the host server
2.  Download and run the installer - this can be done silently using the **-q** option
3.  Access the installation wizard at **http://localhost:8080**  
4.  You will need to provide the following details:<br>
    4.1  The desired HTTP port for the frontend (`8080` in this example)<br>
    4.2  The IP address, TCP port and administrative credentials of the database host server (if the database is installed on the same server, use `localhost` as DB Host)<br>
    4.3  Database name (`papertrail` in this example; this is case sensitive)
5.  When complete, conduct a [Health Check](../Reference/health)  

See [Windows](Windows), 
 [Linux](ubuntu-linux), [MacOSX](macosx) 

## Upgrades

1. Run a full [backup](../Configuration/Backups)  
Rename the `Papertrail` installation folder according to date of upgrade and current version, i.e. `Papertrail_2013-03-04_r864` as it allows for simplified rollbacks
1. Run the installer  
(If applicable also reconfigure the service under the correct user account)
1. Turn on [maintenance mode](../Reference/maintenance)
1. Start PaperTrail and Conduct a health check
1. Turn off [maintenance mode](../Reference/maintenance)

#### More Links
[Service options](service)  
[Backups](../Configuration/Backups)  
[Replication](Replication)  
[LDAP / Active Directory](../Integration/ldap-ad)


