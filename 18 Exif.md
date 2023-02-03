# Exif

**If only the password were in the image?**

**https://mega.nz/#!SDpF0aYC!fkkhBJuBBtBKGsLTDiF2NuLihP2WRd97Iynd3PhWqRw You could really ‘own’ it with exif.**

---

In this task we are given a picture of a password in which we are to find the hidden password within the image. As with previous tasks, `exiftool` is excellent at outputting exif data and meta data. Let's use this to extract the info:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# exiftool Computer-Password-Security-Hacker\ -\ Copy.jpg                
ExifTool Version Number         : 12.52
File Name                       : Computer-Password-Security-Hacker - Copy.jpg
----
----
Components Configuration        : Y, Cb, Cr, -
Flashpix Version                : 0100
Owner Name                      : flag{3l1t3_3x1f_4uth0r1ty_dud3br0}
GPS Latitude Ref                : South
GPS Longitude Ref               : East
Quality                         : 60%
DCT Encode Version              : 100
APP14 Flags 0                   : [14], Encoded with Blend=1 downsampling
APP14 Flags 1                   : (none)
Color Transform                 : YCbCr
Image Width                     : 660
```

And we can collect our flag.

---

Flag: `flag{3l1t3_3x1f_4uth0r1ty_dud3br0}`
