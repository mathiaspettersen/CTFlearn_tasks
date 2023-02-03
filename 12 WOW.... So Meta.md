# WOW.... So Meta

**This photo was taken by our target. See what you can find out about him from it. https://mega.nz/#!ifA2QAwQ!WF-S-MtWHugj8lx1QanGG7V91R-S1ng7dDRSV25iFbk**

---

This task asks us to find out information from the photo. As with previous tasks, we have several stegonography tools available, such as `exiftool`. This tool prints out the exif information in an image, or metadata if you like. Let's try to run `exiftool 3UWLBAUCb9Z2.jpg`:


```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# exiftool 3UWLBAUCb9Z2.jpg 
ExifTool Version Number         : 12.52
File Name                       : 3UWLBAUCb9Z2.jpg
Directory                       : .
File Size                       : 104 kB
File Modification Date/Time     : 2023:02:03 02:59:28-05:00
File Access Date/Time           : 2023:02:03 02:59:36-05:00
File Inode Change Date/Time     : 2023:02:03 02:59:36-05:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Current IPTC Digest             : dbad0204d16a63027791298bc460859a
Coded Character Set             : UTF8
Application Record Version      : 2
Digital Creation Time           : 16:45:55
Digital Creation Date           : 2014:12:27
Time Created                    : 16:45:55
IPTC Digest                     : dbad0204d16a63027791298bc460859a
Exif Byte Order                 : Big-endian (Motorola, MM)
Orientation                     : Horizontal (normal)
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Software                        : Photos 1.5
Modify Date                     : 2014:12:27 16:45:55
Exif Version                    : 0221
Date/Time Original              : 2014:12:27 16:45:55
Create Date                     : 2014:12:27 16:45:55
Components Configuration        : Y, Cb, Cr, -
Light Source                    : Tungsten (Incandescent)
Flashpix Version                : 0100
Color Space                     : sRGB
Exif Image Width                : 4002
Exif Image Height               : 1536
Scene Capture Type              : Standard
Sharpness                       : Hard
Padding                         : (Binary data 2060 bytes, use -b option to extract)
XMP Toolkit                     : XMP Core 5.4.0
Creator Tool                    : Photos 1.5
Date Created                    : 2014:12:27 16:45:55
Warning                         : [minor] Fixed incorrect URI for xmlns:MicrosoftPhoto
Camera Serial Number            : flag{EEe_x_I_FFf}
Image Width                     : 800
Image Height                    : 307
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 800x307
Megapixels                      : 0.246
Date/Time Created               : 2014:12:27 16:45:55
Digital Creation Date/Time      : 2014:12:27 16:45:55

```

As we see, we get our flag by running that command.

---

Flag: `flag{EEe_x_I_FFf}`
