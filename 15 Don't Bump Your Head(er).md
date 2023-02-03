# Don't Bump Your Head(er)

**Try to bypass my security measure on this site! http://165.227.106.113/header.php**

---

In this task we are granted with a website for us to bypass the security measures. Once we enter the site, we see that we have to supply the correct user agent:

![bilde](https://user-images.githubusercontent.com/70077872/216585165-63df4c35-345e-44ce-9415-a956e5a5ce45.png)

Since we do not know which user agent it want yet, we can look around the website to see if there is anything interesting. We will start by looking a the code behind the website through Inspect Element (right click + Inspect). We immediately see here that there is a comment containing `Sup3rS3cr3tAg3nt`. Let's assume this is the correct one:

awesomesauce.com

![bilde](https://user-images.githubusercontent.com/70077872/216586251-e79ce9a9-9e82-4390-ae36-e6646e9aa747.png)


Now we have to change our user agent in our request right as we are entering this website. Burpsuite is a great tool to intercept and alter traffic. I'll open Burpsuite, choose Proxy->Intercept->Intercept is on. Then I must make my browser run in "Burpsuite" mode as well ([tutorial](https://portswigger.net/burp/documentation/desktop/external-browser-config/browser-config-firefox)). Once we refresh the website, we see that our user agent is `Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0`, but we want it to be `Sup3rS3cr3tAg3nt`. Let's change this and forward our request:

From this:

![bilde](https://user-images.githubusercontent.com/70077872/216587158-6c2b196f-cfb3-499e-9fe9-677ad59dcb97.png)

To this:

![bilde](https://user-images.githubusercontent.com/70077872/216587457-65953ca5-6959-410d-b449-fd16fe073c5d.png)

However, as we forward that packet, the website updates with another request:

![bilde](https://user-images.githubusercontent.com/70077872/216587725-c9d7c8ff-5575-4b0c-92dc-02288f263637.png)

It seems like in addition to changing our user agent, we have to make it look like we come from `awesomesauce.com` as well. A quick google search reveals that HTTP requests have both an `Origin` parameter and a `Referer` parameter. After some research, it seems like `Referer` is the correct one as it relates to the address where the resource has been requested from. Let's try to add this in addition to changing the user agent. We firstly need to turn Intercept off and on again, then refresh the page:

![bilde](https://user-images.githubusercontent.com/70077872/216590501-29bad5ca-9486-45f0-b92f-5381e03b4835.png)

After we forward that packet, we get our flag.

---

Flag: `flag{did_this_m3ss_with_y0ur_h34d}`
