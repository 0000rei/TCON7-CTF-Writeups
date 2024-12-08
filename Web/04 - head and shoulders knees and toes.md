# TCON7 Writeup
## head and shoulders knees and toes

---

Category: `Web`
Points: `80`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

If you understand web, then riddle me this. Check the protocol to read the header Look for something with X-Power

Add to your host file to: `13.212.185.158 shoulder.tconserver.eskie`

open `http://shoulder.tconserver.eskie`

---

## Solution

After adding the IP Address and FQDN in the host file.

Viewing the Response Headers will show the flag:
```
X-Powered-by: tcon{a2dce9df9acd3c0c617692f1b417d3cb}
X-Flag: tcon{eskiegwapo123}
```

> AppSec Note: This is a common web misconfiguration, information disclosure in the response headers. The web technology used in the website and (luckily) its specific version can be disclosed in the response headers. This can be leverage if the version used is proven vulnerable such as with public exploits and CVEs.
> -- 000rei