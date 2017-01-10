# Installation and Configuration

## Installation
To install PaperTrail you will first need to install the prerequisites:

* Java 8 SDK
* PostgreSQL or MS SQL on localhost or remote server
* LibreOffice

Once you have the prerequisites : 

1.  Create a new database (e.g. "PaperTrail") within the installed database application on the host server
2.  Download and run the installer - this can be done silently using the **-q** option 
3.  You will need to provide the database name ("PaperTrail" in this example; this is case sensitive) as well as administrative credentials to the database application to complete the installation process
4.  Access the installation wizard at **http://localhost:8080**  
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


