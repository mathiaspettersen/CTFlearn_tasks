# Rubber Duck

**Find the flag! Simple forensics challenge to get started with.**

---

We are given a pictire of a rubber duck where we are to find the flag.

## Solution 1

To find the metadata and exif information, we can use `exiftool` to aid us. Let's run it:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# exiftool RubberDuck.jpg     
ExifTool Version Number         : 12.52
File Name                       : RubberDuck.jpg
Directory                       : .
File Size                       : 197 kB
File Modification Date/Time     : 2023:02:06 05:21:49-05:00
File Access Date/Time           : 2023:02:06 05:21:57-05:00
File Inode Change Date/Time     : 2023:02:06 05:21:57-05:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 72
Y Resolution                    : 72
Comment                         : CTFlearn{ILoveJakarta}.
Profile CMM Type                : Apple Computer Inc.
Profile Version                 : 4.0.0
Profile Class                   : Display Device Profile
Color Space Data                : RGB
Profile Connection Space        : XYZ
```

And we have our flag.

---

## Solution 2

We can also use `strings`. This program searches for all printable objects within a file. We can use `grep -i` for a case insensitive search for "ctf":

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# strings RubberDuck.jpg| grep -i "ctf"
CTFlearn{ILoveJakarta}
```

Where we also get our flag.

---

Flag: `CTFlearn{ILoveJakarta}`
