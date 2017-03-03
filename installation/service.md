### Configuring service settings 
  

| OS        | Configuration Applied in
| ------------- |-------------
| Linux   | /opt/Papertrail/run.sh 
| Windows | service.vmoptions

###  Configuration Options 


| Option        | Description | Example
| ------------- |------------- | -------
| -Xmx    | Max memory | -Xmx2048M
| -Xms    | Min memory | -Xms2048M
| -Xss    | Thread Stack Size | -Xss1m
| -D*systemProperty* | -Dhttp.proxyPort=8800

### System Properties

System properties can either be set as startup configuration option using `-DsystemProperty=value`, or in the `conf/papertrail.properties` file:

| System Property | Description | Example
| ----------------| ------------| -------
| java.net.useSystemProxies||true
| http.proxyHost|HTTP Proxy Host|squid
| http.proxyPort|HTTP Proxy Port|8800
| http.proxyUser|    |
| http.proxyPassword|     |
| http.nonProxyHosts|    |`localhost|127.0.0.1|10.*.*.*|*.foo.co|etc`
| socksProxyHost|     |
| socksProxyPort|     |
| java.net.socks.username|     |
| java.net.socks.password|   | 
