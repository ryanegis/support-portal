# Ubuntu Linux

## Java

*  Install Oracle Java 8 SDK:
```javascript
add-apt-repository ppa:webupd8team/java --yes   
apt-get update   
echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
apt-get install oracle-java8-installer update-java-alternatives -s java-8-oracle  
```

*  Install JCE Unlimited strength policy files for some AES-256 encryption operations (optional).

*  The policy jar files can be downloaded from [here](http://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html)
```javascript
cp local_policy.jar /usr/lib/jvm/java-8-oracle/jre/lib/security/
cp US_export_policy.jar /usr/lib/jvm/java-8-oracle/jre/lib/security/ 
```


## PostgreSQL 

*  Install PostGres 

```javascript
apt-get install postgresql-9.3
```

(If postgres is not available, follow the instructions at http://wiki.postgresql.org/wiki/Apt to install the repository and then re-try.)

*  Create database and postgres Papertrail user:

```javascript
PSQL_VERSION=9.3 sudo -u postgres psql -c 
"CREATE ROLE papertrail PASSWORD 'papertrail' SUPERUSER CREATEDB CREATEROLE INHERIT LOGIN;"   
sudo -u postgres psql -c 'create database papertrail with owner papertrail;'  
echo host  
papertrail  
papertrail  127.0.0.1/32              
md5 >> /etc/postgresql/$PSQL_VERSION/main/pg_hba.conf /etc/init.d/postgresql restart
```

## Conversion

Install the following dependencies:

*  libreoffice
*  libtiff-tools
*  ghostscript
*  swftools

```javascript
apt-get install libreoffice libtiff-tools ghostscript
```

swftools is not a standard package - To install it, use
```javascript
sudo apt-get -y install libjpeg62 libgif4 sudo apt-get -y install libart-2.0-2 wget -P /tmp/http://archive.canonical.com/ubuntu/pool/partner/s/swftools/swftools_0.9.0-0ubuntu2_amd64.deb chmod a+x /tmp/swftools_0.9.0-0ubuntu2_amd64.deb sudo dpkg -i /tmp/swftools_0.9.0-0ubuntu2_amd64.deb
```

## PaperTrail Service

1) Install PaperTrail
`sh Papertrail_<version>.sh -q`

2) Update the db settings in the `/opt/Papertrail/conf/papertrail/properties`

```javascript
db.database=papertrail db.host=localhost db.pass=papertrail db.user=papertrail db.type=postgresql
```

3) Start papertrail
`/etc/init.d/papertrail start`

