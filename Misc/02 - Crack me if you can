# TCON7 Writeup
## Echoes of Bini

---

Category: `Misc`
Points: `80`
Writeup by: [xk4k4r0tx](https://github.com/xk4k4r0tx)

---

## Challenge: 

A file that is password protected contains the flag. Try to guess or break the password.

<a>https://tcon7.laet4x.com/files/8b32251051c36507fa892cf94621c72f/fireball-jutsu.zip?token=eyJ1c2VyX2lkIjozMSwidGVhbV9pZCI6OCwiZmlsZV9pZCI6MTh9.Z1cX7A.Nop3Rz66goPg94znYWeF-xUjlBk</a>

---

## Solution:

As per the challenge, the zip file is password-protected, so we need to crack the password to open it. Using fcrackzip, a tool capable of cracking password-protected zip files and available on Kali Linux, along with rockyou as the dictionary, the password was successfully cracked and retrieved.




```bash
$ fcrackzip -u -D -p ~/rockyou.txt fireball-jutsu.zip 


PASSWORD FOUND!!!!: pw == khatcon
```

We will now use the password to extract the flag.txt file from the zip file, which contains the flag.
tcon{971fe8b0daa4291ca8a4d88f6ba713b5}
