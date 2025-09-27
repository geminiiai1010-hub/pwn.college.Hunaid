# Matching with *
This challenge is about learning about the glob `*` and applying it in codes.
## My solve
**Flag** `pwn.college{czDRGPLsw71VhO40r7-orf4r3_F.QXxIDO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~matching-with-:~$
```
2. This challenge is about using the glob `*` and changing the current directory to /home/challenges. But the constraint is only using at most 4 characters in the argument of `cd`
```bash
hacker@globbing~matching-with-:~$ cd /ch*
```
3. Run `/challenge/run` to output the flag.
```bash
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{czDRGPLsw71VhO40r7-orf4r3_F.QXxIDO0wSM3gjNzEzW}
```
## What i learned
1. What is `*` : - '*' is a character that is used as a wildcard. When used in a file name the terminal searches for all the files that matches the format of the file name. But if the file name doesnt match the terminal leaves the glob as it is.
2. The syntax of `*` `File_name*`. This is one way of using the `*`.
3. The `*` matches any part of the file except the `/` and `.`.
## References
https://pwn.college/linux-luminarium/globbing/ - Matching with *

# Matching with ?
This challenge is about `?` and what happens when you encounter it in your programs as an argument.
## My solve
**Flag** `pwn.college{YRtXTlRoIwlYIZySNmY1Ukd1ZUo.QXyIDO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$
```
2. In this challenge the use of `c` , `h`, `*` is not permitted instead we are supposed to use `?`. So first we have to move to the `/challenge` directory.
```bash
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$
```
3. Same as the above line we have to run `/challenge/run` to get the flag but we cant use `c`, `h` and `*` .
```bash
hacker@globbing~matching-with-:/challenge$ /?ha??enge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{YRtXTlRoIwlYIZySNmY1Ukd1ZUo.QXyIDO0wSM3gjNzEzW}
```
## What i learned
1. The `?` works similar to the `*` but instead of acting as wildcard for multiple characters it acts as a wildcard only for one character.
2. The `?` can replace any character to fill in one place in a argument.
## References
https://pwn.college/linux-luminarium/globbing/ - Matching with ?

# Matching with []
In this challenge we have to use `[]` to provide a subset of the characters which can be matched for a wildcard.
## My solve
**Flag** `pwn.college{IQy8WFEdRjsjSgK00ODD_tfJX89.QXzIDO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~matching-with-:~$
```
2. Make the `/challenge/files` the current directory using `cd` as that contains all the files.
```bash
hacker@globbing~matching-with-:~$ cd /challenge/files
```
3. To get teh flag value we have to run `/challenge/run` but with an argument which is `file_[]` the brackets should contain the characters that the terminal should look for in the current directory.
```bash
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{IQy8WFEdRjsjSgK00ODD_tfJX89.QXzIDO0wSM3gjNzEzW}
```
## What i learned
1. The `[]` can be used as a easy replacement of the `?` as we can mention specific characters to search for.
2. While using `[]` it should contain subset of the characters to search for.
## References
https://pwn.college/linux-luminarium/globbing/ - Matching with []

# Matching paths with []
In this challenge instead of making the `/challenge/files` the current directory we have to use `[]` to give absolute path to the files.
## My solve
**Flag** `pwn.college{AvQx5s8BpvuouVjQJFX49oFGgqc.QX0IDO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~matching-paths-with-:~$
```
2. Without making `/challenge/files` the current directory run the command `/challenge/run` along with an absolute path as the argument. The absolute path is `/challenge/files/file_[absh]` (i am using the brackets as the directory has multiple files).
```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[absh]
You got it! Here is your flag!
pwn.college{AvQx5s8BpvuouVjQJFX49oFGgqc.QX0IDO0wSM3gjNzEzW}
```
## What i learned
1. The `[]` can be used also in absolute paths instead of just arguments.
2. The syntax in both the cases remains the same.
## References
https://pwn.college/linux-luminarium/globbing/ - Matching paths with []

# Multiple Globs
This challenge make you use multiple `*` in the argument.
## My solve 
**Flag** `pwn.college{IOmXNABc_sUu3e9oeUjPEobW0S5.0lM3kjNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~multiple-globs:~$
```
2. We need to `cd` to the `/challenge.files` directory as that contains the files with the flag.
```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$
```
3. We need to look in files that have the character `p` in its name. So we can use the command `/challenge/run` with the `*p*` as the argument.
```bash
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{IOmXNABc_sUu3e9oeUjPEobW0S5.0lM3kjNxwSM3gjNzEzW}
```
## What i learned
1. The command line can comprehend multiple globs in the same argument or command.
## References
https://pwn.college/linux-luminarium/globbing/ - Multiple globs

# Mixing Globs
This challenge required you to use multiple globs `*`, `[]`, `?`.
## My solve
**Flag** `pwn.college{cKQn4vvtujNYYi4ZVKyyplVlGbX.QX1IDO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~mixing-globs:~$
```
2. `cd` to the `/challenge/files` directory as that contains the file with he flag.
```bash
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$
```
3. We have to search for the files (challenging, educational, pwning) so, i searched for the starting letters of each of the files using `[]` to search the starting characters and then using `*` for the following characters.
```bash
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [pec]*
You got it! Here is your flag!
pwn.college{cKQn4vvtujNYYi4ZVKyyplVlGbX.QX1IDO0wSM3gjNzEzW}
```
## What i learned
1. The commamd line can comprehend multiple types of globs at the same time in the same absolute path or argument.
## References
https://pwn.college/linux-luminarium/globbing/ - Mixing globs

# Exclusionary globbing
This challenge is to search for the opposite of what is mentioned in the `[]`.
## My solve
**Flag** `pwn.college{cKQn4vvtujNYYi4ZVKyyplVlGbX.QX1IDO0wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~mixing-globs:~$
```
2. `cd` to the `/challenge/files` directory as tht contains the files with the flag.
```bash
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$
```
3. As you have to find the characters other than whats in the brackets so, for that the command required is `/challenge/run` along with the argument `[!pwn]*`.
```bash
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [!pec]*
You got it! Here is your flag!
pwn.college{cKQn4vvtujNYYi4ZVKyyplVlGbX.QX1IDO0wSM3gjNzEzW}
```
## What i learned
1. `!` or `^` can be used to find the opposite of what is mentioned in the brackets.
2. This can be used with `[]` only but can paired with other globs like `*` or `?`.
## References
https://pwn.college/linux-luminarium/globbing/ - Exclusionary globbing

# Tab completion
This challenge tells puts the constrait of not typing the full file name instead using the tab key
## My solve
**Flag** `pwn.college{EnRN1HvoPR_IRKbooqBHOXUgfn-.0FN0EzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~tab-completion:~$
```
2. Type the `cat` command along with the file `/challenge/pwn` then press tab to complete the file name.
```bash
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ 
pwn.college{EnRN1HvoPR_IRKbooqBHOXUgfn-.0FN0EzNxwSM3gjNzEzW}
```
## What i learned
1. The tab key completes the argument that matches with the name in the directory.
2. If more than matches with the name it doesnt work.
## References
https://pwn.college/linux-luminarium/globbing/ - Tab completion

# Multiple options for tab completion
This challenge requires you to use tab to find the flag from multiple files starting with the same character
## My solve
**Flag** `pwn.college{8yRxo2oaXgeCRMmhCl2BJcg2I5v.0lN0EzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~multiple-options-for-tab-completion:~$
```
2. Type `/challenge/files/p` and then use the tab key to list out all the files starting with `p` character.
```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwn
```
3. After checking files `pwn` and `pwn-college` i found the flag in `pwncollege-flag`.
```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{8yRxo2oaXgeCRMmhCl2BJcg2I5v.0lN0EzNxwSM3gjNzEzW}
```
## What i learned
1. When there are multiple matches for the search using the tab key the command line lists out all the files that match.
## References
https://pwn.college/linux-luminarium/globbing/ - Multiple options for tab completion.

# Tab completion on commands
In this challenge you have to use the tab command on the command metioned in the question.
## My solve
**Flag** `pwn.college{crQXYAPj1IUw0jZ2r5DVSfUlXKj.0VN0EzNxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@globbing~tab-completion-on-commands:~$
```
2. Use the command mentioned which is `pwn.college` and use tb key which completes the command. That command provides the flag.
```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-3950 
Correct! Here is your flag:
pwn.college{crQXYAPj1IUw0jZ2r5DVSfUlXKj.0VN0EzNxwSM3gjNzEzW}
```
## What i learned
1. The tab key complete the commands that match too not only the file names and path names.
## References
https://pwn.college/linux-luminarium/globbing/ - Tab completion on commands.
