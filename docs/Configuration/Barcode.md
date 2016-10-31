Barcode Recognition Setup
-------------------------

Setup an extractFromBarcode rule on at he appropriate node
Install the Softek SDK**  Download the latest version from:  
[Windows SDK
v8.1.2](http://http://softeksoftware.co.uk/download/barcode_sdk/windows/softek_barcode_sdk_8_1_2.zip)  
 [Linux SDK v8.1.2](http://bardecode.com/barcode_linux.tar.gz)

Libraries need to be copied to /usr/lib/java, /usr/lib/ or
C:\\Windows\\System32 or to where the java.library.path is pointing\


For a list of all versions goto http://www.bardecode.com/en1/quick-download/ although a different
license may need to be loaded via the License property

### Supported Barcodes

*  Codabar also known as Code 2 of 7, Codeabar, Ames Code, NW-7 and Monarch (ReadCodabar)
*  Code 128 Symbol Sets A, B and C (ReadCode128)
*  Code 128 Short Format (ReadShortCode128)
*  Code 2 of 5 Datalogic (ReadCode25ni)
*  Code 2 of 5 Iata1 (ReadCode25ni)
*  Code 2 of 5 Iata2 (ReadCode25ni)
*  Code 2 of 5 Industrial (ReadCode25ni)
*  Code 2 of 5 Interleaved (ReadCode25)
*  Code 2 of 5 Matrix (ReadCode25ni)
*  Code 3 of 9 (ReadCode39)
*  Code 3 of 9 Extended (ReadCode39 and ExtendedCode39)
*  Code 93 (ReadCode93)
*  EAN-8, European Article Number/International Article Number (ReadEAN8)
*  EAN-13 and UPC-A, European Article Number/International Article Number (ReadEAN13)
*  GS1-128, UCC-128, EAN-128 (ReadCode128)
*  GS1-Databar (please see 2-D section below)
*  Patch Code Symbols (ReadPatchCodes)
*  UPC-A, Universal Product Code (ReadEAN13 and ReadUPCA)
*  UPC-E, Universal Product Code (ReadUPCE)
*  QR-Code (ReadQRCode)
*  Data Matrix ECC200 sizes 8x8 to 144x144 (ReadDataMatrix)
*  GS1-Databar
*  Micro-PDF-417 (ReadMicroPDF417)
*  PDF-417, Portable Data File (ReadPDF417)

Properties
----------

**AllowDuplicateValues**  Barcodes containing the same text on the same
page

**BarcodesAtTopOfPage**  Search from the top of a page downwards

**Code128Lenient**  relax some of the requirements for Code 128 barcodes

**Code25Checksum**  Code 25 barcodes include checksum character

**Code25MinLengthOccurrence**  control for false positive readings for
Code 25 barcodes

**Code39Checksum**  Code 39 barcodes include checksum character

**Code39MaxRatioPcnt**  set the max ratio between the wide and narrow
bars

**Code39NeedStartStop**  Require start and stop \* characters for a Code
39 barcode

**ColorProcessingLevel**  control the amount of processing time spent
reading barcode values from color images

**ColorThreshold**  Contrast setting for color images

**ConvertUPCEToEAN13**  Output UPC-E barcodes in EAN-13 format

**DatabarOptions**  set the advanced options for reading GS1 Databar
barcodes

**DataMatrixAutoUTF8**  Automatic detection of UTF8 data in datamatrix
barcodes

**Despeckle**  Clean up images containing specks of black and white

**Encoding**  character encoding for barcode values

**ErrorCorrection**  Correct errors in barcodes

**ExtendedCode39**  Read Code 39 barcodes in the extended symbol set

**GammaCorrection**  gamma correction value for color images

**LineJump**  Frequency of line sampling in an image

**MaxLength**  Maximum string length of a barcode

**MaxRectOverlap**  maximum number of threads

**MaxThreads**  maximum overlap for bounding rectangles

**MedianFilter**  Apply a median filter to the image

**MedianFilterBias**  Lighten/darken an image during a median filter

**MinLength**  Minimum string length of a barcode

**MinOccurrence**  Minimum number of hits needed to read a barcode

**MinSeparation**  Minimum distance between similar barcodes

**MinSpaceBarWidth**  Minimum width of a space in a barcode

**MultipleRead**  Read more than one barcode

**NoiseReduction**  Clean up images containing un-wanted black marks

**PageNo**  Page number to scan in an image

**Pattern**  Regular expression to search for

**PDF417AutoUTF8**  Automatic identification of UTF8 data in PDF-417
barcodes

**Pdf417ChannelMode**  Control the way macros are handled in PDF417
barcodes

**Pdf417MacroEscapeBackslash**  Handling of back slash characters in
PDF417 macros

**Photometric**  Photometric interpretation for a black and white bitmap

**PrefOccurrence**  Preferred number of hits for a barcode

**QRCodeAutoUTF8**  Automatic identification of UTF8 data in QrCode
barcodes

**QRCodeBWAutoMedianFilter**  automatic use of median filter for QrCode
detection

**QuietZoneSize**  Size of quiet zone around a barcode

**ReadCodabar**  Read Codabar barcodes

**ReadCode128**  Read Code 128 barcodes

**ReadCode25**  Read Code 25 (interlaced) barcodes

**ReadCode25ni**  Read Code 25 (non-interlaced) barcodes

**ReadCode39**  Read Code 39 barcodes

**ReadDatabar**  Read GS1 Databar barcodes

**ReadDataMatrix**  Read Data Matrix barcodes

**ReadEAN13**  Read EAN-13 barcodes

**ReadEAN8**  Read EAN-8 barcodes

**ReadMicroPDF417**  Read micro-PDF-417 barcodes

**ReadNumeric**  Only read numeric barcodes

**ReadPatchCodes**  Read Patch Codes

**ReadPDF417** Read PDF-417 barcodes

**ReadShortCode128**  Read short Code 128 barcodes

**ReadUPCA** Read UPC-A barcodes

**ReadUPCE** Read UPC-E barcodes

**ReportUnreadBarcodes** Report barcodes that could not be decoded

**ScanDirection**  Orientation to scan for a barcode

**ShortCode128MinLength**  Minimum length for a barcode of type
"SHORTCODE128"

**ShowCheckDigit**  Display check digits

**SkewedDatamatrix**  Check for skewed linear barcodes

**SkewedLinear**  Check for skewed datamatrix barcodes

**SkewLineJump**  Frequency of line sampling for skewed barcodes

**SkewTolerance**  Search for barcodes at an angle to horizontal or
vertical

**TifSplitMode**  Controls how a TIF file should be split

**TifSplitPath**  Split a TIF file into smaller parts based on the
location of barcodes in the image

**TimeOut**  Set a time out for barcode detection

**UseFastScan**  Do a quick scan prior to a deeper search.

**UseOverSampling**  Another method for cleaning up 'noisy' images

**WeightLongerBarcodes**  boost the hit count for longer barcodes.
