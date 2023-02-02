# Taking LS

**Just take the Ls. Check out this zip file and I be the flag will remain hidden. https://mega.nz/#!mCgBjZgB!_FtmAm8s_mpsHr7KWv8GYUzhbThNn0I8cHMBi4fJQp8**

---

As the name suggests, we probably have to traverse the filesystem to find the flag. The link directs to a .ZIP file which we download.

Unzipping the file can easily be done with the `unzip` command in Linux (`unzip 'The Flag.zip'`) or by using the GUI to extract it to a chosen folder.

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# ls
'The Flag.zip'
                                                                                                                              
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# unzip The\ Flag.zip 
Archive:  The Flag.zip
   creating: The Flag/
  inflating: The Flag/.DS_Store      
   creating: __MACOSX/
   creating: __MACOSX/The Flag/
  inflating: __MACOSX/The Flag/._.DS_Store  
   creating: The Flag/.ThePassword/
  inflating: The Flag/.ThePassword/ThePassword.txt  
  inflating: The Flag/The Flag.pdf   
  inflating: __MACOSX/The Flag/._The Flag.pdf  
                                                                                                                              
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# ls
 __MACOSX  'The Flag'  'The Flag.zip'
```

After unzipping, we are left with a folder called 'The Flag'. This folder contains a PDF. If we try to open it either through the GUI or with `xdg-open 'The Flag.pdf'`, we need a password as well.

Running strings on the PDF does not seem to yield any results, as we hope to find the password here. Reminiscing to the name of the challenge, we should probably explore the filesystem more. To find hidden files, or files starting with a `.`, we can use the `-la` operand in Linux:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/The Flag]
└─# ls   
'The Flag.pdf'
                                                                                                                              
┌──(root㉿kali)-[~/Documents/ctflearn/The Flag]
└─# ls -la
total 40
drwxr-xr-x 3 root root  4096 Oct 30  2016  .
drwxr-xr-x 4 root root  4096 Feb  2 04:06  ..
-rw-r--r-- 1 root root  6148 Oct 30  2016  .DS_Store
-rw-r--r-- 1 root root 16647 Oct 30  2016 'The Flag.pdf'
drwxr-xr-x 2 root root  4096 Oct 30  2016  .ThePassword
```
It is apparent that there is a hidden directory called `.ThePassword`. Entering this folder given us the password:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/The Flag]
└─# cd .ThePassword
                                                                                                                              
┌──(root㉿kali)-[~/Documents/ctflearn/The Flag/.ThePassword]
└─# ls    
ThePassword.txt
                                                                                                                              
┌──(root㉿kali)-[~/Documents/ctflearn/The Flag/.ThePassword]
└─# cat ThePassword.txt 
Nice Job!  The Password is "Im The Flag".
```

If we use this password on the password protected PDF, we are granted the flag:

![bilde](https://user-images.githubusercontent.com/70077872/216281338-f8b326f1-5e57-4d6e-96bd-b8c0b7b13a39.png)

Flag: `ABCTF{T3Rm1n4l_is_C00l}`

