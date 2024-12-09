# TCON7 Writeup
## He Left!!

---

Category: `OSINT`
Points: `400`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Hi Howdy,

We received information that one of the author of the TCON7 CTF has left the country. Could you help us track his current location?

NOTE: This challenge uses a non-standard flag format. Enter the human-readable name of the location.

tcon{location}

---

## Solution:

So one of the author of the CTF has left the country. We can assume it is laet4x.

Looking from his links in his website - https://laet4x.com/, there's Twitter, [Facebook](https://www.facebook.com/4lfr4nc1s/), Discord, GitHub, Blogs, and Linkedin. His location might be at Los Angeles, California, but this is wrong.

Not knowing that his location can be found in his [Instagram](https://www.instagram.com/laet4x). His bio contains `bc691003939b33f22ac89afc39417969b3240c6fba15b987c3e9a576cdb15b0b` which seesms to be hash.

Checking the hash using a hash identifier tool - https://hashes.com/en/tools/hash_identifier. It seems to be a SHA-256 hash.
```
bc691003939b33f22ac89afc39417969b3240c6fba15b987c3e9a576cdb15b0b - Possible algorithms: SHA256
```

Decoding this hash from https://www.dcode.fr/sha256-hash will return: `Osaka`

Using the flag format, the flag is: `tcon{Osaka}`