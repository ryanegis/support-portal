**EasyPDF deployment and configuration** ========================================

The following combination of software will need to be installed on the EasyPDF server 
=======================================================================================

·       Windows Server 2008 32/64 bit.

·       PaperTrail 32 bit (latest release available).

·       EasyPDF version 6/7 32 bit.

·       EasyPDF PaperTrail Addon 32 bit (EasyPDF 6 requires Addon r5453
and EasyPDF 7 requires Addon r8738).

·       Microsoft Office 2010.

·       Any other native applications that may need to be converted to
PDF by EasyPDF (i.e. AutoCAD).

 

**Note : UAC should be disabled on the machine before any software is
installed.**

**Local installation** (Both PaperTrail and EasyPDF running on same
host) :

1.     Install EasyPDF application.

2.     Install PaperTrail release.

3.     Install EasyPDF PaperTrail Addon.

4.     Set the “BCL easyPDF SDK 7 Loader” and “Papertrail” services to
run as the same account which should be granted administrative
permissions.

5.     Start PaperTrail and confirm that installation was successful.

6.     Add the following line to the easypdf.properties file and restart
PaperTrail thereafter :

easypdf.word.nativeOfficePDF=true

7.     Import test documents to confirm that all is set up correctly.

** **

**Remote installation** (PaperTrail and EasyPDF running on separate
hosts) :

·       **EasyPDF server** :

1.     Install EasyPDF application.

2.     Install PaperTrail release.

3.     Install EasyPDF PaperTrail Addon.

4.     Set the “BCL easyPDF SDK 7 Loader” and “Papertrail” services to
run as the same account which should be granted administrative
permissions.

5.     Start PaperTrail and confirm that installation was successful.

6.     Add the following line to the easypdf.properties file and restart
PaperTrail thereafter :

                 easypdf.word.nativeOfficePDF=true

7.     Import test documents locally to confirm that all is set up
correctly.

 

·       **PaperTrail application server** :

1.     Once PaperTrail is up and running, set the below properties in
the papertrail.properties file to enable remote conversions :
```
conversion.filetype.\*=remote
conversion.filetype.pdf=pdf
conversion.remote.host=http://host1:8080
```
2.     Import test documents on application server to confirm that all
is set up correctly.

**Troubleshooting**

If any conversion issue are being experienced, create a .vbs
file which can be run to test conversions outside of PaperTrail. The
paths in the properties are input and output files, and should be
configured accordingly :
```vbscript
Set oPrinter = CreateObject("easyPDF.Printer.7")
Set oPrintJob = oPrinter.PrintJob
oPrintJob.PrintOut "C:\\test.txt", "C:\\output.pdf"
```
 

Another way to test the conversions is to navigate to
*C:\\Users\\Public\\Documents\\BCL Technologies\\easyPDF SDK
7\\Samples\\Visual C\#\\EasyPDFPrinterTest* and then running
EasyPDFPrinterTest.exe. This will allow you to select an input document
to convert and specify the output path of the PDF.

 

For any more information, the user manual can be accessed at
<http://www.pdfonline.com/easypdf/sdk/usermanual/>

 

 

