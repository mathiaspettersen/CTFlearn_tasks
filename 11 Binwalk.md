# Binwalk

**Here is a file with another file hidden inside it. Can you extract it? https://mega.nz/#!qbpUTYiK!-deNdQJxsQS8bTSMxeUOtpEclCI-zpK7tbJiKV0tXYY**

---

The link points to an image that we download. As the task name is `Binwalk`, we will try to run the program `binwalk` in Linux on the file:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# binwalk PurpleThing.jpeg    
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 780 x 720, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, best compression
153493        0x25795         PNG image, 802 x 118, 8-bit/color RGBA, non-interlaced
```

As we see, binwalk shows us there is an image within the image. We need to figure out how to extract this. Luckily, `binwalk` has a method for extraction. If we want to extract all files from an image, we can use `binwalk -D 'image:png' PurpleThing.jpeg`. If you get an error from Binwalk, just as `--run-as=root` behind the statement and it should work.

When we run that command, we get a directory called `PurpleThing.jpeg.extracted`:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/_PurpleThing.jpeg.extracted]
└─# ls
0.png  25795.png  29  29.zlib
```

As we see, there are three files. If we open the `25795.png`, we get our flag.

---

Flag: `ABCTF{b1nw4lk_is_us3ful}`

