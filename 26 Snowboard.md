# Snowboard

**Find the flag in the jpeg file. Good Luck!**

---

We are given a .jpeg of a man standing on a snowboard, and we have to find the flag.

Starting with the low-hanging fruit, we try to run exiftool on the jpeg:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# exiftool Snowboard.jpg                                                 
ExifTool Version Number         : 12.55
File Name                       : Snowboard.jpg
Directory                       : .
File Size                       : 106 kB
File Modification Date/Time     : 2023:02:21 11:53:44-05:00
File Access Date/Time           : 2023:02:21 11:53:44-05:00
File Inode Change Date/Time     : 2023:02:21 11:53:44-05:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Comment                         : CTFlearn{CTFIsEasy!!!}.
```

We actually get a flag, but it is unfortunately not the right one. Let's try harder.

We can run `binwalk` to see if there is any hidden files in the jpeg. We get this output:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# binwalk Snowboard.jpg 
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
90            0x5A            TIFF image data, little-endian offset of first image directory: 8
932           0x3A4           JPEG image data, JFIF standard 1.01
14651         0x393B          Copyright string: "CopyrightOwner> <rdf:Seq/> </plus:CopyrightOwner> <plus:Licensor> <rdf:Seq/> </plus:Licensor> </rdf:Description> </rdf:RDF> </x:"
14685         0x395D          Copyright string: "CopyrightOwner> <plus:Licensor> <rdf:Seq/> </plus:Licensor> </rdf:Description> </rdf:RDF> </x:xmpmeta>  "
```

It seems like there is something hidden. We can extract this using `binwalk -D 'image:jpeg' Snowboard.jpeg --run-as=root`. When that is run, we get a new directory called `_Snowboard.jpg.extracted` which contains three files:

```bash
┌──(root㉿kali)-[~/Downloads/_Snowboard.jpg.extracted]
└─# ls
0.jpeg  3A4.jpeg  5A.jpeg

```

Let's try to run `strings` on any of these files to see if there is anything we can use. We try the first file, `0.jpeg`:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/_Snowboard.jpg.extracted]
└─# strings 0.jpeg | head 
JFIF
CTFlearn{CTFIsEasy!!!}
Q1RGbGVhcm57U2tpQmFuZmZ9Cg==
Exif
Canon
```

We see that we are given a string of some sort, being `Q1RGbGVhcm57U2tpQmFuZmZ9Cg==`. Since it ends with `==`, we can almost be certain it is Base64 encoded. Let's decode it:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/_Snowboard.jpg.extracted]
└─# echo "Q1RGbGVhcm57U2tpQmFuZmZ9Cg==" | base64 -d                        
CTFlearn{SkiBanff}
```

And we can collect our flag.

---

Flag: `CTFlearn{SkiBanff}`
