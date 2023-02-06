# My Blog

**Hi, I'm Noxtal! I have hidden a flag somewhere in my [Cyberworld](https://noxtal.com/) (AKA blog)... you may find a good application for your memory. ;)**

**Note: This is my real website (thus no deadly bug to exploit here). You might want to read some of my content (writeups, tutorials, and cheatsheets). I would be glad to receive any kind of feedback.**

**[Click here](https://noxtal.com/) to access it, have fun checking my blog out! Cheers!**

**Hint: replace the flag{} part with CTFlearn{}.**

---

Wer are greeted by a website from Noxtal containing a blog, learning platform, projects, and info about Noxtal:

![bilde](https://user-images.githubusercontent.com/70077872/216967870-878859f3-8c0b-4d46-8b44-0efe0df22a70.png)

Since the caption tells us we _"may find a good application for your memory"_, we can try to look at Inspect Element (right click + Inspect) and check the memory/storage tab:

![bilde](https://user-images.githubusercontent.com/70077872/216968116-d0d8d811-ce5f-42e7-a817-f6c19dcb646e.png)

It does not seem like there is anything useful here, and Cookies is the only parameter that has information. Since the task is named `My blog`, lets try to enter the blog and do the same:

![bilde](https://user-images.githubusercontent.com/70077872/216968378-b083a854-6bf9-4aec-be7a-08ba50a4e23b.png)

There is nothing interesting in Cookies, but there is something in Local Storage. 

And we have our flag.

---

Flag: `CTFlearn{n7f_l0c4l_570r463_15n7_53cur3_570r463}`
