# Base 2 2 the 6

**There are so many different ways of encoding and decoding information nowadays... One of them will work! Q1RGe0ZsYWdneVdhZ2d5UmFnZ3l9**

---

In this challenge we are given a string to decode: `Q1RGe0ZsYWdneVdhZ2d5UmFnZ3l9`. There are plenty different ways to decode, but paying attention to the name of this task is key to solving it. It is named: Base 2 2 the 6 == Base2 to the 6 == Base2^6 == **Base64**.

Base64 is a common way of encoding and decoding information, and its hashes usually end with '=' or '==', so it is easily identifiable.

Running the decoding through linux using the `base64 -d` option:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/The Flag]
└─# echo "Q1RGe0ZsYWdneVdhZ2d5UmFnZ3l9" | base64 -d             
CTF{FlaggyWaggyRaggy}                              
```

Gives us the flag.

Flag: `CTF{FlaggyWaggyRaggy}`
