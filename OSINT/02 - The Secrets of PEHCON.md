# TCON7 Writeup
## The Secrets of PEHCON

---

Category: `OSINT`
Points: `100`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Welcome to the intriguing world of digital exploration! Within the depths of pehcon.org, a hidden treasure lies waiting to be uncovered. This domain is known for its camaraderie with a certain enigmatic entity, TCON, known for its cryptic connections.

As you navigate through the various pathways of this digital space, stay alert for unusual patterns and clues that may reveal the hidden text. Can you unravel the connections and reveal the secrets of pehcon.org and its ally, TCON?

The challenge awaits you!

---

## Solution:

After viewing the website, a flag can't seem to be found.

Performing DNS records lookup will.

There's a website we can use to look for DNS records called DNSDumpster (https://dnsdumpster.com/). Enter the domain `pehcon.org`. 

View the DNS records
```
TXT Records
"tcon{d040f27c3a87b2298032d43511d4f841}" 
```


Another way is using the `dig` command:
```bash
$ dig pehcon.org TXT

; <<>> DiG 9.18.28-0ubuntu0.24.04.1-Ubuntu <<>> pehcon.org TXT
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 46480
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;pehcon.org.                    IN      TXT

;; ANSWER SECTION:
pehcon.org.             300     IN      TXT     "tcon{d040f27c3a87b2298032d43511d4f841}"
```

> Note: This is part of reconnaissance phase.
