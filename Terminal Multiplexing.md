# Launching screen
This challenge requires to launch the screen and exit it.
## My solve
**Flag** `pwn.college{8WbcA_5M9-k-NCCS5knekPuWsIY.0VN4IDOxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@terminal-multiplexing~launching-screen:~$
```
2. Use the `screen` command and then exit. This will give you the flag.
```bash
hacker@terminal-multiplexing~launching-screen:~$ screen
                                        Screen version 5.0.1 (build on 2025-05-15 15:05:07) 
Copyright (c) 2025 Alexander Naumov
Copyright (c) 2018-2024 Alexander Naumov, Amadeusz Slawinski
Copyright (c) 2015-2017 Juergen Weigert, Alexander Naumov, Amadeusz Slawinski
Copyright (c) 2010-2014 Juergen Weigert, Sadrul Habib Chowdhury
Copyright (c) 2008-2009 Juergen Weigert, Michael Schroeder, Micah Cowan, Sadrul Habib Chowdhury
Copyright (c) 1993-2007 Juergen Weigert, Michael Schroeder
Copyright (c) 1987 Oliver Laumann

This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as
published by the Free Software Foundation; either version 3, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program (see the file COPYING); if not, see
https://www.gnu.org/licenses/, or contact Free Software Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02111-1301 
USA.

Send bugreports, fixes, enhancements, t-shirts, money, beer & pizza to screen-devel@gnu.org
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{8WbcA_5M9-k-NCCS5knekPuWsIY.0VN4IDOxwSM3gjNzEzW}
hacker@terminal-multiplexing~launching-screen:~$
```
## What i learned
1. How to launch the screen using the terminal and how to exit it.
## References
https://pwn.college/linux-luminarium/terminal-multiplexing/ - Launching screen

# Deattaching and Reattaching 
This challenge requires to deattach and reattach the flag.
## My solve
**Flag** `pwn.college{E1BJhoV_I0R7EVAaBaJQIhwahlI.0lN4IDOxwSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@terminal-multiplexing~detaching-and-attaching:~$
```
2. Use the screen command and then deattach the screen using crtl-A and then pressing d .
```bash
hacker@terminal-multiplexing~launching-screen:~$ screen
Screen version 5.0.1 (build on 2025-05-15 15:05:07) 
Copyright (c) 2025 Alexander Naumov
Copyright (c) 2018-2024 Alexander Naumov, Amadeusz Slawinski
Copyright (c) 2015-2017 Juergen Weigert, Alexander Naumov, Amadeusz Slawinski
Copyright (c) 2010-2014 Juergen Weigert, Sadrul Habib Chowdhury
Copyright (c) 2008-2009 Juergen Weigert, Michael Schroeder, Micah Cowan, Sadrul Habib Chowdhury
Copyright (c) 1993-2007 Juergen Weigert, Michael Schroeder
Copyright (c) 1987 Oliver Laumann

This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as
published by the Free Software Foundation; either version 3, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program (see the file COPYING); if not, see
https://www.gnu.org/licenses/, or contact Free Software Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02111-1301 
USA.

Send bugreports, fixes, enhancements, t-shirts, money, beer & pizza to screen-devel@gnu.org
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 163.pts-1.terminal-multiplexing~detaching-and-attaching]
```
3. Now run `/challenge/run` the reattach the screen.
```bash
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 163.pts-1.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{E1BJhoV_I0R7EVAaBaJQIhwahlI.0lN4IDOxwSM3gjNzEzW}
Yes! Flag is: pwn.college{E1BJhoV_I0R7EVAaBaJQIhwahlI.0lN4IDOxwSM3gjNzEzW}
hacker@terminal-multiplexing~detaching-and-attaching:~$
```
## What i learned
1. To deattach the screen we have to launch it and then use crtl-A followed by d.
2. To reattach we have to launch screen with `-r`.
## Refereneces
https://pwn.college/linux-luminarium/terminal-multiplexing/ - Deattaching and Reattaching 


