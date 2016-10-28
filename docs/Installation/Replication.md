# Replication

## Clean Install

* Install PaperTrail on master.
* Startup master.
* Shutdown master and create db dump.
```java
	db.replication.enable=true db.replication.external.id=master db.replication.group.id=master file.replication.upstream=http://slave:8080
```
* Enable replication on the master and start PaperTrail.
* Restore master dump on slave and copy over repository.
* Enable replication on slave and start PaperTrail.
```java
db.replication.enable=true db.replication.external.id=slave db.replication.group.id=slave db.replication.master=replication1 file.replication.upstream=http://master:8080
```

## Upgrade

* Shutdown PaperTrail on master and slave.
* Upgrade PaperTrail on master and startup.
* Upgrade PaperTrail on slave and startup.


## Filestore Replication


When setting up file store replication to a secondary PaperTrail installation, follow the below points:
 
* When entering the URL to the secondary PT, include "/store" at the end of the PT URL e.g. http://<hostname>:<port>/store
* Always tick the "Async" option. Not only is this option helpful for slow connections, but it also manages imports if the secondary PT is not available.
