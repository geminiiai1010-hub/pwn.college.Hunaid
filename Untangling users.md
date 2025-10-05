# Becoming root with su
This challenge requires you to become the root user and read the flag
## My solve
**Flag** `pwn.college{8vUUmF-nWy7oO70fBhUy7Ub2Q-F.QX1UDN1wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@users~becoming-root-with-su:~$
```
2. To become the root user type the command `su` and then the password is `hack-the-planet`.
```bash
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker#
```
3. The read the flag using the command `cat /flag`.
```bash
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{8vUUmF-nWy7oO70fBhUy7Ub2Q-F.QX1UDN1wSM3gjNzEzW}
```
## What i learned
1. To become the root user you have to use the command `su` and type the password in.
## References
https://pwn.college/linux-luminarium/users/ - Becoming root with su

# Other users with su
This challenge requires you to change the user to another user.
## My solve
**Flag** `pwn.college{0DSeMKGu4ceO913mEN_Oyfhyy9n.QX2UDN1wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
zardus@users~other-users-with-su:/home/hacker$
```
2. To switch to the other user type the command `su` and then type the user which is `zardus`. Following that type the password `dont-hack-me`.
```bash
hacker@users~other-users-with-su:~$ su zardus
Password:
```
3. To get the flag run the command `/challenge/run`.
```bash
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{0DSeMKGu4ceO913mEN_Oyfhyy9n.QX2UDN1wSM3gjNzEzW}
```
## What i learned
1. How to switch to other user using `su`.
2. Syntax `su username` then type the password in.
## References
https://pwn.college/linux-luminarium/users/ - Other users with su

