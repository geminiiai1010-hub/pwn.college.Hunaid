# Learning from documentation
In this challenge you'll have to figure out how to use all these commands for figure out the way to the flag.
## My solve
**Flag** `pwn.college{EageE5bgrGJ4hRITPDjL7dXaovb.QX0ITO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@man~learning-from-documentation:~$ 
```
2. Use the command `/challenge/challenge` along with the argument `--getflag`
```bash
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{EageE5bgrGJ4hRITPDjL7dXaovb.QX0ITO0wSM3gjNzEzW}
```
## What i learned
1. You can give argument with `/challenge/challenge`
## References
https://pwn.college/linux-luminarium/man/ - Learning from documentation

# Learning Complex Usage
This challenge requires you to use complex commands to capture the flag.
## My solve
**Flag** `pwn.college{YBiV-U8QBRHUW_2GmFZK1gRYOWM.QX1ITO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@man~learning-complex-usage:~$
```
2. Use `/challenge/challenge` with appropriate argument (The argument to be used is `/flag`).
```bash
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{YBiV-U8QBRHUW_2GmFZK1gRYOWM.QX1ITO0wSM3gjNzEzW}
```
## What i learned
1. `--printfile` is used to print arbritary files to the terminal
2. Syntac of --printfile `absolute path --printfile absolute path of file`
## References
https://pwn.college/linux-luminarium/man/ - Learning complex usage

# Reading manuals
This challenge requires to use the `man` command to open the manual of a command and use that manula to solve the challenge.
## My solve
**Flag** `pwn.college{A6f5o3ESO2c6xkZeU8T_3LXcmtp.QX0EDO0wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~reading-manuals:~$
```
2. Open the manual for the `challenge` command using `man` which is shortform for manual.
```bash
hacker@man~reading-manuals:~$ man challenge
(This is what opens up after using the command)
CHALLENGE(1)                              Challenge Commands                              CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --focxke NUM
              print the flag if NUM is 653

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
```
3. Use `/challenge/challenge` along with the `--focxke` command and the number given which prints the flag.
```bash
hacker@man~reading-manuals:~$ /challenge/challenge --focxke 653
Correct usage! Your flag: pwn.college{A6f5o3ESO2c6xkZeU8T_3LXcmtp.QX0EDO0wSM3gjNzEzW}
```
## What i learned
1.How the manual command works and what it does.
2.The syntax of the manual command is `man command_name`.
3.`man` is shortform of manual.
4. The manual command give all the details for the command given as the argument.
## References
https://pwn.college/linux-luminarium/man/ - Reading manuals.

# Searching manuals
This challenge requires you to search in the manual for the argument which outputs the flag.
## My solve
**Flag** `pwn.college{gfrvzSvfGzI50i4U0tKmlAsqD-C.QX1EDO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@man~searching-manuals:~$
```
2. Open the manual for the `challenge` command using the `man` command.
```bash
hacker@man~searching-manuals:~$ man challenge
CHALLENGE(1)                               Challenge Commands                               CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right argument.

       --fortune
              read a fortune

       --version
              output version information and exit

       --jem  A neat argument, but not the right one.

       --mqj  A neat argument, but not the right one.

       --gqk  A neat argument, but not the right one.
.......
```
3. Using the `/` command in the manual helps search for the word required. In this case i searched for `flag`.
```bash
--mmxexp
              This argument will give you the flag!
```
4. Put the correct argument along with `/challenge/challenge` to output the flag.
```bash
hacker@man~searching-manuals:~$ /challenge/challenge --mmxexp
Initializing...
Correct usage! Your flag: pwn.college{gfrvzSvfGzI50i4U0tKmlAsqD-C.QX1EDO0wSM3gjNzEzW}
```
## What i learned
1. In the manual's of commands `/` can be used to search for words you are looking for.
2. `n` can be used to move onto the next ocurence of the word.
3. `N` can be used to move to the previous occurence of the word.
4. This way navigating throught manual's for help is easy.
## References
https://pwn.college/linux-luminarium/man/ - Searching Manuals

# Searching for manuals

# Helpful Programs
This challenge requires you to use the `--help` command to print the flag value.
## My solve
**Flag** `pwn.college{wWcsfXMSyETIWC-omr2uTLCZYk2.QX3IDO0wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@man~helpful-programs:~$
```
2. Use `--help` along with `/challenge/challenge`.
```bash
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
```
3. Next I used the `-p` to print the unique number.
```bash
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 223
```
4. Used the unique number with `-g`. This would give the flag value.
```bash
hacker@man~helpful-programs:~$ /challenge/challenge -g 223
Correct usage! Your flag: pwn.college{wWcsfXMSyETIWC-omr2uTLCZYk2.QX3IDO0wSM3gjNzEzW}
```
## What i learned
1. The use of `--help` is to tell how to run special arguments, because not all the commands have a manspage.
2. The syntax of help is `command --help`.
3. There are multiple ways to use the help command.
## References
https://pwn.college/linux-luminarium/man/ - Helpful Programs

# Help for buitlin
Some commands, are buitlin rather than being programmed by manspage. These types of commands use the help command to list out the different arguments that can be used.
## My solve
**Flag** `pwn.college{8LXWX8jTq-IHx1rXdDPcH4z71E8.QX0ETO0wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@man~help-for-builtins:~$
```
2. So in this challenge the `challenge` is a shell builtin. So, you are required to use help to find the argument to be used to find the flag.
```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "8LXWX8jT".
```
3. In the output of the last command we can see that `--secret` prints the flag. The value to be provided to the `--secret` is also given which is `8LXWX8jT`.
```bash
hacker@man~help-for-builtins:~$ challenge --secret 8LXWX8jT
Correct! Here is your flag!
pwn.college{8LXWX8jTq-IHx1rXdDPcH4z71E8.QX0ETO0wSM3gjNzEzW}
```
## What i learned
1. The `help` command is only for shell builtin commands.
2. The syntax for help is `help command_name`.
3. Help prints out the arguments that can be used with the command.
4. Help 
