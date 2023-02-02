# Forensics 101

**Think the flag is somewhere in there. Would you help me find it? https://mega.nz/#!OHohCbTa!wbg60PARf4u6E6juuvK9-aDRe_bgEL937VO01EImM7c**

---

We are firstly greeted with a picture of a minion:

![bilde](https://user-images.githubusercontent.com/70077872/216267508-42c9f8ea-9e50-442d-b0d2-38a02a8ebfb3.png)

As there is a download button on the page, I choose to download it to see if we can extract some more information out of it. A common tool in Linux to aid in stegonography is `exiftool`. This tool prints all the metadata of the image and visualizes any comments if present at all. `exiftool 95f6edfb66ef42d774a5a34581f19052.jpg` yield this result:

![bilde](https://user-images.githubusercontent.com/70077872/216268132-86eb8ad0-4536-4172-a142-d908d868c410.png)

```
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# exiftool 95f6edfb66ef42d774a5a34581f19052.jpg 
ExifTool Version Number         : 12.52
File Name                       : 95f6edfb66ef42d774a5a34581f19052.jpg
Directory                       : .
File Size                       : 9.8 kB
File Modification Date/Time     : 2023:02:01 08:05:10-05:00
File Access Date/Time           : 2023:02:01 08:05:30-05:00
File Inode Change Date/Time     : 2023:02:01 08:05:22-05:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Image Width                     : 236
Image Height                    : 218
Encoding Process                : Progressive DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 236x218
Megapixels                      : 0.051
```

Based on the results there does not seem like there is any interesting here.

Moving on, we can use the `strings` command which prints all the printable characters in an image, file, or document. This allows us to find hiddens message within an image. Running `strings 95f6edfb66ef42d774a5a34581f19052.jpg` yields:

![bilde](https://user-images.githubusercontent.com/70077872/216268750-8eda995d-b259-4efe-a7f1-403a362c6631.png)

As we can see, the flag is hidden within image (the `tail` operand is used to only show the last 10 lines of the files).

Flag: `flag{wow!_data_is_cool}`
