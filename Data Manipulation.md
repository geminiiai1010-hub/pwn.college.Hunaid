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

# Exctracting specific section of text
This challenge requires you to fetch a section of the output of the command.
## My solve
**Flag** `pwn.college{EtB7ZRF0TPlmNdgLvMRa9vMx_pm.01NxEzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@data~extracting-specific-sections-of-text:~$
```
2. As we have to take output from `/challenge/run` we use that followed by `cut -d " " -f 2 - ` and we have to eliminate newlines so we write `tr -d "\n"`.
```bash
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d ' ' -f2- | tr -d " \n"
pwn.college{EtB7ZRF0TPlmNdgLvMRa9vMx_pm.01NxEzNxwSM3gjNzEzW}
```
## What i learned
1. We can use cut to get sections of a text.
2. Syntax ` cut -d " " -f no. text_file.txt`
## References
https://pwn.college/linux-luminarium/data/ - Extracting specific section of text

# Sorting data
This challenge requires you to sort all the flags in a file to find the real one.
## My solve
**Flag** `pwn.college{ExphsPVZeZGKMVUCjquYyxJc9E_.0FM0MDOxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@data~sorting-data:~$
```
2. In the challenge it is told that when the flags are sorted the real flag will be at the end. So we can use the command ` sort /challenge/flags.txt` or to get the real flag at the top we can use `sort -r /challenge/flags.txt`.
```bash
hacker@data~sorting-data:~$ sort -r /challenge/flags.txt
pwn.college{ExphsPVZeZGKMVUCjquYyxJc9E_.0FM0MDOxwSM3gjNzEzW}
pwn.college{ExphsPVZeZGKMVUCjquYyxJc9E_.0FM0MDOxwSM3gjNzEzW}
pwn.college{ExphsPVZeZGKMVUCjquYyxJc9E_.0FM0MDNxwSM2gjNzEzW}
pwn.college{ExphsPVZeZGKLVUCjquYyxIc9E_.0FM0MDOxwSM3gjNzEzW}
pwn.college{ExphsPVZeZFKMVUCjquYyxJc9E_.0FM0LDOxwSM3gjNzEzW}
pwn.college{ExphsOVZeZGKMVUCjquYyxJc9E_.0FM0MDOxwSM3gjNzEzW}
pwn.college{ExphsOVZeZGKLVUCjpuYyxJc9E_.0FM0MDOxwSM3giNzEyW}
pwn.college{ExpgsPVZeYFJMVUCjquXxxJc9E_.0FM0MCOxwSL2gjMzDyW}
pwn.college{EwohsPVZeZGKMVUCjquYxxJc9E_.0FM0MDOxwSM3gjNyEyW}
pwn.college{DxpgsOVZeYGKMVTCiquYyxJb9E_.0EM0LDOxwSM3gjNzEzV}
pwn.collegd{ExphsPVZeZGKMVUCjpuYyxJc9E_.0FM0MDOxwSM3gjMzEzW}
pwn.collegd{ExphsPVZeZGKMVUCjpuXyxJb9E_.0FL0MDOxwSM3gjNzDzW}
pwn.collegd{ExphsOUZeZGKMUUCjqtYyxJc9E_.0FM0MDOxwSM3gjNyEzW}
pwn.collegd{ExphrPUZdZFKMUUCjpuXyxJc8D_.0FM0LDNwwSM3gjMyDzW}
pwn.collegd{DxphrPUZeZGKMVUCjquYyxJb9E_.0FM0MDOxvSM3gjNzEzW}
pwn.collefe{ExphsPVZdZGKMVUCjquYyxJc9E_.0FM0LCNwvRM3gjNyEyW}
pwn.collefe{ExphsPUZeZGKMVTCjptXxwJc9E_.0EL0LDNwwSM3fjNyEzW}
pwn.collefe{ExphrPVZdZGKMVUBjquYyxIb9E_.0FM0MDOxwSM3giMzEzW}
pwn.collefe{EwphrPVZeZFJLVUBiquXxxIc9E_.0FM0MDOxvSL2fjNzEyW}
pwn.collefd{ExogsPVZeZGKMUTCjquYyxJc9E_.0FM0MDOwwSM3gjNzEzW}
pwn.collefd{DxohsOVZdZFJMVUCjqtYyxJc9D_.0FM0MDOxwSL3giMzEzW}
pwn.colldge{DxphsPVZeZFJLUUCiptYxxJc9E_.0EL0MDNxwSM3gjNzEyV}
pwn.colldgd{ExphsPVZeZGKMVUBjquYyxIc9E_.0EM0MDNxvSL3fiNzEzW}
pwn.colldgd{DxpgsPVYeZGKMVUCjquYxxJc9E_.0FM0MDNwwSM3gjNzEzW}
pwn.colldgd{DxohsPUZeZGKMVUCjquXyxJc8E_.0FM0MDOxwRL3gjNyEzW}
pwn.colldfe{ExphsPVZeZGKMVUBjquYxxJc9E_.0FM0MDOxwSM3gjNzEzW}
pwn.colldfe{ExphrOUZeYGKMUTCipuXyxJc9E_.0FM0LCOxwRM3fjNzEzV}
pwn.colkege{ExphsPVZeZGKMVUCiquYywJc9E_.0FM0MDOxwSM3gjNzEzW}
pwn.colkege{EwphrPVZeZFKMUUCjquYxxJc9E_.0EM0MCOxwSM3gjNzEzW}
pwn.colkege{DwpgsPVZeZFJMUUBipuYxxJb8E_.0FL0MCOxwSM3fjMzDzW}
pwn.colkegd{DxohsPVZeZFKMVTCjqtYywIc9E_.0FL0MCNxvRM3fjNzEzW}
pwn.coklege{ExphsPVZeZGKMUUBiquYyxJc9E_.0FM0MDOxwSM3gjNzEzV}
pwn.coklege{ExphsPVZdZGKMVTCjquYyxJc9E_.0EM0MDOxwSL3fjNzEzW}
pwn.coklege{EwphsPVZeZGKMVUCjquYyxJb8E_.0EM0MDOxwSM3gjNzEzV}
pwn.coklege{DxphsPVZeYGKMVUCjptYyxJc9D_.0FM0MDOxwSM2fiNzEzW}
pwn.coklegd{ExphrPVZeZGKMVUCjquYxxJc9E_.0FM0MCOxwSM3gjNzEzW}
pwn.coklefe{ExphsPVZeZFKLVUCjpuYyxJc9E_.0FM0MDOxwSM2giNzDzW}
pwn.cokldge{ExphsPVYeZFKMVUCjquYyxIc9E_.0EM0MDOxwSM3gjNzEyW}
pwn.cokldgd{DxphsPVZeZGJMUUBjquXywJc9E_.0FM0LDOwwSM3giMzEzW}
pwn.cnllege{ExphsPVZeZGKMVUCjquYyxJc9E_.0FM0MDOxwSM2gjNzEzW}
pwn.cnllege{ExphsPVZeZGKMVUCjquYyxJc9E_.0FM0LDOxwSM3giNzEzW}
pwn.cnllege{ExphsPVZeZGJMVUCjpuYyxJc9E_.0FM0MDOwwSL3gjMyEzW}
pwn.cnllege{ExphsPUZeZGJLVUCjpuYywJc9E_.0FM0LDOxwRM3gjNzEzW}
pwn.cnllege{ExpgsPVZeZGKMVUBjquYyxJb8E_.0FM0MDOxwSM3gjNyEzW}
pwn.cnllege{DxphrPVZeZGKMVUBjquYywJc9E_.0EM0MCOxwSM2gjNzEzW}
pwn.cnllegd{ExphsPVZeZGKMVUCiquYywIc9D_.0FM0MDOxvRM3gjNzEzW}
pwn.cnllefe{ExogsOVZeZGKMVUCjquYxxJc9D_.0FM0LDOxwSM3gjMzEzV}
pwn.cnllefd{DxphsPVYeZGJMVUCjqtYyxIc9E_.0FL0MDOxwSM2gjNzEzV}
pwn.cnllefd{DxpgsPVZdZGKMVUCjquYyxJc8E_.0EM0MDOxwSM3gjMzEzW}
pwn.cnlldge{EwphsPVZdZGKLVUCjquXxxJc8E_.0FM0MDNwwSM3gjNzEzW}
pwn.cnlkege{ExphrPVYeZGKMUUBjquYyxIc8E_.0EM0MDOxwSM2gjNzDyV}
pwn.bollege{ExphsPVZeZGKMVUCjquYyxJc9E_.0FM0LDOxwSM3fjNzEzW}
pwn.bollege{ExphsPVZeZFJLVUCjpuXyxJc9E_.0FL0MDOxwSL2gjMzEzW}
pwn.bollege{ExphsOUZdYGKLVUBiptYyxJc8D_.0FM0MDOxvSM2gjNzDyV}
pwn.bollegd{EwphsPVZdZGKLVUCjquYxxJc9E_.0EM0LDOxwSM3fjMzDzW}
pwn.bollefe{ExohsOVZdZGKMVUBjpuXyxJc9D_.0FM0MCNwwRL3gjNzDyW}
pwn.bolldfe{ExphsPVZeZGKMVUCjquYyxJc9D_.0FM0MDOxwSM3gjNzEzW}
pwn.boklefd{DwphrPVZeZFKMUUBjptYywIc9D_.0FM0LDNxwRM3gjNzEyW}
pwn.bnllegd{EwogsPUYeYGKMUTCjquXywIc8D_.0FL0MDOxvRM3gjNyEyW}
pwm.colldge{ExphsPVYdZGKLVTCjqtYxwIc9E_.0FL0MDOwvSM3gjNzEzW}
pwm.colldgd{ExphsPVZeZGKMVTCjquYyxJc9E_.0EM0MCOxwSL3fjNyEzW}
pwm.colkdfe{ExphsPUYeZGKLVUBiqtYyxJc8E_.0FL0MDOxvRL2giNyDyW}
pwm.cnllefe{DxphsPVYeYGKLUUCipuYyxJc8E_.0FL0MDOwvRL2fjNzEyW}
pwm.cnlldgd{ExphsPVZeZGKMUUCjquYyxJc9D_.0EM0MDOxvSL3giNzEzW}
pwm.cnlkegd{DwphsPVZdZGKLUTCjquYxwJc9E_.0FL0MDNxwSL2gjNyEyW}
pwm.bollege{ExphsPVYdZGKMVUCjqtYyxJc9E_.0FM0MDOwwSM3fiNzDzW}
pvn.college{ExphsPVZeZGKMVUCjquYyxJc9E_.0FM0MDOxwSM2gjNzEzW}
pvn.college{ExphsOVZeZGKMVUCjquYyxJc9E_.0FM0MDOxwSM3gjNzEzW}
pvn.college{ExpgsPVYeYGKMVUCjquYyxJc9E_.0FL0MDOxwRM3fjNzEyW}
pvn.college{EwphrPUZeZGKMVTCiqtYxxJb8D_.0EL0MDOxwSL2giMyEzW}
pvn.college{DxphsPVZeZGKMVUCjquYxxJc9E_.0FM0MCOxwSM3gjNzEzW}
pvn.collegd{ExohrOVZdYGJMUUCjqtXyxIc9E_.0EM0MDOwvRM3giNzEzW}
pvn.cokkege{EwphsOUZeZGKMVTCiquYxxIc8E_.0EM0LDOxvRL3gjNzEzW}
pvn.cnklege{ExpgrPVYeZFJMVUCjquYyxIb9E_.0FL0MDNxvSL3giMzDzW}
pvn.bolldfd{DxpgsPVZdYFKLVUCjquXyxJc9E_.0FL0MDOwwSL3giMzEyW}
pvn.bolkegd{DxpgsPVZeZGKMVUCjqtYyxJc9E_.0FM0MDOxwRM2giMzEyW}
pvn.bolkefe{DxohsPVYeZGKMVTCjpuXyxIc9E_.0EM0MDOxwSM3gjNyEzW}
pvm.cokkdfe{DxphrPVYeZFKMUUCjquYxxIc8D_.0FM0LDOxwSM3gjNzEzW}
pvm.cnklege{ExogsOVZdZGJMVUCjpuYywJb9D_.0EL0MCOxwSL3gjMzEyW}
pvm.bollege{ExphsOVYeZGJLVUCjquXyxJc9E_.0FM0MDOxwSM3giNyEzV}
own.college{ExphrOVZeYFKMVUCjqtXywJc9E_.0FL0MCOwvSM2gjMzEzW}
own.collegd{ExphrPVZdZGKLVTCjquYyxJc9D_.0EM0MDOxwSM2fjNzEzW}
own.collegd{DxphrPVZeZGJMVUBjquYyxJb9E_.0EM0MDNxvRM3fjNzDzW}
own.collefe{EwohrPVYeYGKLVUCiquXywJb9D_.0FM0LCOwwSL3giNzDzW}
own.colkege{ExphsPUZdZGKLVUCiquYyxIc9D_.0FL0LDOxwSL3gjNyEyW}
own.colkege{ExphrOVZdZGKMVUBjqtYxxJc8E_.0FM0MDOxwSM3gjNzEzW}
own.colkefd{ExohrPUYdZFKLVTCiquYyxIb9D_.0FM0LDOxvSM3gjNyEzW}
own.cnllege{ExphsPVYeZGKMVUBjpuYxxJc9E_.0FL0MCOxvSM3gjNzEzW}
own.bollefe{DxogsOVYeZGKMVUBjqtXxxJc8E_.0FM0LDOxwSL3gjMzEyW}
own.bnklefd{DxphsPVZdZGJMUUCjquYywIc8D_.0FL0LDOxwRM2gjNzEzV}
owm.college{ExohsPVYdZFKMVTCjquXyxJc9D_.0FM0LCOxwSM3fiMzDyV}
owm.collefe{ExphrPVZeZGKMVUCjquYyxJc8E_.0EM0LDOxvSM2gjNyEzV}
owm.bnlldfe{DxphsPUZdZGKLVUBiquYyxIb8E_.0FM0MDOwwRM3gjNzDzW}
ovn.collegd{ExogsPVZeYGKMVTCipuYxwJc9E_.0EM0LDNxwSM2gjNyEzV}
ovn.cokkdge{ExogsOUZdZGJMUUCjqtXyxIc9E_.0FL0MCNwwSM3gjMzEzW}
ovn.cnlldge{DwpgsPUZeZFJMVUCjptYyxIc9D_.0FL0MDOxvSM2gjNzEzV}
ovn.cnlkege{ExpgsPVYeZGJMVUCipuYxxIb8E_.0EM0MDOxwRL3giNzEzV}
ovn.bollefe{DwpgsOVZdZGKMUTCjqtXyxJc9D_.0EL0MDNwvSL3giNzEyW}
ovn.bnlkdfe{DwphrPVYdZGJMUUCjpuYxxJb8D_.0FM0MDOxwRM3gjNyEzW}
ovm.cnklege{DxphsOVZdZFJMVUCjqtYxxIb8E_.0EM0MCOwwSM3giNzEzV}
ovm.bollege{ExpgsPVZeZGKLVUBiqtYxwIc8D_.0FM0MDOxvSL2fjMzEzW}
```
## What i learned
1. Sort can be used to sort data in a file.
2. We can use `-r` to reverse the order of sorting, `-n` can be used to sort according to number, `-u` can be used to sort unique lines only, `-R` can be used to sort in a random order.
3. Syntax ` sort file_name.txt`.
## References
https://pwn.college/linux-luminarium/data/ - Sorting data.


