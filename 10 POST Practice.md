# POST Practice

**This website requires authentication, via POST. However, it seems as if someone has defaced our site. Maybe there is still some way to authenticate? http://165.227.106.113/post.php**

---

We are granted with a website that says: 

![bilde](https://user-images.githubusercontent.com/70077872/216313051-e2c3fd7e-5782-4628-9f54-4df006b1bc9a.png)


Since there is nothing else on this page, we should inspect the code to see if there is anything useful for us:

![bilde](https://user-images.githubusercontent.com/70077872/216313197-3d2284b6-ec6a-4256-b75e-96d3359cf4d9.png)

Using Inspect Element reveals to us that there is a username `admin` and a password `71urlkufpsdnlkadsf`. These might be useful for authentication later.

The site tells us we have to submit POST data. Contrary to GET, POST data is when you post information to a website; in this case, a username and a password. This can be performed using for example Burpsuite or cURL in the terminal. We will try with cURL first.

## Solution 

cURL is a tool that allows us to get the code response from a website, and add parameters to alter its response. In this case, we want to POST so we have to specify that in our command:

```bash
curl -X POST
```

We then have to enter the URL we are going to POST to:

```bash
curl -X POST http://165.227.106.113/post.php
```

Lastly, we need to specify our username and password which we recently found. cURL has a `-d` option that means HTTP POST data. Since the POST data is specified here, we do not need it at the start of the command after all:

```bash
curl http://165.227.106.113/post.php -d "username=admin&password=71urlkufpsdnlkadsf

---

<h1>flag{p0st_d4t4_4ll_d4y}</h1>
```

We are now granted with the flag.

---

Flag: `flag{p0st_d4t4_4ll_d4y}`
