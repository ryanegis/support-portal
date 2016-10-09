## LDAP Configuration  

OpenLDAP 

<pre>Configure User format = <var>uid=${user},o=Directory</var>
</pre>

<div style="background:#eee;border:1px solid #ccc;padding:5px 10px;">**Note:** Active directory will return less results and attributes when using port 3268 vs 389</div>

##   
Multiple LDAP Servers

Configured by addition a set of properties per domain:

`ldap.extra.**_domain1-corp.local_**.host=  
ldap.extra.domain1-corp.local.user=  
ldap.extra.domain1-corp.local.pass=  
ldap.extra._**domain2-corp.local**_.host=  
ldap.extra.domain2-corp.local.user=  
ldap.extra.domain2-corp.local.pass=`

## Synchronizing With LDAP / Active Directory

Check <span class="menu">LDAP -> Auto Create</span> <span class="menu">users</span> to create new users from LDAP when they login  
Check <span class="menu">LDAP -> Auto Sync Groups</span>  to synchronize group membership, this will sync on user create and on the interval specified under <span class="menu">Authentication -> Group Sync Interval</span>

You can also specify a datasource under **Authentication -> Group Sync Provider** e.g. ds:groups 

```SELECT memberOf as groups FROM '@ldap/objectClass=user&SAMAccountName=${filter}```

## Troubleshooting

*   Get the LDAP queries that PaperTrail is executing by increasing the log level:  <span class="filename">com.egis.utils.ldap in </span><8.8.4 or <span class="menu">com.egis.security.ldap</span> in 8.8.4+

<var>DEBUG</var> to see the results of queries  
<var>TRACE</var> to see the actual query being run and authentication requests

*   Use an off the shelf tool to check what options work when connecting:

GUI:  

[http://jxplorer.org/](http://jxplorer.org/)  
[http://www.ldapsoft.com/ldapbrowser/ldapadmintool.html](http://www.ldapsoft.com/ldapbrowser/ldapadmintool.html)  

CLI:  

`ldapsearch -h 172.16.237.131 -D "administrator@corp.egis-software.com" -w password -b "cn=users,dc=corp,dc=egis-software,dc=com" -s sub "(&(objectClass=user)(mail=*))" '*'`  

Use tcpdump or wireshark to capture ldap queries and results at the protocol level.  

*   Adjust the LDAP query string in <span class="menu">Services -> Properties -> LDAP</span> as appropriate