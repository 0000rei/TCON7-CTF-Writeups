# TCON7 Writeup
## Sepolia Secrets 

---

Category: `OSINT`
Points: `400`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Explore the mysteries surrounding address `0xbFCC250e1d5603d144c7ce99834403B0452d2644`. Within this address lies a hidden secret waiting to be uncovered. Delve deep and see if you can piece together the clues to find what’s been concealed. The answers are there; you just need to look closely!

---

## Solution:

Looking from the challenge, `0xbFCC250e1d5603d144c7ce99834403B0452d2644` looks like a blockchain address.

Searching Sepolia in the internet, confirms it is a blockchain. Sepolia is an Ethereum testnet. 

A blockchain explorer was also shown in google, called [Etherscan](https://sepolia.etherscan.io/).

Searching the `0xbFCC250e1d5603d144c7ce99834403B0452d2644` in Etherscan will return the transactions done from this address (https://sepolia.etherscan.io/address/0xbFCC250e1d5603d144c7ce99834403B0452d2644).

We can check every transaction for any details or flags. Until in this [transaction](https://sepolia.etherscan.io/tx/0x9288721c25055aded25a3383ce29640c56eeaae132347da8c53e83fc88a6f31d), there seems to be something in Input Data. 
`0x74636f6e7b62393665363138376265643532356465353465633766636261373138376231647d`

Clicking the button 'View Input As' > 'UTF-8' will show the flag `tcon{b96e6187bed525de54ec7fcba7187b1d}`.