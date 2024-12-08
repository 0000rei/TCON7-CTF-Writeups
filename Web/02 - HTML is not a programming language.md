# TCON7 Writeup
## HTML is not a programming language

---

Category: `Web`
Points: `30`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Yes It is not! Come on, you can also find one if you look at the code, errms markup.

Add to your host file to: `13.212.185.158 html.tconserver.eskie`

open `http://html.tconserver.eskie`

---

## Solution

After adding the IP Address and FQDN in the host file.
From the title of the challenge, a flag can be found in the page source of the website.

View the Page Source of `http://html.tconserver.eskie/`
`tcon{3b290c0f864319497f957ac1b1293492}`

> AppSec Note: This is a common web misconfiguration, information exposure or sensitive hardcoded information. 
> -- 000rei