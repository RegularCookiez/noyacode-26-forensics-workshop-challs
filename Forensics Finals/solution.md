# Solution

As a final test, this netcat challenge brings you to a quiz that tests previous forensics concepts you have learnt.

Simply enter the command `nc challenge-services.ejctf-practice.xyz 6767` to connect to the relevant server via Netcat.

---

When you connect to the server, you will be given the following details:

```
  ______                       _            ______ _             _
 |  ____|                     (_)          |  ____(_)           | |
 | |__ ___  _ __ ___ _ __  ___ _  ___ ___  | |__   _ _ __   __ _| |___
 |  __/ _ \| '__/ _ \ '_ \/ __| |/ __/ __| |  __| | | '_ \ / _` | / __|
 | | | (_) | | |  __/ | | \__ \ | (__\__ \ | |    | | | | | (_| | \__ \
 |_|  \___/|_|  \___|_| |_|___/_|\___|___/ |_|    |_|_| |_|\__,_|_|___/

Welcome to the final forensics assessment!
You have 30 minutes to complete two sections.

The first section tests on MCQs, awarding 4 points.

The second section offers interactive challenges, awarding 8 points.

There are a total of 100 points, get 70% for an A. Good luck
```

To complete the challenge, you will need to score enough points from the MCQs and the interactive challenges.

To add extra difficulty, the questions and answer choices are shuffled for each unique connection.

Finally, there is also a time limit of 30 minutes before the server stops you from answering further.

Therefore, the following sections will cover on answers for the different sections and the given explanations in the quiz, in an arbitrary order.

## MCQ Answers

```
Q1. What is ExifTool mainly used to analyse?
A) LSB steganography
B) Metadata ⟵
C) Printable characters
D) File contents
```

ExifTool is a free and open source software program for manipulating and analysing metadata.

While it can analyse partial file contents, you would primarily not use it for that.

Meanwhile, it cannot analyse steganography as it was not designed for it.

---

```
Q2. What is the main reason for using LSB steganography instead of MSB?
A) More secure
B) Easier to calculate
C) Changes the file less noticeably ⟵
D) Less data to store
```

The primary goal of steganography is to conceal hidden data inside a file.

Hence, the main concern is that changing MSBs instead of LSBs would significantly alter the resultant bytes.

This is because in binary, powers of 2 increase to the left.

Hence, changing the leftmost MSB would cause a larger net change in the final value than changing the rightmost LSB.

This would hence result in a noticeable change in the file, defeating the purpose of steganography.

---

```
Q3. What must you always specify in a Netcat command?
A) IP address
B) Port number ⟵
C) Netcat version
D) Domain name
```

Netcat is a utility for reading from and writing to network connections.

Firstly, you need to specify a domain name or IP address.

Hence, you do not need to specifically mention either one as long as you enter one.

However, the port you want to connect to the server from needs to be specified clearly.

Hence, it is the correct answer.

---

```
Q4. Which is not a difference between zsteg and Steghide?
A) zsteg is solely for analysis but Steghide also offers embedding
B) zsteg can analyse BMP files but Steghide cannot ⟵
C) zsteg cannot analyse audio but Steghide can
D) zsteg does not offer password decryption while Steghide does
```

The other three statements are valid differences.

Firstly, zsteg cannot analyse audio as it only operates on PNG/BMP.

Secondly, zsteg does not offer the ability to password-decrypt findings, unlike Steghide.

Thirdly, Steghide was also designed with the functionality to create steganography, whereas zsteg was solely designed for analysis.

This leaves the last option as an invalid difference because both support BMPs.

---

```
Q5. Which of these files must have strings output?
A) A non-empty file
B) A text file
C) A file with a nonzero file size
D) A file with printable characters ⟵
```

Firstly, a non-empty file may not have strings content because it may have only non-printable characters.

Secondly, a text file may not have strings output because it is empty.

Thirdly, a file with nonzero file size might not have strings output due to the same reason as the first.

Therefore, the correct answer is a file with printable characters. (strings specifically searches for them)

---

```
Q6. Which of these file formats is incompatible with Steghide?
A) .JPEG
B) .PNG ⟵
C) .AU
D) .BMP
```

Steghide only supports the following file formats: JPEG, BMP, WAV, and AU.

Therefore, .PNG is the correct answer.

---

```
Q7. In steganography, what does the B in LSB most commonly refer to?
A) Binary
B) Base
C) Bit ⟵
D) Byte
```

LSB stands for least bit steganography.

It works because you adjust the smallest bit (rightmost) for multiple data bytes in binary.

This is used to construct hidden ASCII strings in secret.

---

```
Q8. Which of these is a base-16 number system?
A) Decimal
B) Binary
C) Hexadecimal ⟵
D) Ternary
```

Binary is a base-2 number system. (10100101)

Ternary is a base-3 number system. (21021101)

Decimal is a base-10 number system. (1234567890)

This leaves Hexadecimal as the answer, as a base-16 number system. (5A595A5A595641)

---

```
Q9. What ASCII range consists of printable characters?
A) 0-255
B) 0-126
C) 32-126 ⟵
D) 32-255
```

Printable characters refer to characters that can be displayed and printed.

These include letters, numbers, and symbols.

Meanwhile, invisible non-printable characters also exist.

Think of spaces, tabs, and newlines as examples.

In ASCII, the printable range of characters is 32-126.

---

```
Q10. What does the Linux command cp do?
A) Copy the file contents to the clipboard
B) Copy the current path to the clipboard
C) Create a new path
D) Copy a file from one path to another ⟵
```

cp is a Linux command used to copy a file from one path to another.

This command is used in the format 'cd /old/path/file /new/path/file'.

This would make a copy of the file at /new/path from /old/path.

---

```
Q11. What can't be used to uncover metadata?
A) Zsteg
B) Strings
C) Steghide ⟵
D) ExifTool
```

This is a tricky question.

The most obvious wrong answer is ExifTool, since it is designed to uncover metadata.

Another surprising wrong answer is strings. This is because printable metadata is still part of file contents (and can thus be found)

The most surprising wrong answer would be zsteg. If you didn't know, zsteg actually has capabilities to identify and report suspicious metadata!

This leaves Steghide as the only tool unable to analyse metadata (instead focusing on LSB steganography).

---

```
Q12. Which Linux command searches for text patterns in lines?
A) ls
B) strings
C) grep ⟵
D) pwd
```

ls lists files and directories in the current path.

pwd prints the current directory.

strings prints all printable characters in the file, but does not search for patterns.

This leaves grep, that actively searches for regex patterns and returns findings.

---

```
Q13. 77 68 61 74
A) mean
B) what ⟵
C) this
D) does
```

The following four numbers were in the decimal number system.

If you noticed, these could actually map to ASCII characters.

After that, you could've then obtained 'what' as the correct answer.

---

```
Q14. The lengths of Base64 strings come in multiples of what?
A) 4 ⟵
B) 2
C) 64
D) 16
```

Base64 strings are structured in groups of four.

This is because the Base64 system converts 3 bytes of data to 4 characters.

The length of every encoded string must hence be a multiple of four for proper decoding.

Even if the original string does not produce four characters, padding like = is added.

(p.s. I do realise that multiples of 4 are mathematically multiples of 2, but technicalities won't make you the next forensics master ok??)

---

```
Q15. The everyday numbers we use can be classified under what?
A) Hexadecimal
B) Binary
C) Ternary
D) Decimal ⟵
```

The everyday numbers we use are in base-10.

This is because we represent numbers with ten digits.

For example, we use 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9 to represent numbers.

Therefore, Decimal is the answer. (It refers to a base-10 system)

---

## Interactive Challenge Answers

After completing the MCQs, you will see the following details:

```
You have finished the MCQs, and shall now move on to the interactive challenges.
These challenges are designed to go slightly beyond your base knowledge.

It is recommended to open up a second terminal for solving.
```

Now, I will also go through the 5 interactive challenge solutions in an arbitrary order (since they are randomised).

```
Challenge 1: Find the secret text in isitreallytext.txt
https://drive.google.com/drive/folders/1HdikpDVwkLbySOoPGJcoEnYDQHlxV_bu

Hint: Wrong file extension?
```

The hint tells us that this text file is likely not a text file.

So, what could it be? Looking at the .txt in a text editor like Notepad, it should say something like:

```
‰PNG

   
IHDR      Å   » ,Õ   IDATxìÝ¨mWq ðÍ¥	ED¤” %H	A¤	‚ˆ” ¡ˆH)A$H‘¤H	E‚øG‘"RB‘ B)""¥H)"DJ	RJ$Hþ!"ï• mÅžÛó9/“¬7oö¹gŸ³÷=?îÖÌ[kf¾kfÖìµ×Ùkí÷lq¾8_ý·X–7*çª×¯];¿~íúùµ][–×Î¯_¿¶Ô-qËÿÎÑòŸÅâüW¿úåR¿Ä_¿~®Ýõ×Ú¿úë_/í/QK£
xåâüü_ùß¥Íëç×Vø¶¯-íÿ÷ÿ÷ùr~~¾8÷?ÿâ_ýõ«çüÃˆéú*®ëç¿üÕ¯Îé‹R“~¾8¿¾ŒáÚÒ>üµ¥íëêKº]âoü·DžŸŸ/…×W˜kçðÚ^çc…_œûÿùòKØ9:_œ¯ú|m©_á–¾Ví—å«¯þúœn	[Öý»8ÿŸÿùŸULð×—¸ë¯Ù—‹Åbq¾XÜL¯¾úê2ñÜL¿üå/oÁ.7Ú^[Ú­h±¸¡_,n.+,Ùbq3n±¸Á¿üòËeLb],n`‹7JÇ“½L¯¼òJÙ v2ß×ç>¼8‹7âX,Þ¨³WÑbñf±x£ÎV…ç{±x·XÜ¨‹u^.*¼Ü-7l.o”üVxq.oà‹7êžì¬;ï–ÿ-ÿé–å²Xþ§¶”-ù×þ]
```

The PNG header at the top followed by IHDR and IDAT are actually signs that this file is a PNG, not a text file!

It seems strange that this PNG would come as a text file, but remember that anyone can rename file extensions.

This means that the challenge author likely renamed this PNG into a text file for obfuscation!

Converting to PNG, we get a valid non-corrupt image, but still find nothing.

This is where we do a bit of guesswork, and try `zsteg`, since it is used for PNG steganalysis.

Running `zsteg` with the command `zsteg isitreallytext.png` can give you the following:

```
your_username@HOSTNAME:/mnt/c/Users/your_username/Downloads$ zsteg isitreallytext.png
b1,rgb,lsb,xy       .. text: "The answer is wedidntevenlearnthisyet"
b4,r,msb,xy         .. text: "33Cwww333www333www033qww233vww133tww133pww733sww"
b4,g,msb,xy         .. text: "33Cwww333www333www033qww233vww133tww133pww733sww"
b4,b,msb,xy         .. text: "33Cwww333www333www033qww233vww133tww133pww733sww"
b4,rgb,msb,xy       .. text: "3333333CDwwwwwwwww333333333wwwwwwwww333333333wwwwwwwww"
b4,bgr,msb,xy       .. text: "3333333CDwwwwwwwww333333333wwwwwwwww333333333wwwwwwwww"
b4,abgr,msb,xy      .. file: RDI Acoustic Doppler Current Profiler (ADCP)
your_username@HOSTNAME:/mnt/c/Users/your_username/Downloads$
```

We see that `zsteg` has revealed an answer, and typing it into the challenge gives us 8 points!

---

```
Challenge 2: Find the closest MRT station to where where_is_this.jpg was taken from.
https://drive.google.com/drive/folders/1HdikpDVwkLbySOoPGJcoEnYDQHlxV_bu

Hint: All lowercase, where can I find location information?
```

The challenge tasks us to find the closest MRT station to where a JPG is taken from.

We can see the JPG is somewhere in Singapore, but it's hard to tell clearly where it is.

Instead of guessing endlessly for the location, if you remember, we could use `ExifTool`!

This is because we could use location metadata to our advantage here, and `ExifTool` can help us find it!

We run `ExifTool` with the command `exiftool where_is_this.jpg`. Below is an example of what it would look like:

```
your_username@HOSTNAME:/mnt/c/Users/your_username/Downloads$ exiftool where_is_this.jpg
ExifTool Version Number         : 12.76
File Name                       : where_is_this.jpg
Directory                       : .
File Size                       : 7.3 MB
File Modification Date/Time     : 2026:01:08 03:31:07+08:00
File Access Date/Time           : 2026:01:08 03:31:09+08:00
File Inode Change Date/Time     : 2026:01:08 03:31:07+08:00
File Permissions                : -rwxrwxrwx
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Exif Byte Order                 : Big-endian (Motorola, MM)
Make                            : Apple
Camera Model Name               : iPhone 16
Orientation                     : Horizontal (normal)
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Software                        : 18.5
Modify Date                     : 2025:06:29 12:42:01
Host Computer                   : iPhone 16
Exposure Time                   : 1/2141
F Number                        : 1.6
Exposure Program                : Program AE
ISO                             : 50
Exif Version                    : 0232
Date/Time Original              : 2025:06:29 12:42:01
Create Date                     : 2025:06:29 12:42:01
Offset Time                     : +08:00
Offset Time Original            : +08:00
Offset Time Digitized           : +08:00
Shutter Speed Value             : 1/2141
Aperture Value                  : 1.6
Brightness Value                : 9.124886854
Exposure Compensation           : 0
Metering Mode                   : Multi-segment
Flash                           : Off, Did not fire
Focal Length                    : 6.0 mm
Subject Area                    : 2859 2135 3140 1880
Maker Note Version              : 15
Run Time Flags                  : Valid
Run Time Value                  : 89760022236458
Run Time Scale                  : 1000000000
Run Time Epoch                  : 0
AE Stable                       : No
AE Target                       : 196
AE Average                      : 184
AF Stable                       : Yes
Acceleration Vector             : -0.9877620934 -0.004969268105 0.02941340022
Focus Distance Range            : 0.94 - 1.34 m
Image Capture Type              : Unknown (12)
Live Photo Video Index          : 8595185700
HDR Headroom                    : 1.00999999
Signal To Noise Ratio           : 60.19127273
Photo Identifier                : 6A39E0E4-5612-448C-B770-297CE9C1E6D2
Focus Position                  : 61
HDR Gain                        : 2.206154586
Front Facing Camera             : No
Sub Sec Time Original           : 933
Sub Sec Time Digitized          : 933
Color Space                     : Uncalibrated
Exif Image Width                : 5712
Exif Image Height               : 4284
Sensing Method                  : One-chip color area
Scene Type                      : Directly photographed
Exposure Mode                   : Auto
White Balance                   : Auto
Digital Zoom Ratio              : 1.158464035
Focal Length In 35mm Format     : 30 mm
Lens Info                       : 2.220000029-5.960000038mm f/1.6-2.2
Lens Make                       : Apple
Lens Model                      : iPhone 16 back dual wide camera 5.96mm f/1.6
Composite Image                 : General Composite Image
GPS Latitude Ref                : North
GPS Longitude Ref               : East
GPS Altitude Ref                : Above Sea Level
GPS Time Stamp                  : 04:42:00.99
GPS Speed Ref                   : km/h
GPS Speed                       : 0.9599999785
GPS Img Direction Ref           : True North
GPS Img Direction               : 41.27783203
GPS Dest Bearing Ref            : True North
GPS Dest Bearing                : 41.27783203
GPS Date Stamp                  : 2025:06:29
GPS Horizontal Positioning Error: 55.1893864 m
Profile CMM Type                : Apple Computer Inc.
Profile Version                 : 4.0.0
Profile Class                   : Display Device Profile
Color Space Data                : RGB
Profile Connection Space        : XYZ
Profile Date Time               : 2022:01:01 00:00:00
Profile File Signature          : acsp
Primary Platform                : Apple Computer Inc.
CMM Flags                       : Not Embedded, Independent
Device Manufacturer             : Apple Computer Inc.
Device Model                    :
Device Attributes               : Reflective, Glossy, Positive, Color
Rendering Intent                : Perceptual
Connection Space Illuminant     : 0.9642 1 0.82491
Profile Creator                 : Apple Computer Inc.
Profile ID                      : ecfda38e388547c36db4bd4f7ada182f
Profile Description             : Display P3
Profile Copyright               : Copyright Apple Inc., 2022
Media White Point               : 0.96419 1 0.82489
Red Matrix Column               : 0.51512 0.2412 -0.00105
Green Matrix Column             : 0.29198 0.69225 0.04189
Blue Matrix Column              : 0.1571 0.06657 0.78407
Red Tone Reproduction Curve     : (Binary data 32 bytes, use -b option to extract)
Chromatic Adaptation            : 1.04788 0.02292 -0.0502 0.02959 0.99048 -0.01706 -0.00923 0.01508 0.75168
Blue Tone Reproduction Curve    : (Binary data 32 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 32 bytes, use -b option to extract)
Image Width                     : 5712
Image Height                    : 4284
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:4:4 (1 1)
Run Time Since Power Up         : 24:56:00
Aperture                        : 1.6
Image Size                      : 5712x4284
Megapixels                      : 24.5
Scale Factor To 35 mm Equivalent: 5.0
Shutter Speed                   : 1/2141
Create Date                     : 2025:06:29 12:42:01.933+08:00
Date/Time Original              : 2025:06:29 12:42:01.933+08:00
Modify Date                     : 2025:06:29 12:42:01+08:00
GPS Altitude                    : 43 m Above Sea Level
GPS Date/Time                   : 2025:06:29 04:42:00.99Z
GPS Latitude                    : 1 deg 23' 33.51" N
GPS Longitude                   : 103 deg 53' 46.30" E
Circle Of Confusion             : 0.006 mm
Field Of View                   : 61.9 deg
Focal Length                    : 6.0 mm (35 mm equivalent: 30.0 mm)
GPS Position                    : 1 deg 23' 33.51" N, 103 deg 53' 46.30" E
Hyperfocal Distance             : 3.72 m
Light Value                     : 13.4
Lens ID                         : iPhone 16 back dual wide camera 5.96mm f/1.6
your_username@HOSTNAME:/mnt/c/Users/your_username/Downloads$
```

While there are many interesting metadata fields, showing how this photo was taken from an `iPhone 16`, what you should notice is this:

```
GPS Position                    : 1 deg 23' 33.51" N, 103 deg 53' 46.30" E
```

As you can see, we found the exact GPS position as to where this image was taken!

However, it's in a format that Google can't parse.

To fix this, you ask AI to format its coordinates better.

Below are those same coordinates rounded and formatted in Decimal Degrees:
`1.392641, 103.896194​`

We can then enter the same coordinates in a maps service like Google Maps.

Simply search around for the closest MRT, and you'll find it to be Sengkang MRT.

Simply enter `sengkang` and you will solve the interactive challenge to get 8 points.

---

```
Challenge 3: Find the hidden answer in beepboop.wav
https://drive.google.com/drive/folders/1HdikpDVwkLbySOoPGJcoEnYDQHlxV_bu

Hint: .... .. -. -
```

As you might be able to tell, the hint is in morse code, decoding to "HINT".

This suggests there is some connection to Morse Code in this challenge.

Indeed, if we download and listen to `beepboop.wav`, we can hear beeps sounding like it.

There are some online tools that can actually parse and decode morse code from audio.

One such tool is https://morsecode.world/international/decoder/audio-decoder-adaptive.html.

You can upload `beepboop.wav` on the decoder and decode it from there.

It should say something like:
`PASSWORD IS UPPERCASE: CTF`

You might think to the challenge is `CTF`, but that is wrong.

Instead, we need to think more critically. This likely references password steganography!

Specifically, it likely references Steghide, as it supports WAV files during embedding.

Now, we take our newly found password, and run `steghide extract -sf beepboop.wav` for steganalysis.

Enter the password, and you should see something like this:

```
your_username@HOSTNAME:/mnt/c/Users/your_username/Downloads$ steghide extract -sf beepboop.wav
Enter passphrase:
wrote extracted data to "answer.txt".
```

From there, we can use the `cat` command in Linux to reveal the file contents.

Enter `cat answer.txt` to reveal the answer and submit it for 8 points!

```
your_username@HOSTNAME:/mnt/c/Users/your_username/Downloads$ cat answer.txt
The answer is ITSNOTALLASCIIANDBASE64
```

---

```
Challenge 4: Find the legitimate flag in flag_in_a_million.txt
https://drive.google.com/drive/folders/1HdikpDVwkLbySOoPGJcoEnYDQHlxV_bu

Hint: The flag is EJCTF{*****_***_*********}. How do I match an unknown pattern?
```

In this challenge, we get a very large file called `flag_in_a_million.txt`.

Opening the file in a text editor, we see a lot of fake flags `EJCTF{this_is_a_fake_flag}`.

Luckily, the challenge hint gives us the correct format, `EJCTF{*****_***_*********}`.

Normally, using `grep` to search for `EJCTF{` would not work because both match that keyword.

However, we can use a `regular expression` (regex) instead of just plain text.

One trick in `regex` that you should know is that "." can match to any character.

This allows us to use the regex `EJCTF{....._..._.........}` to match the real flag.

Now, we use `grep` with this regex payload to find the flag.

Simply enter the command `strings flag_in_a_million.txt | grep EJCTF{....._..._.........}` to search for the real flag.

It should output something like this:

```
your_username@HOSTNAME:/mnt/c/Users/your_username/Downloads$ strings flag_in_a_million.txt | grep EJCTF{....._..._.........}
EJCTF{f0Und_th3_leg1tfl4g}
```

Simply submit this real flag to get another 8 points!

---

```
Challenge 5: Completely decode the text in howmuchbase64.txt
https://drive.google.com/drive/folders/1HdikpDVwkLbySOoPGJcoEnYDQHlxV_bu

Hint: Cyberchef/programming can help a lot!
```

Finally, we have a challenge where we get `howmuchbase64.txt`.

Already, the file name suggests there is nested Base64 encoding present.

While you can manually keep decoding it until it produces an English string, there are some convenient options:

Firstly, we can use a tool like Cyberchef to do it, at https://gchq.github.io/CyberChef/.

Simply enter the Base64 into the box labelled `Input`.

Then, keep dragging a bunch of `From Base64` blocks and baking.

This will keep trying to decode the string as Base64.

Eventually, you end up with the result:

```
The answer is BaseInfinity
```

Another solution is to program a script that will keep decoding the string until it says something like "answer".

First, place the relevant file and create a script to read from the file and decode it.

In this example, I coded a Python script to read from the file and keep decoding it.

Below is the full script:

```
import base64

encoded_string = open("howmuchbase64.txt").read()

decoded_string = ""

while "answer" not in decoded_string:
    decoded_bytes = base64.b64decode(encoded_string)
    decoded_string = decoded_bytes.decode('utf-8')
    encoded_string = decoded_string

print(decoded_string)
```

Doing so also recovers the following:

```
The answer is BaseInfinity
```

---

## Final Remarks

After completing the quiz, the server will give you statistics on your total marks and time taken.

If you manage to achieve a score of at least 70%, you should see something like this:

```
Final Score: 100/100 (100%)
Time Taken: 10m 18s

Congratulations! You ACED the assessment with 100 POINTS, earning the coveted A!

You truly learnt A LOT about character encoding standards, steganography and file data.

Honestly, even I didn't expect you to get this far. Brilliant job!

We hope such as a talented mind like yourself will consider joining us. :)

If you want, type something to reveal all interactive task solutions.
If not, you can press enter to get your flag:
```

Pressing enter should give you the final flag, like so:

```
Finally, here lies your last flag:
EJCTF{F34rl355_f0r3n51c5_m45t3R}
```
