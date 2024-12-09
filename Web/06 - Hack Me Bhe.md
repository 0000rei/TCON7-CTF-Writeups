# TCON7 Writeup
## Hack Me Bhe

---

Category: `Web`
Points: `200`
Writeup by: [kangel]()

---

## Challenge: 

Test your known by exploiting the server.

Modify your host file to: `13.212.185.158 vuln.tconserver.eskie`

open `http://vuln.tconserver.eskie:8080`

---

## Solution:
*Vulnerable PHP version leading to RCE 

As initial recon we can check response headers `curl -I http://konoha.tconserver.eskie:8080`
![Pasted image 20241207234504](https://github.com/user-attachments/assets/944a471a-3b14-4cd5-86f8-f1b108745716)


searchsploit can be used to search exploits `searchsploit PHP 8.1.0-dev` 
![Pasted image 20241207234355](https://github.com/user-attachments/assets/32243549-d0c6-436d-b6e8-3a7d238aab26)



> `PHP 8.1.0-dev - 'User-Agentt' Remote Code Execution`
> An early release of PHP, the PHP 8.1.0-dev version was released with a backdoor on March 28th 2021, but the backdoor was quickly discovered and removed. If this version of PHP runs on a server, an attacker can execute arbitrary code by sending the User-Agentt header. https://www.exploit-db.com/exploits/49933

`searchsploit -m 49933` can be used to download the exploit and the script can be run out of the box with python 
![Pasted image 20241207234701](https://github.com/user-attachments/assets/f837cad1-baf7-463a-9e14-17d5010cc506)



After RCE we get a root user.We can look around for the flag. Flag can be found in `/root/key.txt`
![Pasted image 20241207235038](https://github.com/user-attachments/assets/b99c4f1e-9ce9-4cee-81f7-2acd6856394b)

