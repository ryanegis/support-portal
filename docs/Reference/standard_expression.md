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

### Custom Scripts

Custom Groovy code can also be used e.g. to return the first 3 chars of a filename

```groovy
${filename.toLowerCase()[0..3]}
```

See [Groovy JDK](http://docs.groovy-lang.org/docs/latest/html/groovy-jdk)

> Note that due to the `?` and `:` being used to format values they cannot be used in code e.g. 

e.g. ```'${index1 == 'val' ? 'yes' : 'no }``` will not work, use ```${ if (index1 == 'val') then 'yes' else 'no' }```

See [Document Properties](document-properties) for a full list of fields available.


