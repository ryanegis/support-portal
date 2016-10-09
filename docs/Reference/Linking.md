## Manipulating the linking critera

### Linking Documents On Numbers Only
###### Specific node links can be added to only search the digit portion of the index value using IF ELSE logic, i.e.
        <Destination Node>/recursive=true&<Destination Index>=${if (<Source Index> == null) "" else <Source Index>.find("\\d+")}

###### Destination Node: <Root node/child node/>
###### recursive=true: when searching over multiple child nodes
###### Destination Index: Index field you want to link to
###### Source Index: Index field on node you're linking from
###### ${if (<Source Index> == null): If source index has no Value
###### "" else <Source Index>.find("\\d+")}: Find matching Numeric Value
---
### Linking on Numeric with custom field Order_No
eg. Order_No = 12345

       <Destination Node>/recursive=true&Order_No=${if (Order_No == null) "" else Order_No.find("\\d+")}
### Linking on Alphanumeric with custom field Order_No
eg. Order_No = PO12345

      "" else Order_No.find("\\w+")}
### Linking on Alphanumeric, Space, Numeric with custom field Order_No
eg. Order_No = PO 12345

     "" else Order_No.find("\\w+\\s+\\d+")}
     
### Regex Examples eg.
###### **\\w+**    : All alphanumeric values

###### **\\W**     : A non-word character: [^\w]

###### **\\d+**    : All numeric values

###### **\\D**     : A non-digit: [^0-9]

###### **\\s**     : A whitespace character
