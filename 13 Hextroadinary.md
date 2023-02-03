# Hextroadinary

**Meet ROXy, a coder obsessed with being exclusively the worlds best hacker. She specializes in short cryptic hard to decipher secret codes. The below hex values for example, she did something with them to generate a secret code, can you figure out what? Your answer should start with 0x.**

**0xc4115 0x4cf8**

---

As we see, we are granted with two hexadecimal values, being 0xc4115 and 0x4cf8. If we try to decode these from hex to ASCII, we are left with `AÏ`, which makes no sense, so we have to figure something else out here. As the caption suggests, ROXy is a coder. If we use our imagination, ROXy could be the inverse of XOR; a logic gate that "gives a true output when the number of true inputs is odd" (Wikipedia). 

In that case, we can try a hex XOR converter online to see what we are left with. I googled "xor hex" and pressed the first link that came up. Here, we need to input each hex value without the 0x (it removes the 0x automatically):

![bilde](https://user-images.githubusercontent.com/70077872/216547272-c9d7f425-3b8b-440f-9df2-99e460367241.png)

We are then granted our flag after we press `Calculate XOR`.

---

Flag: `CTFlearn{c0ded}
