There are four parts to the flag, each one encoded using a different encoding standard.

---

The first part of the flag is "01000101 01001010 01000011 01010100 01000110 01111011 00110100 01100100".

You should be able to see that it is binary, and that you can convert it through ASCII into text.

You can do it using https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html, and obtain "EJCTF{4d".

---

The second part of the flag is "86 52 110 99 51 68 95 52".

These are regular base-10 numbers, which should you recognise as decimal. Again, use the above ASCII converter to obtain "V4nc3D_4".

---

The third part of the flag is "35 63 31 31 5F 34 66 31".

Notice the "F" character on "5F". This should be a clear signal that this is hexadecimal.

Again, use the above ASCII converter to obtain "5c11_4f1".

---

Finally, the last part of the flag is "QzEwbjREMH0=".

In particular, the equal signs should signal to you that it is Base64, due to the padding.

Decode it with an online Base64 decoder like on https://www.base64decode.org/ to obtain "C10n4D0}".

---

Combine the four flag parts to get the final flag "EJCTF{4dV4nc3D_45c11_4f1C10n4D0}"!
