# TCON7 Writeup
## Meta Cat

---

Category: `Misc`
Points: `300`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

A curious cat image has surfaced, layered with mysteries in every pixel. Look beyond the fur and whiskers—there’s a hidden code concealed within. It’s up to you to reveal the secrets left by the Meta Cat. Decode, decipher, and delve deep to unveil the truth. Will you crack the feline enigma?

<a href="">tconXmetaCat.webp</a>

---

## Solution:

After downloading the file `tconXmetaCat.webp`, the first we can do in Image Steganography challenge is look for exif data.

Using `exiftool` will show the flag in Image Description:
```bash
$ exiftool tconXmetaCat.webp
ExifTool Version Number         : 12.76
File Name                       : tconXmetaCat.webp
Directory                       : .
File Size                       : 247 kB
File Modification Date/Time     : 2024:11:30 21:47:39+08:00
File Access Date/Time           : 2024:11:30 22:24:24+08:00
File Inode Change Date/Time     : 2024:11:30 21:47:39+08:00
File Permissions                : -rwxrwxrwx
File Type                       : Extended WEBP
File Type Extension             : webp
MIME Type                       : image/webp
WebP Flags                      : EXIF, ICC Profile
Image Width                     : 2048
Image Height                    : 2048
Profile CMM Type                : Little CMS
Profile Version                 : 2.1.0
Profile Class                   : Display Device Profile
Color Space Data                : RGB
Profile Connection Space        : XYZ
Profile Date Time               : 2012:01:25 03:41:57
Profile File Signature          : acsp
Primary Platform                : Apple Computer Inc.
CMM Flags                       : Not Embedded, Independent
Device Manufacturer             :
Device Model                    :
Device Attributes               : Reflective, Glossy, Positive, Color
Rendering Intent                : Perceptual
Connection Space Illuminant     : 0.9642 1 0.82491
Profile Creator                 : Little CMS
Profile ID                      : 0
Profile Description             : c2ci
Profile Copyright               : CC0
Media White Point               : 0.9642 1 0.82491
Red Matrix Column               : 0.43607 0.22249 0.01392
Green Matrix Column             : 0.38515 0.71687 0.09708
Blue Matrix Column              : 0.14307 0.06061 0.7141
Red Tone Reproduction Curve     : (Binary data 64 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 64 bytes, use -b option to extract)
Blue Tone Reproduction Curve    : (Binary data 64 bytes, use -b option to extract)
VP8 Version                     : 0 (bicubic reconstruction, normal loop)
Horizontal Scale                : 0
Vertical Scale                  : 0
Warning                         : [minor] Improper EXIF header
Exif Byte Order                 : Little-endian (Intel, II)
Image Description               : tcon{29b4657876f5fd4f943f70aadbf03b75}
Orientation                     : Horizontal (normal)
X Resolution                    : 71.983
Y Resolution                    : 71.983
Resolution Unit                 : inches
Artist                          : tcon
Y Cb Cr Positioning             : Centered
Exif Version                    : 0210
Components Configuration        : Y, Cb, Cr, -
Flashpix Version                : 0100
Color Space                     : Uncalibrated
Exif Image Width                : 2048
Exif Image Height               : 2048
Owner Name                      : laet4x
GPS Latitude Ref                : North
GPS Longitude Ref               : East
Image Size                      : 2048x2048
Megapixels                      : 4.2
GPS Latitude                    : 13 deg 50' 55.49" N
GPS Longitude                   : 121 deg 59' 31.88" E
GPS Position                    : 13 deg 50' 55.49" N, 121 deg 59' 31.88" E
```
