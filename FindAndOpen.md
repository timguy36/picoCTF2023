# FindAndOpen

## Challenge Description

Someone might have hidden the password in the trace file.
Find the key to unlock this file. This tracefile might be good to analyze.

## Tags
Forensics

## Challenge Information

Points: 200

## Hints

1) Download the pcap and look for the password or flag.
2) Don't try to use a password cracking tool, there are easier ways here.

## Solution

The challenge provides us with two files, a password protected zip and a wireshark packet capture.
````
flag.zip: Zip archive data, at least v1.0 to extract, compression method=store
dump.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
````
<br>
Upon examining the packet capture file, at first glance, it seems to contain packets from the use of google chromecast among some other random packets. <br>

The random packets contains data that seems to be planted by the challenge creator so let's follow up on this lead.
<br>
<br>

| Protocol | Data                                                                   |
|----------|------------------------------------------------------------------------|
| 0x6865   | Flying on Ethernet secret: Is this the flag                            |
| 0x3143   | iBwaWNvQ1RGe1Could the flag have been splitted?                        |
| 0x4c4b   | AABBHHPJGTFRLKVGhpcyBpcyB0aGUgc2VjcmV0OiBwaWNvQ1RGe1IzNERJTkdfTE9LZF8= |
| 0x7361   | PBwaWUvQ1RGesabababkjaASKBKSBACVVAVSDDSSSSDSKJBJS                      |
| 0x314d   | PBwaWUvQ1RGe1Maybe try checking the other file                         |

<br>
The data for the packet with protocol 0x4c4b has a "=" at the end so i'm guessing it's encoded using base64. <br><br>

````
Data (56 bytes)
    Data: 564768706379427063794230614755676332566a636d56304f69427761574e7651315247…
    [Length: 56]
````

<br>
The data field of the packet is in hexadecimal so we have to decode that string using hexadecimal then base64 <br><br>

````
Hex to plaintext
564768706379427063794230614755676332566a636d56304f69427761574e76513152476531497a4e45524a546b64665445394c5a46383d
-> VGhpcyBpcyB0aGUgc2VjcmV0OiBwaWNvQ1RGe1IzNERJTkdfTE9LZF8=

base64 to plaintext
VGhpcyBpcyB0aGUgc2VjcmV0OiBwaWNvQ1RGe1IzNERJTkdfTE9LZF8=
-> This is the secret: picoCTF{R34DING_LOKd_
````

<br>
We finally have something! But it looks like that flag is incomplete.<br><br>

If we use the partial flag on the password protected zip file, it creates the file "flag" with the contents

## Flag

picoCTF{R34DING_LOKd_fil56_succ3ss_419835ef}
