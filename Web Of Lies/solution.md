# Solution

We are given the image file `web_of_lies.jpg`.

---

The description and challenge topic points to us having to use the strings command.

Strings is a command that is used to extract printable ASCII in a file's binary data.

Indeed, there are some telltale signs of additional ASCII text being inserted inside the file.

These include:
```
Steghide returning Corrupt JPEG data: 73 extraneous bytes before marker 0xd9
The top row of pixels looking corrupted and not aligning to the rest of the image
```
---

A naive solution to extract the printable ASCII would be `strings web_of_lies.jpg`.

This outputs a lot of printable text, like this:

```
...
e2\g
>pA>9
2zrUR~
~\d/
SI      J%
EJCTF{very_real_flag}
```

While the flag on the bottom might look like a legitimate find, it's a fake flag!

A better solution would be to use strings with grep.

---

grep is a command-line utility in Linux that searches for regex (regular expression) patterns in text.

In Linux, there is a technique called piping.

You can use it by calling the command `strings web_of_lies.jpg | grep EJCTF{`.

Specifically, the pipe "|" takes the strings output of `web_of_lies.jpg` and uses it as the input for grep.

Additionally, the grep command takes in `EJCTF{`, which is a neat trick to search for the flag.

(This is because CTFs strictly follow a specified flag format, and we can exploit the given flag format `EJCTF{`)

Running the command will output the actual flag (alongside the previous fake):

```
Okay, this is the real flag: EJCTF{l14r_l14R_str1n9y_sp1d3r}`g
EJCTF{very_real_flag}
```
