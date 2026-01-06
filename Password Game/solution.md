# Solution

We are given the image file `password_game.jpg`.

---

Given the references to passwords and the challenge topic, it should be clear we are dealing with Steghide.

Specifically, Steghide is an LSB steganography tool that can embed files in JPG/BMP/WAV/AU files.

Additionally, it also uses password encryption!

---

Looking at the challenge hint, it should be clear that the password is somewhere on the image.

In fact, we can see that the image is a screenshot from "The Password Game" on neal.fun.

---

Looking at the image, we note down the on-screen password `NoVemberlike(Us)666PepsiVII3pe4g`.

Now, we can attempt to use it to break the steganography in the image.

First, we navigate to our Downloads folder with the `cd` command.

For example, on Windows, it would be `cd /mnt/c/Users/your_username/Downloads`.

To perform Steghide extraction, we then run the command `steghide extract -sf password_game.jpg`.

It will prompt us to enter a passphrase, where we can enter what we recorded down.

It should succeed, and extract a file called `flag.txt`.

Below is a snippet of what that could look like:

```
your_username@HOSTNAME:/mnt/c/Users/your_username/Downloads$ steghide extract -sf password_game.jpg
Enter passphrase:
wrote extracted data to "flag.txt".
```

---

After extracting `flag.txt`, we can open it and read it in a text editor.

Alternatively, we can also use the `cat` command to output its contents.

Typing a command like `cat flag.txt` should print the flag `EJCTF{k1ll3d_p4u1_4g41n_5mh}`.
