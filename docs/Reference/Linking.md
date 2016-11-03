## Manipulating the linking critera

### Linking Documents On Numbers Only
Specific node links can be added to only search the digit portion of the index value using IF ELSE logic, i.e.
`<Destination Node>/recursive=true&<Destination Index>=${if (<Source Index> == null) "" else <Source Index>.find("\\d+")}`

### Linking on Numeric with custom field Order_No
eg. Order_No = 12345

`<Destination Node>/recursive=true&Order_No=${if (Order_No == null) "" else Order_No.find("\\d+")}`

### Linking on Alphanumeric with custom field Order_No
eg. Order_No = PO12345

`"" else Order_No.find("\\w+")`
### Linking on Alphanumeric, Space, Numeric with custom field Order_No
eg. Order_No = PO 12345

`else Order_No.find("\\w+\\s+\\d+")`
