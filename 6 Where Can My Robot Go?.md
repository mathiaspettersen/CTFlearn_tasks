# Where Can My Robot Go?

**Where do robots find what pages are on a website?**

**Hint:**

**What does disallow tell a robot?**

---

This challenge is referring to robots as is 'crawlers' meaning search engines that crawl through websites to find the most relevant results. When someone creates a website, they can add a `robots.txt` file which tells the crawlers what websites they are allowed and disalloweed to crawl. This file usually lies in the root of the website, meaning:

```
https://www.ctflearn.com/robots.txt
```

If we enter this website, we see that there is a file containing some information:

```
User-agent: *
Disallow: /70r3hnanldfspufdsoifnlds.html 
```

This means that the crawlers can crawl everything apart from `/70r3hnanldfspufdsoifnlds.html`, which is a subdirectory. Let's enter this directory:

```
https://ctflearn.com/70r3hnanldfspufdsoifnlds.html
```

And we got our flag.

---

Flag: `CTFlearn{r0b0ts_4r3_th3_futur3}`
