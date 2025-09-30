# Practicing Piping
This module will teach you about input and output redirection. Simply put, every process in Linux has three initial, standard channels of communication
# Redirecting Output
This challenge gives the first look to redirecting stdout to files.
## My solve
**Flag** `pwn.college{kKd8YM1HZsAj3KBKl9VX-TbQNci.QX0YTN0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
You have created the COLLEGE file and wrote the right value to it, but it 
doesn't look like you did it via input redirection.
hacker@piping~redirecting-output:~$
```
2. The command `echo` is used to output a phrase. So in this case we have to use `echo` followed by `PWN` to redirect it to file `COLLEGE` we have to use `>`.
```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{kKd8YM1HZsAj3KBKl9VX-TbQNci.QX0YTN0wSM3gjNzEzW}
```
## What i learned 
1. `>` can be used to redirect the output.
2. `echo` can be used along with `>` followed by file name to redirect output to a file.
## References
https://pwn.college/linux-luminarium/piping/ - Redirecting output

# Redirecting more output
In this challenge you are supposed to redirect output from command instead from `echo`.
## My solve
**Flag** `pwn.college{Y-QpcWwM1ESckYgLifuO0Lsbmah.QX1YTN0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~redirecting-more-output:~$
```
2. Use the command `/challenge/run` along with `>` and file name `myflag` to redirect the output from `/challenge/run` into myflag. This will store the flag value in the file `myflag`.
```bash
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
```
3. Now if we use `cat` to read the file `myflag` we will get the flag as the output.
```bash
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{Y-QpcWwM1ESckYgLifuO0Lsbmah.QX1YTN0wSM3gjNzEzW}
```
## What i learned
1. `>` can be paired with commands instead of `echo` statements to redirect the output to a file.
## References
https://pwn.college/linux-luminarium/piping/ - Redirecting more output.

# Appending output
In this challenge instead of using `>` we are using `>>` to redirect the output.
## My solve
**Flag** `pwn.college{4nn5UM33SyIJi8ye3fURTgyQVlj.QX3ATO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~appending-output:~$
```
2. First we have to use `>` to redirect the first half of the flag to the file `the-flag`.
```bash
hacker@piping~appending-output:~$ /challenge/run > the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
```
3. Then we have to use `>>` along with the same command as before that is `/challenge/run` and append in to the file `the-flag`. This step will overwrite onto the first half of the flag.
```bash
hacker@piping~appending-output:~$ /challenge/run >> the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
```
4. Read the file `the-flag` using the command `cat`.
```bash
hacker@piping~appending-output:~$ cat the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{4nn5UM33SyIJi8ye3fURTgyQVlj.QX3ATO0wSM3gjNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
```
## What i learned
1. `>>` can be used to append stuff into a file.
2. `>>` can be paired with either the file name or the absolute path to the file to append the stuff.
3. `>>` can overwrite redirection of `>`.
## References
https://pwn.college/linux-luminarium/piping/ - Appending output

# Redirecting errors
This challenge requires you to redirect the errors into a file.
## My solve
**Flag** `pwn.college{I-TYLbwXI4imGuGwulo0x7Yktkq.QX3YTN0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~redirecting-errors:~$ 
```
2. As we have to redirect the errors into `instructions` and the output to the `myflag` file we will have to first use `>` then `2>` the 2 in this case will tell the terminal to redirec the errors.
```bash
hacker@piping~redirecting-errors:~$ /challenge/run >myflag 2> instructions
```
3. We can read the files `myflag` and `instructions` using the `cat` command.
```bash
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{I-TYLbwXI4imGuGwulo0x7Yktkq.QX3YTN0wSM3gjNzEzW}
```
## What i learned
1. Errors can be redirected using `2>` into any file.
## References
https://pwn.college/linux-luminarium/piping/ - Redirecting errors

# Redirecting input
This challenge required you to use `<` to redirect input from a command to a file.
## My solve
**Flag** `pwn.college{89rtENaU1j6ZxN9stj5lnenKcpT.QXwcTN0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~redirecting-input:~$
```
2. Redirect the output `COLLEGE` using `echo` and into the file `PWN`
```bash
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
```
3. Redirect the input using command `/challenge/run` into the file `PWN`.
```bash
hacker@piping~redirecting-input:~$ /challenge/run <PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{89rtENaU1j6ZxN9stj5lnenKcpT.QXwcTN0wSM3gjNzEzW}
```
## What i learned
1. `<` can be used to redirect input to a file.
2. Syntax `command < file_name`.
## References
https://pwn.college/linux-luminarium/piping/ - Redirecting input

# Grepping stored results 
This challenge required to redirect output and then search for the flag.
## My solve
**Flag** `pwn.college{ArzAkQQbHjVLCf-RTIqe1urQCYo.QX4EDO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~grepping-stored-results:~$
```
2. Redirect the output from the command `/challenge/run` to the file `/tmp/data.txt`. This file will now have 100 of lines of data.
```bash
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
```
3. To search for the flag we have to use the command `grep` that searches for the argument. Here the argument to be given should be `pwn.college` as all the flags start with that. The file's absolute path should be provided `/tmp/data.txt`
```bash
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{ArzAkQQbHjVLCf-RTIqe1urQCYo.QX4EDO0wSM3gjNzEzW}
```
## What i learned
1. `>` can redirect huge amount of output also.
## References
https://pwn.college/linux-luminarium/piping/ - grepping stored results.

# Grepping Live Output
This challenge requires you to use a syntax for the command such that you can grep without storing the data.
## My solve
**Flag** `pwn.college{445UGz61T1bTFHk9AJPg2LE9muQ.QX5EDO0wSM3gjNzEzW}`
1. Connect to the dojo using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~grepping-live-output:~$
```
2. So we need to grep the flag without storing the data in a file. To do that we need to seperate the command and grep statement with `|`. The command to run will be `/challenge/run` and the gre statement will be `grep pwn.college` as all the flag's start with pwn.college.
```bash
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{445UGz61T1bTFHk9AJPg2LE9muQ.QX5EDO0wSM3gjNzEzW}
```
## What i learned
1. The `|` can be used to grep data without storing the data in a file.
2. Syntax ` command | grep data`
## References
https://pwn.college/linux-luminarium/piping/ - Grepping live output.

# Grepping errors
This challenge requires you to grep errors from the command using `2>& 1`.
## My solve
**Flag** `pwn.college{0cdXaWeIv3WueHpEH2wtJ_CSKKo.QX1ATO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~grepping-errors:~$
```
2. Run the command `/challenge/run` followed by `2>& 1` and then seperate this with `|` to write the grep statement. The grep statement will be `grep pwn.college` as all the flags start with pwn.college.
```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{0cdXaWeIv3WueHpEH2wtJ_CSKKo.QX1ATO0wSM3gjNzEzW}
```
## What i learned
1. The command `2>& 1` should be used to get the errors and then use grep to get the required data.
2. Syntax ` command 2>& 1 | grep data_to_search`.
## References
https://pwn.college/linux-luminarium/piping/ - Grepping errors.

# Filtering with grep -v
This challege requires you to filter from multiple decoy flags.
## My solve
**Flag** `pwn.college{4sJisc0BPDw4UZVeb3WxlggxFwA.0FOxEzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~filtering-with-grep-v:~$
```
2. Use the command `/challenge/run`. This command will provide 1000 flags with one real flag. Then sepearte the command with `\` to use grep statement. In this case we have to use `grep -v` as we want to filter the real one out of the 999 flags containing the word decoy.
```bash
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{4sJisc0BPDw4UZVeb3WxlggxFwA.0FOxEzNxwSM3gjNzEzW}
```
## What i learned
1. The grep statement can be paired with `-v` to remove the matches from the output.
2. Syntax ` grep -v data_to_not_search_for`
## References
https://pwn.college/linux-luminarium/piping/ - Filtering with grep -v

# Duplicating Piped Data

# Process Substitution for data
In this challenge you have to compare outputs of 2 files using process substitution and the `diff` command.
## My solve
**Flag** `pwn.college{sAG6vqUvwvgzWk-f8nhzW1o8xzw.0lNwMDOxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~process-substitution-for-input:~$
```
2. As we have to find the difference between the outputs of both the commands we have to use `diff` along with the commands seperated with `<`.
```bash
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
52a53
> pwn.college{sAG6vqUvwvgzWk-f8nhzW1o8xzw.0lNwMDOxwSM3gjNzEzW}
```
## What i learned
1. What is process substitution and how it works
## References
https://pwn.college/linux-luminarium/piping/ - Process Substitution for data

