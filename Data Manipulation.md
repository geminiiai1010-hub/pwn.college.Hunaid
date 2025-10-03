# Data Manipulation
This challenge expands on the piping of data
# Translating characters
This challenge requires you to swap cases of each of the character using the `tr` command
## My solve
**FLag** `pwn.college{g2Cqw-bapvfYkAgyvfv_DwqiwFj.01MxEzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@data~translating-characters:~$
```
2. Use the `/challenge/run` command followed by `|` then using `tr` to swap cases the arguments should be `ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz` and `abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ` these two arguments should be written properly as uneven matching can lead to wrong change of character. In this case if the character is `A` it will get swapped with `a` and soo on. This will work the other way also.
```bash
hacker@data~translating-characters:~$ /challenge/run | tr ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
yOUR CASE-SWAPPED FLAG:
pwn.college{g2Cqw-bapvfYkAgyvfv_DwqiwFj.01MxEzNxwSM3gjNzEzW}
```
## What i learned
1. The `tr` command can be used to swap characters for output of a command.
2. syntax `command | tr arg1 arg2`.
## References
https://pwn.college/linux-luminarium/data/ - Translating characters.

# Deleting Characters
This challenge requires you to remove characters from the output of a command using `tr`
## My solve
**Flag** `pwn.college{saMvivQWvyoA2LS60OkwkkzmnAg.0FNxEzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@data~deleting-characters:~$
```
2. Run the command `/challenge/run` as we have to remove characters from the flag. Followed by that use `tr` with `-d` this indicates that we are deleting characters. The character to be deleted are `^%`.
```bash
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{saMvivQWvyoA2LS60OkwkkzmnAg.0FNxEzNxwSM3gjNzEzW}
```
## What i learned
1. `tr` with `-d` can be used to delete characters from output of a command.
2. Syntax `command | tr -d character_to_delete`.
## References
https://pwn.college/linux-luminarium/data/ - Deleting characters

# Deleting newline
This challenge requires you to use `tr` to delete newlines.
## My solve
**Flag** `pwn.college{cjiE2m69t6nx7l2oUmXJQ34ikFj.0VNxEzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@data~deleting-newlines:~$
```
2. Use the command `/challenge/run` as that gives the flag. As we have to delete the newlines we need to use `tr` with `-d` and `"\n"` as \n indicates newline.
```bash
hacker@data~deleting-newlines:~$ /challenge/run | tr -d "\n"
Your line-split flag: pwn.college{cjiE2m69t6nx7l2oUmXJQ34ikFj.0VNxEzNxwSM3gjNzEzW}hacker@data~deleting-newlines:~$
```
## What i learned
1. We can delete newline using the `tr -d` command.
2. newline need to be in double quotes like `"\n"`.
3. Syntax ` command | tr -d "\n" `
## References
https://pwn.college/linux-luminarium/data/ - Deleteing newline

# Extracting the first lines with head
This challenge requires you to use the `head` command to extract the first few lines.
## My solve
**Flag** `pwn.college{ofxdwfFdtoomQq8fJ34CscDgydu.0lNxEzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@data~extracting-the-first-lines-with-head:~$
```
2. As we have to extract the first 7 lines from the `/challenge/pwn` file we have to use `head -n 7`. We have to pipe the data to the file `/challenge/college`.
```bash
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{ofxdwfFdtoomQq8fJ34CscDgydu.0lNxEzNxwSM3gjNzEzW}
```
## What i learned
1. `Head` can be used to read the first few lines of output from a command.
2. The default number opf line is 10.
3. We can change the number of lines using `-n`.
4. Syntax `command | head -n no. `
## References
https://pwn.college/linux-luminarium/data/ - Extracting the first lines with head

