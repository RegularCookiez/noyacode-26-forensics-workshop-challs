# Solution

The description and the image should hint towards examining metadata.

---

To examine the metadata of a file, we can open our Linux terminal and navigate to our Downloads folder with cd.

For example, on Windows, this would be the command `cd /mnt/c/Users/your_username/Downloads`.

After that, we can use ExifTool by running the command `exiftool digital_secrets.avif`.

---

Once ExifTool outputs the image file's metadata, you should see something like this:

```
ExifTool Version Number         : 12.76
File Name                       : digital_secrets.avif
Directory                       : .
File Size                       : 18 kB
File Modification Date/Time     : 2026:01:07 00:28:45+08:00
File Access Date/Time           : 2026:01:07 00:33:55+08:00
File Inode Change Date/Time     : 2026:01:07 00:31:28+08:00
File Permissions                : -rwxrwxrwx
File Type                       : AVIF
File Type Extension             : avif
MIME Type                       : image/avif
Major Brand                     : AV1 Image File Format (.AVIF)
Minor Version                   : 0.0.0
Compatible Brands               : avif, mif1, miaf
Handler Type                    : Picture
Primary Item Reference          : 1
XMP Toolkit                     : Image::ExifTool 12.76
Description                     : You're on the right track with ExifTool... but where's the flag?
Exif Byte Order                 : Big-endian (Motorola, MM)
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Y Cb Cr Positioning             : Centered
Exif Version                    : 0232
Components Configuration        : Y, Cb, Cr, -
User Comment                    : RUpDVEZ7dGgzX0QzdjFsXzE1XzFuX3RoM19kM1Q0MUw1fQ==
Flashpix Version                : 0100
Color Space                     : Uncalibrated
Color Profiles                  : nclx
Color Primaries                 : BT.709
Transfer Characteristics        : sRGB or sYCC
Matrix Coefficients             : BT.601
Video Full Range Flag           : 1
AV1 Configuration Version       : 1
Chroma Format                   : YUV 4:2:0
Chroma Sample Position          : Unknown
Image Width                     : 1200
Image Height                    : 643
Image Spatial Extent            : 1200x643
Image Pixel Depth               : 8 8 8
Media Data Size                 : 17976
Media Data Offset               : 408
Image Size                      : 1200x643
Megapixels                      : 0.772
```

---

There are some interesting fields here, but one that should capture your attention is this:

`User Comment                    : RUpDVEZ7dGgzX0QzdjFsXzE1XzFuX3RoM19kM1Q0MUw1fQ==`

This field is a user comment, which is easily editable.

Also notice the equal signs on the back, suggesting that this string is padded Base64!

Decode the Base64 in an online decoder such as https://www.base64decode.org/.

You should obtain the flag `EJCTF{th3_D3v1l_15_1n_th3_d3T41L5}`
