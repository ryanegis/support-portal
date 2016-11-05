# Installation and Configuration

## Installation
To install PaperTrail you will first need to install the prerequisites:

* Java 8 SDK
* PostgreSQL or MS SQL on localhost or remote server
* LibreOffice

Once you have the prerequisites : 

1.  Download and run the installer - this can be done silently using the **-q** option  
2.  Access the installation wizard at **http://localhost:8080**  
3.  When complete, conduct a [Health Check](../Reference/health)  

See [Windows](Windows), 
 [Linux](http://docs.papertrail.co.za/Installation/ubuntu-linux), [MacOSX](http://docs.papertrail.co.za/Installation/MacOSX) 

## Upgrades

1. Run a full [backup](../Configuration/Backups)  
Rename the `Papertrail` installation folder according to date of upgrade and current version, i.e. `Papertrail_2013-03-04_r864` as it allows for simplified rollbacks
1. Run the installer  
(If applicable also reconfigure the service under the correct user account)
1. Turn on [maintenance mode](../Reference/maintenance)
1. Start PaperTrail and Conduct a health check
1. Turn off [maintenance mode](../Reference/maintenance)

#### More Links
[Service options](../Configuration/service)  
[Backups](../Configuration/Backups)  
[Replication](http://egis.papertrail.co.za/wiki/Installation/Replication)  
[LDAP / Active Directory](http://egis.papertrail.co.za/wiki/Integration/LDAP)


