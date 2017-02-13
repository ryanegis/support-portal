# eSign

### Requirements and Preparation
* Ensure that the client is licensed for the eSign module
* Administration > Properties > Front End:
  * Ensure that `pdf_sign`, `upload_for_signature` are not listed under Disabled Actions
  * If anything is changed here, a restart of the PaperTrail service is required
* Administration > Properties > eSignature:
  * Set the `eSignature Upload Node` (ensure that users that will be designing templates have sufficient permissions here)

### Creating a Design and a Template
* Log into the V2 interface (`localhost:8080/web/portal`)
* Select `eSign`
* Click `Upload for Signature` and select the source document
* In the new tab (ensure that pop-ups are not blocked), set fields etc and then add the Signature box(es)
* Signatures can be open to anyone (leave the `Name` field blank), or restricted to a specific user via the `Name` field
* When done, click the disk (Save) icon to save the design
  * This saves the form design under the e`Signature Upload Node` defined in the Requirements and Preparation stage.
* Then click the Settings cog and `Save as template`
  * Name the template and select the node that this template will reside in. The node must either be a Cabinet or a Folder; Divisions are not allowed. This is the location where the created forms will save to

### Signing Documents
* V2 Interface: Navigate to `eSign` and select the form > `New Request`
* Classic Interface: `Tools > New Form`
* Signed documents will be created in the node specified under `Save as template`
