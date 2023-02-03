# Viginere Cipher

**The vignere cipher is a method of encrypting alphabetic text by using a series of interwoven Caesar ciphers based on the letters of a keyword.**

**I’m not sure what this means, but it was left lying around: blorpy**

**gwox{RgqssihYspOntqpxs}**

---

The task revolves around solving a Vigenere cipher to get the flag. A Vigenere cipher is a cipher that builds on intervowen Cesar ciphers based on a keyword which is added. This means one has to have the keyword to solve the cipher. In our case, it isn't explicitly stated that there is a keyword, but the caption says: _"I’m not sure what this means, but it was left lying around: blorpy"_. We can assume that `blorpy` is our keyword.

Using online decoders (as they are the easiest), we can try to crack the cipher. In this case I am using [dCOde](https://www.dcode.fr/vigenere-cipher) to solve it. Once we add the cipher and the keyword, we can decrypt it:

![bilde](https://user-images.githubusercontent.com/70077872/216581480-98645271-e2a6-4781-94cb-7b07a1a57dfd.png)


As we see in the top left corner, we got our flag.

---

Flag: `flag{CiphersAreAwesome}`
