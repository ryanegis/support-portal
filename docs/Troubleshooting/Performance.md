### Check underlying system

1.  Is there enough memory?  Their should always be at least 1 - 2GB
    free memory in production to avoid using swap space
1.  Is CPU Usage high? Then check the [CPU Usage guide](cpu-usage)
1.  Check network performance via ICMP ping and Browser developer tools
    network tab - Response times of \< 250ms are good \< 1s are
    acceptable
1.  Check the following resources for identifying lower level
    bottlenecks

-   <http://www.brendangregg.com/usemethod.html>
-   <http://www.brendangregg.com/linuxperf.html>
-   <http://techblog.netflix.com/2015/11/linux-performance-analysis-in-60s.html>

