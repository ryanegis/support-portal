# High Availability

## Replication (Master – Master)

1.  Use the **New Replication Installation** option in the wizard on both the master and slave.  
2.  Check **Master** on the primary node.  
3.  The master node is responsible for **triggering timeouts**, running **scheduled rules** etc.  

## Replicated installation.

To convert a standalone installation to a replicated installation, follow these steps:  

*  Stop PaperTrail and create a **database backup**.  
*  Configure the following properties in **papertrail.properties** on the master

```javascript
index.upstream=http://slave:8080
replication.upstream=http://slave:8080  
file.replication.upstream=http://host:8080  
replication.master=true  
replication.increment=2  
replication.offset=1  
db.identity.override=true # for sql server replication only  
```

*  Configure these properties on the slave:  

```javascript
index.upstream=http://master:8080  
replication.upstream=http:// master:8080
file.replication.upstream=http:// master:8080  
replication.master=false  
replication.increment=2  
replication.offset=2  
db.identity.override=true # for sql server replication only  
```

*  Start up the master
*  Wait a few minutes and start up the slave

## Clustering

*  Select the **New Clustering** installation from the wizard:  

OR

*  Add these properties to the **papertrail.properties**  
```javascript
index.upstream=http://slave:8080   
cluster.enable=true   
storage.upstream=http://slave:8080  
```
*  Restart PaperTrail.

> Note: Clustering requires a low latency (<1ms), reliable (preferably dual path redundant network) network connection to function correctly.  Replication can be used in WAN environments.

Ensure that port `5701` is open for inbound traffic from all cluster members to all cluster members. See [Hazelcast Ports](http://docs.hazelcast.org/docs/3.3/manual/html/ports.html)
