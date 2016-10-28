## Web Scan

### Web Scan Profile Settings

#### separation

type - *string*

Possible values:

1. **None** - combine all images to single PDF file;

2. **Page** - put each image to new PDF file, so each PDF file will contain single page;

3. **Blank** - create new PDF when blank image appeared. For instance, there is images sequence:

  ```
  image1, image2, blank image, image3, image4, image5, blank image, image6
  ```

  As a result of **Blank** separation, scan addon will return 3 PDF files: 2 pages (image1, image2), 3 pages (image3, image4, image5) and 1 page (image6).

4. **Barcode** - create new PDF when image with unique barcode appeared. For instance, there is images sequence:

  ```
  image1, image with barcode1, image2, image3, image with barcode3
  ```

  As a result of **Blank** separation, scan addon will return 3 PDF files: 1 page (image1), 3 pages (image with barcode1, image2, image3) and 1 page (image with barcode3).

#### resolution

type - *object*

Fields:

1. **x** - integer, *x* value of resolution. Common possible values: 100 - 600

2. **y** - integer, *y* value of resolution. Common possible values: 100 - 600

3. *units* - string, measure units for *x* and *y*. Possible values:

  * Inches
  
  * Centimeters
   
  * Points
   
  * Pixels
   
**Important note:** list of supported values for *resolution* may vary depending on scanner model
   
#### compressionMode
   
type - *string*
   
Common values:
   
1. **None** - don't use any compression mode;
   
2. **Jpeg** - intended for the compression of color photographs
   
3. **Lzw** - a compression licensed by UNISYS
   
4. **Jbig** - intended for bi-tonal and grayscale document images
   
5. **Png** - Portable Network Graphic
   
6. **Group4** - CCITT Group 4 fax encoding, intended for document images

**Important note:** list of supported values for *compressionMode* may vary depending on scanner model

#### pdfDecoder

type - *object*

Fields:

1. **resolution** - integer, resolution at which to render a PDF page. Minimum - 1, maximum - 3600.

#### barcodeSettings

type - *object*

See (Barcode Configuration)[http://support.papertrail.co.za/Configuration/Barcode/] for list of supported properties

### Examples

Split images into PDF files by barcode and use 300x300px scan resolution

```
{
  "separation": "Barcode",
  "resolution": {
    "x": 300,
    "y": 300,
    "units": "Pixels"
  }
}
```

Create single PDF file from scanned images and render it with 80 resolution

```
{
  "separation": "None",
  "pdfDecoder": {
    "resolution": 80
  }
}
```
