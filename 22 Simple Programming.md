# Simple Programming

**Can you help me? I need to know how many lines there are where the number of 0's is a multiple of 3 or the numbers of 1s is a multiple of 2. Please! Here is the file: https://mega.nz/#!7aoVEKhK!BAohJ0tfnP7bISIkbADK3qe1yNEkzjHXLKoJoKmqLys**

---

We are given a `data.dat` file, and are to figure out what is stated in the caption. We can first check how many lines are in the document:

```python
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# wc -c data.dat                         
160223 data.dat
```

There are `160 223` lines which we cannot go through manually. We can create a python script to solve this. The python script is made as follows:

```python
count = 0

with open("data.dat", "r") as file:
	for line in file:
		zeros = line.count("0")
		ones = line.count("1")
		if (zeros % 3 == 0) or (ones % 2 == 0):
			count +=1

print(count)
```

In this script we firstly open the data file and read line by line. Then we count the 0s and 1s in each line to see if it is a mulitple of 3 or 1. If it is, the `count` variable adds +1. Then we run the script:

```python
┌──(root㉿kali)-[~/Documents/ctflearn]
└─# python3 script.py
6662
```

And we have our flag.

---

Flag: `CTFlearn{6662}`
