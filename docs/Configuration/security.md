Security Settings
=================

PaperTrail can be run in 4 distinct security modes:

###  Low (Default)

Suitable for intranet based deployments without confidential data 

### Medium


Access to the various API's used for replication and clustering is
restricted based on Trusted Server entries, some of the endpoints
restricted include:
  

-   conversion
-   signature/upload
-   index/replication
-   store
-   replicate

### High 

Includes all the restrictions of Medium and:
  

-   disables the /script/console endpoint (used by
    /web/admin/console.html and pt script CLI)
-   prevents updates to the following properties via the web UI, they
    need to be set via papertrail.properties file:

 

    ldap.host
    waffle.enable
    spnego.enable
    spnego.kdc
    smtp.debug
    email.spool
    smtp.host
    sms.url
    web.login.sms.otp
    index.store
    http.ssl
    disabled.audits
    disabled.entity.audits
    openoffice.path
    tiff2pdf.process
    pdf2swf.process
    security.level

### Very High

 Includes all the restrictions of High and further restricts:

-   Loading jar files via System/jars folder
-   Loading scripts via System/scripts folder
-   Loading UI plugins via System/plugins folder
-   Scripted data sources
-   runScript, dbLookup and commandLineProcess rules
-   Custom options in Meta Model Fields
-   PQL Expressions

