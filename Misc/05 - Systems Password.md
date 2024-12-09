# TCON7 Writeup
## Systems Password

---

Category: `Misc`
Points: `100`
Writeup by: [xk4k4r0tx](https://github.com/xk4k4r0tx)

---

## Challenge: 

Hey baddy!

I hacked a server and recovered this hash, can you crack this? I believe it has a tcon prefix on it.

Password is used to open the file, you know what I mean?

cdf982bc32debda4e05782d2f7c8c19f

<a href="">hacked-system.rar</a>

---

## Solution:

As per the challenge, the RAR file is password-protected, and the password has a prefix "tcon."
Upon checking, the provided hash is MD5. For the dictionary, we can either add the "tcon" prefix to all words in rockyou or create a rule in John to add the prefix automatically.
I opted for the latter approach, adding the "tcon" prefix to the rockyou dictionary. I also created a text file containing the hash and used John to crack it.

```bash
$ sed 's/^/tcon/' ~/rockyou.txt > tcon_rockyou.txt

$ echo "cdf982bc32debda4e05782d2f7c8c19f" > tconhash.txt

$ john --wordlist=tcon_rockyou.txt --format=raw-md5 tconhash.txt 
Using default input encoding: UTF-8
Loaded 1 password hash (Raw-MD5 [MD5 128/128 AVX 4x3])
Warning: no OpenMP support for this hash type, consider --fork=4
Press 'q' or Ctrl-C to abort, almost any other key for status
tconeskie        (?)     
1g 0:00:00:00 DONE (2024-12-09 12:08) 3.125g/s 25824Kp/s 25824Kc/s 25824KC/s tconeskimohugs..tconeskeiter13
Use the "--show --format=Raw-MD5" options to display all of the cracked passwords reliably
Session completed. 

```
We will now use the password to extract the flag.txt file from the rar file, which contains the flag.

tcon{4376c60c2f87902b2d29971b816b7a38}
