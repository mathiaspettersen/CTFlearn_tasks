# Forensics 101

**Think the flag is somewhere in there. Would you help me find it? https://mega.nz/#!OHohCbTa!wbg60PARf4u6E6juuvK9-aDRe_bgEL937VO01EImM7c**

---

We are firstly greeted with a picture of a minion:

![bilde](https://user-images.githubusercontent.com/70077872/216267508-42c9f8ea-9e50-442d-b0d2-38a02a8ebfb3.png)

As there is a download button on the page, I choose to download it to see if we can extract some more information out of it. A common tool in Linux to aid in stegonography is ´exiftool´. This tool prints all the metadata of the image and visualizes any comments if present at all. `exiftool 95f6edfb66ef42d774a5a34581f19052.jpg` yield this result:

![bilde](https://user-images.githubusercontent.com/70077872/216268132-86eb8ad0-4536-4172-a142-d908d868c410.png)

Based on the results there does not seem like there is any interesting here.



