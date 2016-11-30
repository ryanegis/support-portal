Encryption 

# Encrypting files at rest (AES)

*  Add the following to the __papertrail.properties__ file before starting PaperTrail for the first time   
`storage.encrypt=true`

OR

*  Add a new file store under __Services -> File Store__.  
*  Select Software under the __Encrypt__ option.  
*  Enter a __Key size__ e.g. 128, 196, 256.  
*  Enter the __unique key name__ for this store.  
*  The __encryption key will be automatically generated__ on restart and stored obfuscated in the database.  

# Encrypting files in transit (SSL)

*  Create a __Java keystore__.  
*  Copy the keystore to __conf/keystore__.
*  Under __Services -> Properties -> Front End (SSL)__.
*  Check __Enable__.
*  Enter the __keystore password__.
*  Optional: Check __Force SSL__ to ensure all traffic from HTTP is redirected to HTTPS.  
*  Click __Save__.  
*  Restart __PaperTrail__.  

