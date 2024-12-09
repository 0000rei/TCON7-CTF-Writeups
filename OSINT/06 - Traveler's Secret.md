# TCON7 Writeup
## Traveler's Secret

---

Category: `OSINT`
Points: `250`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Great Scott! The mysterious website laet4x.com holds the key to an encrypted message, but something’s off. Rumor has it, the information we need is no longer accessible in the present. 

<img src="https://tcon7.laet4x.com/files/550d0adb28845381a30633b28ffadc47/bif.jpg">

---

## Solution:

From the title itself, we should travel back in time using the website [Wayback Machine](https://web.archive.org/).

Enter the website's URL: https://laet4x.com/

There's a snapshot recorded last October 2, 2024. View the snapshot of the website through `https://web.archive.org/web/20241002021438/https://laet4x.com/`. 

Checking the page source, a flag can be found:
```html
[...]
<script src="/web/20241002021438js_/https://laet4x.com/assets/js/main.js"></script>
<p style="color:black;">tcon{2a688a0f4bc9aac948361c3356e716ab}</p>
[...]

tcon{2a688a0f4bc9aac948361c3356e716ab}
```

