# Git Is Good

**The flag used to be there. But then I redacted it. Good Luck. https://mega.nz/#!3CwDFZpJ!Jjr55hfJQJ5-jspnyrnVtqBkMHGJrd6Nn_QqM7iXEuc**

---

The task gives us a zip file called `gitIsGood` which we unzip using:

```bash
unzip gitIsGood.zip
```

Once we unzip the file we can enter the folder. The folder contains a file called `flag.txt` which only contains a redacted flag:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/gitIsGood]
└─# cat flag.txt                              
flag{REDACTED}
```

Since we don't know much about this git repository, let's try to view what has happened by looking a the log:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/gitIsGood]
└─# git log                                                                                   
commit d10f77c4e766705ab36c7f31dc47b0c5056666bb (HEAD -> master)
Author: LaScalaLuke <lascala.luke@gmail.com>
Date:   Sun Oct 30 14:33:18 2016 -0400

    Edited files

commit 195dd65b9f5130d5f8a435c5995159d4d760741b
Author: LaScalaLuke <lascala.luke@gmail.com>
Date:   Sun Oct 30 14:32:44 2016 -0400

    Edited files

commit 6e824db5ef3b0fa2eb2350f63a9f0fdd9cc7b0bf
Author: LaScalaLuke <lascala.luke@gmail.com>
Date:   Sun Oct 30 14:32:11 2016 -0400

    edited files
```

By looking at the log we can see that some file has been modified and commited. To see the changes that has been made to the file we can run `git diff <hash 1> <hash 2>`:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/gitIsGood]
└─# git diff d10f77c4e766705ab36c7f31dc47b0c5056666bb 195dd65b9f5130d5f8a435c5995159d4d760741b
diff --git a/flag.txt b/flag.txt
index c5250d0..8684e68 100644
--- a/flag.txt
+++ b/flag.txt
@@ -1 +1 @@
-flag{REDACTED}
+flag{protect_your_git}
```

And we got our flag.

---

Flag: `flag{protect_your_git}`
