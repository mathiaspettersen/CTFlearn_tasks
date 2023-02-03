# QR Code

**Do you remember something known as QR Code? Simple. Here for you : <br /> https://mega.nz/#!eGYlFa5Z!8mbiqg3kosk93qJCP-DBxIilHH2rf7iIVY-kpwyrx-0**

---

Once we enter the website, there is a QR code to be scanned. When I scan this on my phone, an automatic google search is made with the string `c3ludCB2ZiA6IGEwX29icWxfczBldHJnX2RlX3BicXI=`. This must be some type of hash.

Since the hash has a `=` sign after it, it is most likely Base, and most likely Base64. Lets try to decode it in Linux:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# echo "c3ludCB2ZiA6IGEwX29icWxfczBldHJnX2RlX3BicXI=" | base64 -d
synt vf : a0_obql_s0etrg_de_pbqr                                    
```

We then get a weird looking string after the decoding. This type of string reminds me of a ROT cipher where the characters are shifted equally, where ROT13 is the most common. Let's add the ROT into our command:

```bash
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# echo "c3ludCB2ZiA6IGEwX29icWxfczBldHJnX2RlX3BicXI=" | base64 -d | rot13
flag is : n0_body_f0rget_qr_code                                            
```

And there we can collect our flag.

---

Flag: `CTFlearn{n0_body_f0rget_qr_code}`
