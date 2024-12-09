# TCON7 Writeup
## The Coded Conundrum 

---

Category: `OSINT`
Points: `200`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Recently, a cryptic artifact related to fr4nc1stein and laet4x was discreetly added, obscured by layers of syntax.

Your mission is to explore this intriguing mystery, uncovering hidden truths while navigating potential misdirection. Look for peculiar patterns and anomalies that might lead you closer to the secret.

Remember, the most valuable insights may be hidden amidst the chaos of code within its repositories. Good luck!

<img src="https://tcon7.laet4x.com/files/aeb665fdb8c989fc3282f942716229d4/r.jpeg">

---

## Solution:

It is suppose to do something with code, since this is an OSINT challenge, we can guess codes can be upload to code repositories such as GitHub.

Searching `fr4nc1stein` in GitHub will show a user `https://github.com/fr4nc1stein/`. Checking the user's public repositories, there's a repository called `tcon` (https://github.com/fr4nc1stein/tcon)!

There's 5 commits in this repository. So looking for changes in the `readme.md` file.

The flag can be found in the commit [e240e49](https://github.com/fr4nc1stein/tcon/commit/e240e499a740e690953755769dbfd1263436a994#diff-5a831ea67cf5cf8703b0de46901ab25bd191f56b320053be9332d9a3b0d01d15R7) with the description "Old Poem".

> In the heart of the North, where mountains rise tall,
A vision was born, a clarion call.
> HackTheNorth.ph, where minds come to grow,
> A beacon of learning, where talents will flow.
> From Luzon’s vast fields to the cities so bright,
> A community thrives, chasing the light.
> The largest of gatherings, where hackers unite,
> Innovators, dreamers, igniting the night.
> With code as their canvas, they break every chain,
> Creating new worlds from passion and brain.
> A mission to foster, to nurture, to guide,
> Where skill meets ambition, and hearts open wide.
> And deep in this network, a key you will find,
> tcon{fffca4d67ea0a788813031b8bbc3b329}, a prize intertwined.
> For those who seek wisdom, and those who will dare,
> A treasure lies waiting in digital air.
> Redefining hacking, not as it seems,
> But shaping the future through digital dreams.
> For the hackers of tomorrow who dare to explore,
> HackTheNorth.ph opens the door.
> A place where the ICT community grows,
> Globally bound, where talent overflows.
> So join in the quest, and share in the flame,
> At HackTheNorth.ph, where we rise to acclaim.
> The path is uncertain, but with each passing day,
> We inspire, we conquer, and pave a new way.

