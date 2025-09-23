# Comprehending Commands
This module will expose you to some useful linux commands.

# Cat: not the pet, but the command!
This challenge required you to use the `cat` command to read the flag from a file.
## Mysolve
**Flag** `pwn.college{oAu5nqRHdB_QEkXoGT9IbGLJ2jV.QXxcTN0wSM3gjNzEzW}`
1. Connect the dojo host with the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~cat-not-the-pet-but-the-command:~$
```
2. Use the `cat` command along with the file name 'flag'.
```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{oAu5nqRHdB_QEkXoGT9IbGLJ2jV.QXxcTN0wSM3gjNzEzW}
```
## What i learned
1. The cat command is used to read the file.
2. The syntax for the cat command is `cat file_name`
## References
https://pwn.college/linux-luminarium/commands/ - Cat: nto the pet, but the command!

# Catting absolute paths
In this challenge the `cat` commands argument is going to be an absolute path
## My solve
**Flag** `pwn.college{QZ5-_W4VXdQwhzEBz45nzisIxWi.QX5ETO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~catting-absolute-paths:~$
```
2. Use the `cat` command along with the absolute path `/flag`.
```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{QZ5-_W4VXdQwhzEBz45nzisIxWi.QX5ETO0wSM3gjNzEzW}
```
## What i learned 
How the `cat` command can be used along with absolute path as the argument
## References
https://pwn.college/linux-luminarium/commands/ - Catting absolute paths

# More catting practice
This challenge we have to use absolute path as argument for the `cat` command.
## My solve
**Flag** `pwn.college{Qk3uRVUAuWmNXmNJjO519Ixz4_v.QXwITO0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /usr/lib/ecl/flag. Go cat it out **without** cding into that 
directory!
hacker@commands~more-catting-practice:~$ 
```
2. Use the `cat` command along with the absolute path provided.
```bash
hacker@commands~more-catting-practice:~$ cat /usr/lib/ecl/flag
pwn.college{Qk3uRVUAuWmNXmNJjO519Ixz4_v.QXwITO0wSM3gjNzEzW}
```
## What i learned
The `cat` command can be used with any lenght of absolute path.
## References
https://pwn.college/linux-luminarium/commands/ - More catting practice

# Grepping for a needle in a haystack
This challenge requires you to use the `grep` command instead of `cat`.
## My solve
**Flag** `pwn.college{svmoqwIU6oL_OY3RCng5GFueObu.QX3EDO0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~grepping-for-a-needle-in-a-haystack:~$
```
2. Use the `grep` command with the search string as `pwn.college.` and the absolute path as `/challenge/data.txt`.
```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{svmoqwIU6oL_OY3RCng5GFueObu.QX3EDO0wSM3gjNzEzW}
```
## What i learned
1. The syntax of grep command `grep search_string absolute path`.
2. The grep works by searching the start of a string and then outputs the string to the user.
## References
https://pwn.college/linux-luminarium/commands/ - Grepping for a needle in a haystack

# Comparing files
This challenge needs you to use and understand the working of `diff` command.
## My solve
**Flag** `pwn.college{QiYS2a4N3jLLFQSemp_lA5UhJeE.01MwMDOxwSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~comparing-files:~$
```
2. Use the `diff` command along with the txt files given.
```bash
hacker@commands~comparing-files:/challenge$ diff decoys_only.txt decoys_and_real.txt
78a79
> pwn.college{QiYS2a4N3jLLFQSemp_lA5UhJeE.01MwMDOxwSM3gjNzEzW}
```
## What i learned
1. The syntax of diff `diff file1 file2`
2. The output for the above command will we the diff between the files.
```bash
hacker@dojo:~$ cat old
pwn
hacker@dojo:~$ cat new
pwn
college
hacker@dojo:~$ diff old new
1a2
> college
```
## References
https://pwn.college/linux-luminarium/commands/ - Comparing files

