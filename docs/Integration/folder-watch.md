## Normal

Any file dropped into the Watched Folder will be imported into the specified node. 

## CSV

PaperTrail will scan the watched folder for any CSV file. The CSV will then be processed and matching files will be imported with their indexes.  

<span class="filename">Sample.csv</span>  

	filename,index1,index2  
	Sample1.txt,value1,value2  
	Sample2.txt,value3,value4

<span class="filename">Sample1.txt</span>  
	
	Just some content in Sample1   

<span class="filename">Sample2.txt</span>  
	
	Just some content in Sample2  

In this example `Sample1.txt` and `Sample2.txt` would get imported with the index values (value1,value1) and (value3,value4) respectively 

## Import and Sync

Import ant sync works by creating a temporary staging table to contain metadata coming from external systems - This metadata is dropped off in a XML or CSV file. A mapping file is used to map and reformat the data in these files, the mapping file takes the format of a CSV file imported into PaperTrail with the following columns:  

<table border="1" cellpadding="1" cellspacing="1" style="width: 100%;">

<thead>

<tr>

<th scope="col">Column</th>

<th scope="col">Description</th>

</tr>

</thead>

<tbody>

<tr>

<td>name</td>

<td>CSV Only - The name of the CSV column</td>

</tr>

<tr>

<td>xpath    </td>

<td>XML Only - The XPATH to use </td>

</tr>

<tr>

<td>index</td>

<td>The PaperTrail node index name</td>

</tr>

<tr>

<td>expression</td>

<td>Optional - A Groovy standard expression used to filter or reformat the data   
e.g  
<var>PREFIX-${value}</var> - Add a prefix to the value  
<var>${value.find('\d+')}</var> - Extract only digits using a regular expression</td>

</tr>

<tr>

<td>format</td>

<td>Optional - The date format of the value in the CSV/XML - PaperTrail will parse the date using this format and then reformat it using the configured system wide format for consistency.</td>

</tr>

</tbody>

</table>

<span class="filename">Mapping.csv</span>

	name,index,expression,format  
	index 1,filename,,  
	index 2,index2,,  
	index 3,index3,${value}-smith,  
	date 3,date3,,dd/MM/yyyy

<span class="filename">Data.csv</span>  

	index 1,index 2,date 3,index 3  
	file1,oncreate,01/01/2015,john

<span class="filename">XML Mapping.csv</span>

	xpath,index,format,expression  
	/Data/index1/@value,filename,  
	/Data/index2/text(),index2,  
	/Data/index3/text(),index3,,${value}-smith  
	/Data/date3/text(),date3,MM/dd/yyyy,

<span class="filename">Data.xml</span>

    <?xml version="1.0"?>
    <Data>
        <index1 value="file1"/>
        <index2>onupdate</index2>
        <index3>john</index3>
        <date3>01/01/2015</date3>
    </Data>

## Structured

Structured imports import raw textual data and overlay it onto a PDF Template.   
A Datamap file is used to map blocks of text to fields in the PDF.   
The raw data can optionally be processed through a executable (exe) or a groovy script to format it, so that the datamap can extract the content correctly. 

## Update 

Deprecated in favour of Import and Sync CSV or XML

## Attach To Form

This will spawn the specified form and attach the document dropped in the watched folder to the form. 

## Document Archive 

This will import a complete document with all versions, indexes, notes, etc. Document Archives are created using Bulk Export or an Auto Export rule.