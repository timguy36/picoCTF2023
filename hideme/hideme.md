# hideme

## Challenge Description

Every file gets a flag.
The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](./flag.png).

## Tags
Forensics, Steganography

## Challenge Information

Points: 100

## Hints

(None)

## Solution

A link is provided to download the file <flag.png>, viewing it shows the picoCTF logo and nothing special to the naked eye.

Binwalk provides the following output
````
 terminal % binwalk flag.png

 DECIMAL       HEXADECIMAL     DESCRIPTION
 --------------------------------------------------------------------------------
 0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
 41            0x29            Zlib compressed data, compressed
 39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
 39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2858, uncompressed size: 3015, name: secret/flag.png
 42897         0xA791          End of Zip archive, footer length: 22
````
The output shows that there is a compressed archive hidden in the image file.

Extracting flag.png produces the folder /secret with another flag.png inside it.

````
terminal % unzip flag.png 
Archive:  flag.png
warning [flag.png]:  39739 extra bytes at beginning or within zipfile
  (attempting to process anyway)
   creating: secret/
  inflating: secret/flag.png
````
opening the extracted [flag.png](./flag2.png) shows the flag.

## Flag

picoCTF{Hiddinng_An_imag3_within_@n_ima9e_96539bea}
