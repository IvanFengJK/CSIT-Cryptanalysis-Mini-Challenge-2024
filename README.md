# Draconis' Encrypted Birthday Gift Challenge

### Challenge Description
On his birthday, Draconis the dragon received a glittering gift from Goldy, his goldfish friend! Despite all his strength and fiery breath, Draconis couldn't manage to unwrap his present. In desperation, he called Goldy for help.

Goldy sheepishly admitted that he had encrypted the gift using a modified version of the KIASU-BC tweakable block cipher to keep it safe—but in the excitement, he had forgotten the decryption key!

### Challenge Instructions
Your mission is to help Draconis recover the missing plaintext message to unlock his gift and obtain the flag. Once you've cracked the code, submit the flag to receive a digital badge!

If you find yourself stuck, Goldy has left a few helpful hints to guide you along the way.

### Verify Hash
To ensure the integrity of the downloaded zip file, verify its hash value using the following command:

```
md5 challenge\ \(5\).zip
```

The expected MD5 hash value is:
```
MD5 (challenge (5).zip) = a92ef09f2843326b801a61a2ab43218a
```
Make sure the output matches this value to confirm that the file has not been altered.

### Hints

**Hint 1:**
The cipher is linear. You can use the Difference Distribution Table (DDT) or Linear Approximation Table (LAT) tool to verify the sbox to be linear (the other components only involve rewiring/XORs, which are linear by nature). This means that $E(x,k,t) = F(x) + G(k) + H(t)$ for some $F$,$G$,$H$ functions

**Hint 2:**
You don't need to recover the key. Treat $G(k) + H(t)$ as a single unknown variable. Solve for it.

**Hint 3:**
You need to create an instance of the cipher with $key = tweak = 0$