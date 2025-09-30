# Shell Variable 
The Linux command line interface is actually a sophisticated programming language with which you can write actual programs! Because the command line interface is colloquially referred to as a "shell", programs written in this language are referred to as "shell scripts".
# Printing Variable
This challenge requires you to print the variable using `echo` and `$`.
## My solve
**Flag** `pwn.college{oEzRUMaBJgxKqe9DesLOO9xkU1c.QX3UTN0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@variables~printing-variables:~$
```
2. Use `echo` to print the flag value of the variable `FLAG`.
```bash
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{oEzRUMaBJgxKqe9DesLOO9xkU1c.QX3UTN0wSM3gjNzEzW}
```
## What i learned
1. Using echo with `$variable` prints the variable value.
## References 
https://pwn.college/linux-luminarium/variables/ - Printing variables

# Setting variables
This challenge requires you to assign a variable value to another variable.
## My solve
**Flag** `pwn.college{4MvfyaMAxwVgzn7xVF5e9fQzY8L.QX5UTN0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~setting-variables:~$
```
2. Set the variable PWN is equal to variable COLLEGE
```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4MvfyaMAxwVgzn7xVF5e9fQzY8L.QX5UTN0wSM3gjNzEzW}
```
## What i learned 
1. You can write values to variables using `=` sign.
## References
https://pwn.college/linux-luminarium/variables/ - Setting variables

# Multi-word variables.
This challenge requires you to set a multiple word data to a variable.
## My solve
**Flag** `pwn.college{ETCpiGkXcDq_-I0v1oJHgo0oPyz.QXwYTN0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~multi-word-variables:~$
```
2. Set the PWN variable equal to the string "COLLEGE YEAH"
```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{ETCpiGkXcDq_-I0v1oJHgo0oPyz.QXwYTN0wSM3gjNzEzW}
```
## What i learned
1. Variable can be set to multi - word values.
## References
https://pwn.college/linux-luminarium/variables/ - Multi-word variables

# Exporting Variables
This challenge requires to set a value for the variable and then export it.
## My solve
**Flag** `pwn.college{YIM1plhZgNGMIzIJTplj57pzAI2.QXyYTN0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~exporting-variables:~$
```
2. Set the variable `PWN` equal to the variable `COLLEGE` and vice-versa.
```bash
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ PWN=COLLEGE
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
3. Export the variable PWN so that it is accesible by other commands also and then run `/challenge/run`.
```bash
hacker@variables~exporting-variables:~$ export PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{YIM1plhZgNGMIzIJTplj57pzAI2.QXyYTN0wSM3gjNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
## What i learned
1. We need to export varaibles for them to be accessible by other commands.
## References
https://pwn.college/linux-luminarium/variables/ - Exporting Variables.

# Printing exported variables
This challenge requires you to use the `env` command to print the exported variables.
## My solve
**Flag** `pwn.college{ooyD-IwouRS4M5azFuQ6ycorY1o.QX4UTN0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~printing-exported-variables:~$
```
2. Run the `env` command and search for the flag in the output variables.
```bash
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=077e825908e052024199863a9c5b8426fb3d5ad56d6e237004b598ae9f616de8
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{ooyD-IwouRS4M5azFuQ6ycorY1o.QX4UTN0wSM3gjNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```
## What i learned
1. The env command can be used to print all the variables that have been exported.
## References
https://pwn.college/linux-luminarium/variables/ - Printing Exported Variables

# Storing command outputs
This challenge needs you to store command output directly into a variable.
## My solve
**Flag** `pwn.college{kEItGy5DE1FZpGD9u5DmjfKJuLA.QX1cDN1wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~storing-command-output:~$
```
2. Assign the output of `/challenge/run` to the variable `PWN`.
```bash
hacker@variables~storing-command-output:~$ PWN=`/challenge/run`
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
```
3. Read the value of the `PWN` variable using `echo`.
```bash
hacker@variables~storing-command-output:~$ cat "$PWN"
cat: pwn.college{kEItGy5DE1FZpGD9u5DmjfKJuLA.QX1cDN1wSM3gjNzEzW}: No such file or directory
```
## What i learned
1. The outputs of commands can be directly assigned to variables.
2. Syntax `variable_name=$(command)` or you can use back ticks instead of `$()`.
## References
https://pwn.college/linux-luminarium/variables/ - Storing command output.

# Reading Input
This challenge requires you to read input from the user to set value to a variable.
## My solve
**Flag** `pwn.college{0wZhntUp9Llg3yw3MlM6ZP5Bqvc.QX4cTN0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~reading-input:~$
```
2. Use the `read` command followed by `-p` to take input from the user to set the value to variable `PWN`.
```bash
acker@variables~reading-input:~$ read -p "Input: " PWN
Input: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{0wZhntUp9Llg3yw3MlM6ZP5Bqvc.QX4cTN0wSM3gjNzEzW}
```
## What i learned
1. Read can be used to get input from the user.
2. Syntax `read -p "Input statement" file_name`
## References
https://pwn.college/linux-luminarium/variables/ - Reading input.

# Reading Files
This challenge requires you to read the flag from a file.
## My solve
**Flag** `pwn.college{Q_HksBduY_D8kCQ3ELhyDNZHUSv.QXwIDO0wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~reading-files:~$
```
2. Use the `read` command to read from `/challenge/read_me` and assign to variable PWN.
```bash
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Q_HksBduY_D8kCQ3ELhyDNZHUSv.QXwIDO0wSM3gjNzEzW}
```
## What i learned
1. Read can be used to read from files also.
2. Syntax `read variable_name < file_name`
## References
https://pwn.college/linux-luminarium/variables/ - Reading files.

