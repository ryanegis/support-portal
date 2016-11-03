# Standard Expressions

Expressions allow for values to be substituted at runtime. As an example of how expression values are substituted, if you are given a document with the following index values:

```javascript
createdDate = 2009-03-15  
filename = test.doc  
title = sample title  
docid = 123  
```

If the basic syntax is `${lookup?defaultValue:format}` then this is how you would read the expression results using the values in the table in Document properties / indexes on page :

| Standard Expression        | Output
| ------------- |-------------
| ${createdDate:yyyy}   | 2009 
| ${createdDate:yyyy-MM-dd}   | 2009-13-15 
| ${createdDate:yyyyMM} | 200903 
| ${filename} - ${title} ($docid})   | test.doc - sample (123) 

