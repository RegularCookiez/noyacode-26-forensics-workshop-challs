# Solution

We are given a ZIP file that contains an extensionless file and a text file called the_basics.txt on inspection.

---

First, extract the ZIP to read the text file, and recover the following contents:

> =====================================================================================
> 
> This challenge is designed for you to practice basic file/folder navigation!
> 
> First, you have to extract the ZIP file.
> 
> Then in your Linux shell, navigate to the folder you extracted these files to.
> 
> To do this, use the "cd /path/to/directory" command to navigate through directories.
> (Remember, you should navigate to your new folder likely in your Downloads folder!)
> 
> Finally, run the executable with the command "./the_basics"!
> 
> After that, you'll get the flag! :)
> (don't worry there's no virus)
> 
> =====================================================================================

---

Now that we know that the nameless file is an executable, we need to navigate to our extracted folder to run it. (Clicking it won't work on an OS like Windows, since it's a Linux executable)

We do this by opening our Linux terminal, and navigating to the folder we extracted using the cd /path/to/folder command.

The path to folder varies based on where it was extracted to, but it should be somewhere in your Downloads folder, like /mnt/c/Users/your_username/Downloads/the_basics for Windows.

---

Running the executable with "./the_basics" will print the following output, and get you the flag:

> You successfully extracted the ZIP file and ran the executable. For passing this simple test, here's the flag:
> 
> EJCTF{l34rn1n9_7h3_r0p35}

