# Solution

This challenge is a bit more interactive as we are tasked to connect to `challenge-services.ejctf-practice.xyz` via port `39001`.

To do this, we can type the following command in our Linux shell: `nc challenge-services.ejctf-practice.xyz 39001`.

---

After that, a sort of simulation of the EJ Portal terminal will initialise, with Noya guiding you along the process.

Below will be some transcripts of each stage in the challenge and what command you are supposed to type.

---

Stage 1:

```
Noya: hey you're here! real quick, can you help me change my grades?
Noya: i failed h2 math and i need to improve my score...
Noya: what do you say we hack into EJ Portal and give me an A?

Your choice (yes/no):
```

Entering any option will cause Noya to hack into "EJ Portal" anyway, proceeding to the next stage.

---

Stage 2:

```
Noya: alright, we're in!
Noya: hmmm, we got shell access, but i have no idea what files are here...
Noya: what command should we type to list just the files and folders here?
Noya: dont give me any extra options, i'm too lazy to type them.

admin@ejportal:/srv#
```

The command we need to enter is `ls`, which lists files and folders in the current directory.

Entering commands like `ls -l` or `ls -a` will fail here because Noya specifies no options.

Regardless, Noya realises at the last moment that he can enter `ls -l` for a more detailed view anyway and does it.

---

Stage 3:

```
admin@ejportal:/srv# ls -l
total 0
drwxrwxrwx 1 admin admin 4096 Jan 1 00:00 website_config
drwxrwxrwx 1 admin admin 4096 Nov 6 13:51 server_logs
drwxrwxrwx 1 admin teachers 4096 Nov 6 8:21 student_attendance
drwxrwxrwx 1 admin teachers 4096 Nov 6 13:51 student_grades
drwxrwxrwx 1 admin teachers 4096 Feb 30 15:30 student_personal_details
drwxrwxrwx 1 admin teachers 4096 Aug 7 12:03 teacher_personal_details

Noya: alright, we got some folders! i think student_grades is our best bet...
Noya: now enter the command to access that folder!

admin@ejportal:/srv#
```

The command we need to enter is `cd student_grades`, since `cd` allows us to change directory and access the folder.

Alternatively, you can enter `cd /srv/student_grades`, but Noya will point out how needlessly long it is.

---

Stage 4:

```
admin@ejportal:/srv# cd student_grades

admin@ejportal:/srv/student_grades#

Noya: now that you've seen me use that detailed ls command, can you repeat it again?

admin@ejportal:/srv/student_grades#
```

This is a callback to when Noya used the `ls -l` command for a more detailed file/folder listing.

Simply enter it again to proceed to the next stage.

--- 

Stage 5:

```
admin@ejportal:/srv/student_grades# ls -l
total 0
...
-rwxrwxrwx 1 admin teachers 0 Dec 30 01:22 ang_wei_sheng_wilson.csv
-rwxrwxrwx 1 admin teachers 0 Dec 30 01:22 caleb_kow_rong_pin.csv
-rwxrwxrwx 1 admin teachers 0 Dec 30 01:22 chang_yuhao.csv
-rwxrwxrwx 1 admin teachers 0 Dec 30 01:22 michael_hanson_sugiharto.csv
-rwxrwxrwx 1 admin teachers 0 Dec 30 01:22 noya_otter.csv
-rwxrwxrwx 1 admin teachers 0 Dec 30 01:22 zhang_di.csv

Noya: wow, they store all their students grades in CSVs instead of a database?
Noya: maybe this'll be easier than i thought!
Noya: oh, you don't know what's a CSV? it's just a text file of comma-separated values...
Noya: first, i need to see what my CSV looks like...
Noya: can you give me a command that lists its full contents?

admin@ejportal:/srv/student_grades#
```

The command we want to enter is `cat noya_otter.csv` here.

This is because the `cat` command displays the full text contents of a file.

Additionally, `noya_otter.csv` is the CSV of interest, since it has Noya's name.

---

Stage 6:

```
admin@ejportal:/srv/student_grades# cat noya_otter.csv
Physics, Chemistry, Mathematics, Economics
75, 71, 56, 60
46, 75, 50, 86
70, 74, 31, 57

Noya: yep, those are my results!
Noya: i think the second, third, and fourth row is wa1, wa2, and promos...
Noya: this should be easy to edit! can you help me type a command to open my csv on a text editor?

admin@ejportal:/srv/student_grades#
```

This was not in the workshop, but there are commands that can help you open a file in a text editor on a Linux terminal!

One of them is `nano noya_otter.csv`, which uses the nano text editor.

Another alternative is `vim noya_otter.csv`, which uses the vim editor.

Both work, so choose either one.

---

Stage 7:

```
Noya: alright, i should've saved it, but let's check one more time.
Noya: using cat again, can you view the contents of noya_otter.csv once more?

admin@ejportal:/srv/student_grades#
```

Noya wants you to use the `cat` command again, so just enter `cat noya_otter.csv`.

---

Stage 8:

```
admin@ejportal:/srv/student_grades# cat noya_otter.csv
Physics, Chemistry, Mathematics, Economics
75, 71, 56, 60
46, 75, 50, 86
70, 74, 78, 57

Noya: nice, now my math grade is saved!
Noya: hmmmm... but i've yet to reward you for your help...
Noya: try create an empty file called thanks.txt with another command, i'll give you something!

admin@ejportal:/srv/student_grades#
```

The command we want to enter is `touch thanks.txt`.

This is because the `touch` command is used to create an empty file of that name.

---

Stage 9:

```
Noya: alright, i added something in the text file... one final cat and you'll see!

admin@ejportal:/srv/student_grades#
```

Remembering the text name, you can reuse the `cat` command we have already seen.

Enter `cat thanks.txt` as your final answer!

--- 

Finally, after all those Linux commands, the contents of the file will show you the flag!

```
admin@ejportal:/srv/student_grades# cat thanks.txt
Thanks for all the help with changing my grades! :)

As a reward, here's your flag: EJCTF{eLit3_l1nuX_haXx0r}!

Here's some other commands I couldn't cover:
cd .. -> Goes to previous directory
pwd -> Print your current directory
mkdir -> Make a new directory
mv /path/to/f /newpath/to/f -> Move a file to another directory
mv oldname.txt newname.txt -> Rename a file in the same directory
rm file.txt -> Delete a file
rm -r my_directory -> Delete a directory
cp /path/to/source /path/to/dst -> Copy a file from one path to another
head file.txt -> Show the first 10 lines of a file
tail file.txt -> Show the last 10 lines of a file
```






