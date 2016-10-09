# Installation and Configuration

## Installation
To install PaperTrail you will first need to install the prequisties:

* Java 8 SDK
* PostgreSQL or MS SQL on localhost or remote server
* LibreOffice

1. Download and run the installer - this can be done silently using the **-q** option
2. Access the installation wizard at **http://localhost:8080** 
3. When complete conduct a [Health Check](http://docs.papertrail.co.za/Reference/health)  

See [Windows](http://docs.papertrail.co.za/Installation/Windows), 
 [Linux](http://docs.papertrail.co.za/Installation/ubuntu-linux), [MacOSX](http://docs.papertrail.co.za/Installation/MacOSX) 

## Upgrades

1. Run a full [backup](http://docs.papertrail.co.za/Configuration/Backups)  
Rename the `Papertrail` installation folder according to date of upgrade and current version, i.e. `Papertrail_2013-03-04_r864` as it allows for simplified rollbacks
1. Run the installer  
(If applicable also reconfigure the service under the correct user account)
1. Turn on [maintenance mode](http://docs.papertrail.co.za/Reference/maintenance)
1. Start PaperTrail and Conduct a health check
1. Turn off [maintenance mode](http://docs.papertrail.co.za/Reference/maintenance)

#### More Links
[Service options](http://docs.papertrail.co.za/Configuration/service)  
[Backups](http://docs.papertrail.co.za/Configuration/Backups)  
[Replication](http://egis.papertrail.co.za/wiki/Installation/Replication)  
[LDAP / Active Directory](http://egis.papertrail.co.za/wiki/Integration/LDAP)


