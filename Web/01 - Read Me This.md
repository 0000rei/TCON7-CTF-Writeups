# TCON7 Writeup
## Read Me This

---

Category: `Web`
Points: `20`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Look for interesting files in this website below.

Add to your host file to: `13.212.185.158 interest.tconserver.eskie`

open `http://interest.tconserver.eskie`

---

## Solution

After adding the IP Address and FQDN in the host file.
From the title of the challenge "Read Me This", a common file name README or readme can be use to view files in the server.

The flag can be found at `http://interest.tconserver.eskie/readme.txt`
The file contains `tcon{a6f2af252e86baf0ec12ee5c29c0043f}`

> AppSec Note: This is a common web misconfiguration, information exposure. 
> -- 000rei