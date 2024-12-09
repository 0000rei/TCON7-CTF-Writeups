# TCON7 Writeup
## Hidden in Plain Sight 

---

Category: `OSINT`
Points: `300`
Writeup by: [000rei](https://github.com/0000rei)

---

## Challenge: 

In the ever-evolving digital landscape, a curious user known as laet4x has posted a seemingly innocuous image.

This platform, once known for its avian mascot, now hosts a mystery waiting to be unraveled. Your mission is to delve into this digital realm and uncover what secrets this image might hold. Look closely, as the key to discovering the hidden treasure may be cleverly concealed within its pixels.

<img src="https://tcon7.laet4x.com/files/0b23515b814fc96e5d93bf0b75b5120e/tcon.jpeg">

Can you find what lies beneath the surface?

---

## Solution:

Going back to the website https://laet4x.com/ from the challenge "Traveler's Secret".
With the same approach, viewing the source code will show a google sheets link

```html
<!-- Template Main JS File -->
<script src="assets/js/main.js"></script>
<a href="https://docs.google.com/spreadsheets/d/1_m9r4VzMxGW8Ox87yFgAeRqp63EvEi7BoAJGln-aQpE/edit?gid=0#gid=0" style="color: black; text-decoration: none;">&nbsp;</a>
```

There seems to be a <a href="https://docs.google.com/spreadsheets/d/1_m9r4VzMxGW8Ox87yFgAeRqp63EvEi7BoAJGln-aQpE/edit?gid=0#gid=0">spreadsheet link</a>:

Viewing the Google Sheets, there seems to be a hidden column (B). To view the hidden column, download or make a copy of the spreadsheet. And then unhide the column B.

| TCON Date:    |                                        | November 30 |
| ------------- | -------------------------------------- | ----------- |
| Type:         | tcon{a4ad18a29dad260a20ff8538f7a3fc8a} | Public      |
| TCON Planning |                                        |             |
