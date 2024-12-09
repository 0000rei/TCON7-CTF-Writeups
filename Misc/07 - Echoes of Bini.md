# TCON7 Writeup
## Echoes of Bini

---

Category: `Misc`
Points: `200`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

Only those with sharp ears and a mind for puzzles will find the truth hidden within the pop.

<img src="https://tcon7.laet4x.com/files/c6602115e5fc7d179a110e491602dc0d/images.jpeg">

Can you hear the message waiting to be uncovered?

<button>tconXBINI_Salamin.mp3</button>
---

## Solution:

Listening to this repeatedly will not retrieve the flag. As I have experienced in other CTFs online, it can be a wave steganography, but it isn't.

Who knows that `exiftool` can also be used for audio files?

```bash
$ exiftool tconXBINI_Salamin.mp3
ExifTool Version Number         : 12.76
File Name                       : tconXBINI_Salamin.mp3
Directory                       : .
File Size                       : 6.4 MB
File Modification Date/Time     : 2024:12:01 00:55:36+08:00
File Access Date/Time           : 2024:12:01 01:46:02+08:00
File Inode Change Date/Time     : 2024:12:01 00:56:04+08:00
File Permissions                : -rwxrwxrwx
File Type                       : MP3
File Type Extension             : mp3
MIME Type                       : audio/mpeg
MPEG Audio Version              : 1
Audio Layer                     : 3
Audio Bitrate                   : 192 kbps
Sample Rate                     : 48000
Channel Mode                    : Stereo
MS Stereo                       : Off
Intensity Stereo                : Off
Copyright Flag                  : False
Original Media                  : False
Emphasis                        : None
ID3 Size                        : 839680
Title                           : Salamin, Salamin || BaseNaija.com
Artist                          : BINI
Album                           : tcon
Year                            : 2024
Genre                           : BaseNaija
Comment                         : Downloaded From BaseNaija.com
Picture MIME Type               : image/jpeg
Picture Type                    : 32x32 PNG Icon
Picture Description             :
Picture                         : (Binary data 17457 bytes, use -b option to extract)
Track                           : 666c61677b36363332396330366639623336303862343261666138393934383539343165387d
Date/Time Original              : 2024
Duration                        : 0:03:50 (approx)
```

I have already done this but ignored the Track and its value. But revisiting this, it is a hex string!

So decoding from Hex using [CyberChef](https://gchq.github.io/CyberChef) will give the flag: `flag{66329c06f9b3608b42afa899485941e8}`


But we're at TCON!, the flag should be 
```
tcon{66329c06f9b3608b42afa899485941e8}
```