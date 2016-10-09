## Deploying Solutions

1. First take a full [backup](http://docs.papertrail.co.za/Configuration/Backups) if possible.
2. NB: Turn on [Maintenance Mode](http://docs.papertrail.co.za/Reference/maintenance)
> Note A SolutionPack.zip is used in the examples below, however each solution will have it's own filename e.g.  Travel.zip, HR.zip

### Via the CLI

`pt deploy SolutionPack.zip`

### Via the GUI

* Go to the Admin > Services > Tasks > Bulk Import > Deploy Pack
* Select the **SolutionPack.zip**

1. Then conduct a [Health Check](http://docs.papertrail.co.za/Reference/health)
1. Finally turn off [Maintenance Mode](http://docs.papertrail.co.za/Reference/maintenance)