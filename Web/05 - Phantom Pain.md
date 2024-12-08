# TCON7 Writeup
## Phantom Pain 

---

Category: `Web`
Points: `100`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Naka "Hidden" sa server ang flag!

Add to your host file to: `13.212.185.158 konoha.tconserver.eskie`

open `http://konoha.tconserver.eskie`


---

## Solution

After adding the IP Address and FQDN in the host file.
We tried fuzzing files and directories, use different tools, we had a hard time finding this. But the right approach for this challenge is to perform subdomain enumeration.

Adding `hidden` in the host file 
```
[...]
13.212.185.158  hidden.tconserver.eskie
[...]
```

And visiting `http://hidden.tconserver.eskie` will show the flag
`tcon{024dad0f17b96d554d7d7f44f3f33b88}`

> Pentest Note: This is part of reconnaissance phase, it is an additional way to widen the attack surface and identifying potential vulnerabilities by performing subdomain enumeration. Tools such as sublist3r and gobuster will help you perform this information gathering.
> -- 000rei