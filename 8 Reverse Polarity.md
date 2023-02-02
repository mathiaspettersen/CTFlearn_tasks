# Reverse Polarity

**I got a new hard drive just to hold my flag, but I'm afraid that it rotted. What do I do? The only thing I could get off of it was this: 01000011010101000100011001111011010000100110100101110100010111110100011001101100011010010111000001110000011010010110111001111101**

---

## Solution 1

The given string consists of 1s and 0s, which represent the binary language spoken at the lowest level by computers. These binary numbers are later translated into higher level languages until it reaches the fron GUI us humans know and love. As with the morse code task, this is just another [`CyberChef`](https://gchq.github.io/CyberChef/) task.

Add the `From Binary` option into the Recipe, and we have our flag.

## Solution 2

If you are feeling extra adventurous, you could use the Linux terminal to output the ASCII representation of the bits.

```bash
┌──(root㉿kali)-[~/Documents/ctflearn/The Flag]
└─# echo "obase=16; ibase=2; 01000011010101000100011001111011010000100110100101110100010111110100011001101100011010010111000001110000011010010110111001111101" | bc | xxd -r -p
CTF{Bit_Flippin}
```
This command conversts from binary to hex, and then pipes `|` the result into xxd which converts the hex to ASCII ("normal" characters).

---

Flag: `CTF{Bit_Flippin}`
