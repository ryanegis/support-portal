Health checks should be conduced after evyer new installation, upgrade, custom deployment or major config change

## Conducting Health Checks
1. Monitor the log files under  (`logs`) for any startup or migration errors
1. Check system health using `/health` and ensuring everything is **Good**
1. Log into all applications used (`/web/webapps`, `/web/admin`,`/web/portal`, `/web/capture` etc..) and ensure they load and function correctly
