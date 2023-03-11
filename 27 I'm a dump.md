# I'm a dump

**The keyword is hexadecimal, and removing an useless H.E.H.U.H.E. from the flag. The flag is in the format CTFlearn{*}**

---

In this task, we are given a text file that is an executable by running `file`:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# file file                        
file: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=672d1ab79b5c1f063344be7b8edbda2219d8991d, for GNU/Linux 3.2.0, not stripped
```

However, when we run it, nothing happens (you might need to add permission before runnning the file: `chmod 700 file`:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# ./file
                                      
```

We can try to use `strings`to see if there are any hidden messages:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# strings file         
.....
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
u3UH
CTFlearnH
{fl4ggyfH
l4g}H
[]A\A]A^A_
;*3$"

```

And we have our flag.

---

Flag: `CTFlearn{fl4ggyfl4g}`
