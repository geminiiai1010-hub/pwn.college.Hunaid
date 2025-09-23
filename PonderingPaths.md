# Pondering Paths
This module contains 9 challenges each trying to help learn the concept of Linux file paths.

# The Root
This challenge teaches how to get the flag using /pwn.
## My solve
**Flag** `pwn.college{Q9WbHCYQXfhRmvnVDd9FSsY1RTb.QX4cTO0wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~the-root:~$
```
2. Now the command `/pwn` is to be used to get the flag.
```bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{Q9WbHCYQXfhRmvnVDd9FSsY1RTb.QX4cTO0wSM3gjNzEzW}
```
## What i learned
I learned to invoke a program by providing its path on the command line. In this case the starting of the path was from /, so the path would be /pwn.
## References 
https://pwn.college/linux-luminarium/paths/
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

# Program and absolute paths
This challenge requires you to write path more complex path.
## My solve
**Flag** `pwn.college{4ttxm6dZKIhpq2vOD8Q0cU_6jGx.QX1QTN0wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~program-and-absolute-paths:~$ 
```
2. Write the path to the `run` file.
```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{4ttxm6dZKIhpq2vOD8Q0cU_6jGx.QX1QTN0wSM3gjNzEzW}
```
## What i learned
How to navigate from the root directory into a nested directory and then to a file using the `/` command.
## References
https://pwn.college/linux-luminarium/paths/ - Program and absolute path
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

# Position thy self
This challenge make use of the `cd` (change directory) command to navigate around the directories.
## My solve
**Flag** `pwn.college{IT7eLfLeI7JFOjpgFCskECtkoIT.QX2QTN0wSM3gjNzEzW}`
1. Connect the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~position-thy-self:~$ 
```
2. Using `cd` navigate to the home directory then use the `/challenge/run` command.
```bash
hacker@paths~position-thy-self:~$ cd /home
hacker@paths~position-thy-self:/home$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{IT7eLfLeI7JFOjpgFCskECtkoIT.QX2QTN0wSM3gjNzEzW}
```
** My Mistake ** Before using `/challenge/run` command i was not navigating to the home directory instead i was navigating to the challenge directory.
```bash
hacker@paths~position-thy-self:~$ cd /challenge
hacker@paths~position-thy-self:/challenge$ /challenge/run
Incorrect...
You are not currently in the /home directory.
Please use the `cd` utility to change directory appropriately.
```
## What i learned
I learned how to navigate to different directories using `cd` command and fetch the flag using `/challenge/run` command.
## References
https://pwn.college/linux-luminarium/paths/ - Position thy self
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

# Position Elsewhere
This challenge talks about how `cd` can be used to navigate the directories and how it affects the current working directory.
## My solve
**Flag** `pwn.college{EqUqNJFLzrI9VZCu_0MT4dOFHtm.QX3QTN0wSM3gjNzEzW}`
1. Connect to dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~position-elsewhere:~$ 
```
2. Use `/challenge/run` to get the path to follow.
```bash
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /var/lib/apt/lists directory.
Please use the `cd` utility to change directory appropriately.
```
3. Navigate the path using `cd`.
```bash
hacker@paths~position-elsewhere:~$ cd /home
hacker@paths~position-elsewhere:/home$ cd /var
hacker@paths~position-elsewhere:/var$ cd lib
hacker@paths~position-elsewhere:/var/lib$ cd apt
hacker@paths~position-elsewhere:/var/lib/apt$ cd lists
hacker@paths~position-elsewhere:/var/lib/apt/lists$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{EqUqNJFLzrI9VZCu_0MT4dOFHtm.QX3QTN0wSM3gjNzEzW}
```
**My mistake ** Not navigating the path correctly.
```bash
hacker@paths~position-elsewhere:~$ cd home
bash: cd: home: No such file or directory
hacker@paths~position-elsewhere:~$ cd /home
hacker@paths~position-elsewhere:/home$ cd /var
hacker@paths~position-elsewhere:/var$ cd /lib
hacker@paths~position-elsewhere:/lib$ cd /apt
bash: cd: /apt: No such file or directory
```
## What i learned 
How to navigate the paths in a directory.
## References
https://pwn.college/linux-luminarium/paths/ - Position elsewhere
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

# Position yet elsewhere
This challenge same as others required to use `cd` to navigate different paths.
## My solve
**Flag** ` pwn.college{UYQtiAhVi5Mf2738MSkRZKMvuUZ.QX4QTN0wSM3gjNzEzW}'
1. Connect the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~position-yet-elsewhere:~$ 
```
2. Using the `/challenge/run` command get the path to follow.
```bash
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/bin directory.
Please use the `cd` utility to change directory appropriately.
```
3. Using `cd` command follow the path. 
```bash
hacker@paths~position-yet-elsewhere:~$ cd /usr
hacker@paths~position-yet-elsewhere:/usr$ cd bin
hacker@paths~position-yet-elsewhere:/usr/bin$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{UYQtiAhVi5Mf2738MSkRZKMvuUZ.QX4QTN0wSM3gjNzEzW}
```
## What i learned 
How to navigate the paths in a directory. 
## References
https://pwn.college/linux-luminarium/paths/ - Position yet elsewhere
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

# Impicit relative paths, from / 
This challenge requires you to use relative path and not absolute path.
## My solve
**Flag** `pwn.college{oBoaZR8pRu-YKYIhioP4NwN9_Tu.QX5QTN0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~implicit-relative-paths-from-:~$ 
```
2. Navigate to `/` directory using `cd`.
```bash
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ 
```
3. Use `challenge/run` command to get the flag.
```bash
challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{oBoaZR8pRu-YKYIhioP4NwN9_Tu.QX5QTN0wSM3gjNzEzW}
```
** My mistake** Using absolute path instead of relative path.
```Bash
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
```
## What i learned
I learned how to use the relative path correctly instead of absolute path to navigate around the directories.
## Reference
https://pwn.college/linux-luminarium/paths/ - Impicit relative paths, from / 
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

# Explict relative paths, from /
In this challenge you are in need to use explicit path using `.` and `..`.
## My solve
**Flag** `pwn.college{oavfoD1Sweax7QIln5BnGGa-56s.QXwUTN0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~explicit-relative-paths-from-:~$ 
```
2. Navigate to `/` directory using.
```bash
hacker@paths~explicit-relative-paths-from-:~$ cd /
```
3. Use `./challenge/run` to ge the flag.
```bash
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{oavfoD1Sweax7QIln5BnGGa-56s.QXwUTN0wSM3gjNzEzW}
```
## What i learned
I learned how to use `.` to navigate around directories. `.` refers to the same directory, multiple paths can be identical when `.` are used.
## References
https://pwn.college/linux-luminarium/paths/ - Explict relative paths, from /
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

# Implicit relative path
In this challenge we need to run the command from the `/challenge' directory.
## My solve
**Flag** `pwn.college{gRVB59g73v0Q43e0o8I8pioqt9-.QXxUTN0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~implicit-relative-path:~$ 
```
2. Navigate to `/challenge' directory.
```bash
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ 
```
3. Use `run` command to get the flag.
```bash
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{gRVB59g73v0Q43e0o8I8pioqt9-.QXxUTN0wSM3gjNzEzW}
```
## What i learned
There are different ways to navigate the directories and use the `run` command to get the flag value
## References
https://pwn.college/linux-luminarium/paths/ - Implicit relative path
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

# Home sweet home
This challenge needs you to write and read the the flag value from the hme directory.
## My solve
**Flag** `pwn.college{EI60GCbRYzVAkhT7KH2_WwDcyuq.QXzMDO0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@paths~home-sweet-home:~$
```
2. Use the `/challenge/run' command along with a argument following the constraints of the question
```bash
hacker@paths~home-sweet-home:~$ /challenge/run ~/~
Writing the file to /home/hacker/~!
... and reading it back to you:
pwn.college{EI60GCbRYzVAkhT7KH2_WwDcyuq.QXzMDO0wSM3gjNzEzW}
```
## What i learned
1. `cd` will use your home directory as the default destination.
2. You can write and read from the home directory itself.
3. You can provide a argument along with the `run` command to give the location for the `run` command to write and read from.
## References
https://pwn.college/linux-luminarium/paths/ - Home sweet home
https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC


