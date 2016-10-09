## Solution Packs

Solution packs provide a simplemechanism to export the configuration and deployment from one server to another

### Exporting

To export a solution pack browse to **/solutions/export/** while logged on as an adminstrator - A solution pack (.zip) file will be downloaded with the following contents:

* Node Structure
* Templates
* Forms
* System/scripts/
* System/templates
* Workflows

The .zip can be manually edited and updated as required.

### Importing

To import a solution pack drop it into the **plugins** folder or import via the CLI:  
`pt deploy solution-pack.zip`
