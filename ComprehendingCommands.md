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

# Listing files
In this challenge the user is taught to use the command `ls` which list out all the files in a directory.
## My Solve
**Flag** `pwn.college{UTklZb4I2hojbtwU-Y1B3j7gMer.QX4IDO0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~listing-files:~$
```
2. Run `ls` with `/challenge` as the argument.
```bash
hacker@commands~listing-files:~$ ls /challenge
14606-renamed-run-425  DESCRIPTION.md
```
3. Run `/challenge` with `14606-renamed-run-425` to get teh flag.
```bash
hacker@commands~listing-files:~$ /challenge/14606-renamed-run-425  
Yahaha, you found me! Here is your flag:
pwn.college{UTklZb4I2hojbtwU-Y1B3j7gMer.QX4IDO0wSM3gjNzEzW}
```
## What i learned
1. Syntax of ls `ls directory_name`
2. The `ls` commmand list all the files in the directory used as the argument.
## References
https://pwn.college/linux-luminarium/commands/ - Listing files

# Touching files
In this challenge you are supposed to use the `touch` command to create files.
## My Solve
**Flag** `pwn.college{AvMStOp0tDQQOgzuh6OkDeREUCN.QXwMDO0wSM3gjNzEzW}v'
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~touching-files:~$ 
```
2. Change the current directory to `/tmp`.
```bash
hacker@commands~touching-files:~$ cd /tmp
```
3. Create file `pwn` and `college` using `touch` command and run `/challenge/run` to get the flag.
```bash
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{AvMStOp0tDQQOgzuh6OkDeREUCN.QXwMDO0wSM3gjNzEzW}
```
## What i learned
1. The syntax of touch ` touch file_name`.
2. Touch is used to create a new file in the current directory.
## References
https://pwn.college/linux-luminarium/commands/ - Touching files.

# Removing files
In this challenge we have to use a command to remove a file.
## My solve
**Flag** `pwn.college{MCJGaywmOdSiwea9E_xXXmf68vb.QX2kDM1wSM3gjNzEzW}`
1. Connect to the dojo host using the ssh command
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~removing-files:~$ 
```
2. Delete the file `delete_me` using the command `rm` then run `/challenge/check` to get the flag.
```bash
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{MCJGaywmOdSiwea9E_xXXmf68vb.QX2kDM1wSM3gjNzEzW}
```
## What i learned
1. The syntax of rm `rm file_name`.
2. The command `rm` is used to remove a file from the directory.
## References
https://pwn.college/linux-luminarium/commands/ - Removing files

# Moving Files
This challenge requires you to move a file from one directory to another.
## My solve
**Flag** `pwn.college{YVL4vYr6i1d0WNfb5RR1CJ18ji8.0VOxEzNxwSM3gjNzEzW}`
1. Connect the dojo host using the ssh command
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~moving-files:~$
```
2. Move the `/flag` file into `/tmp/hack-the-planet` and run `/challenge/check` command.
```bash
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{YVL4vYr6i1d0WNfb5RR1CJ18ji8.0VOxEzNxwSM3gjNzEzW}
```
## What i learned
1. The syntax of mv ` mv file1 file2`.
2. The `mv` command is used to move a file from one directory to another.
## References
https://pwn.college/linux-luminarium/commands/ - Moving files

# Hidden files
This challenge teachs how linux hides few files and how to list them out.
## My solve
**Flag** `pwn.college{0M3osYriUptQb1fUSF9Miv5KfyK.QXwUDO0wSM3gjNzEzW}`
1. Connet to the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~hidden-files:~$
```
2. Make `/` directory the current directory and use `ls -a` to list out all the files.
```bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv          bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-171552479166  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
```
3. Read the `.flag-171552479166` using the `cat` command.
```bash
hacker@commands~hidden-files:/$ cat .flag-171552479166
pwn.college{0M3osYriUptQb1fUSF9Miv5KfyK.QXwUDO0wSM3gjNzEzW}
```
## What i learned
1. Linux hides the files that start with a `.`
2. To list out the files that start with a `.` we have to use `ls -a` command.
## References
https://pwn.college/linux-luminarium/commands/ - Hidden files

# An Epic Filesystem Quest
This challenge requires you to use your knowledge about `ls, cd, cat`.
## My solve
**Flag** `Q8yXKS4dYjGDrZfemoOLChyngGG.QX5IDO0wSM3gjNzEzW`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~an-epic-filesystem-quest:~$
```
2. Follow the clue's
```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -a
.   .dockerenv  bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
..  CLUE        boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~an-epic-filesystem-quest:/$ cat CLUE
Tubular find!
The next clue is in: /usr/share/maxima-sage/5.42.2/share/lbfgs

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/share/maxima-sage/5.42.2/share/lbfgs
hacker@commands~an-epic-filesystem-quest:/usr/share/maxima-sage/5.42.2/share/lbfgs$ ls
f2cl-lbfgs.lisp  lb2.lisp          lbfgs-ddot.lisp    lbfgs.lisp  maxima-lbfgs.lisp  mcstep.lisp      run-lbfgs.lisp
lb1.lisp         lbfgs-daxpy.lisp  lbfgs-lisp.system  lbfgs.mac   mcsrch.lisp        rtest_lbfgs.mac  sdrive.lisp
hacker@commands~an-epic-filesystem-quest:/usr/share/maxima-sage/5.42.2/share/lbfgs$ ls -a
.   .POINTER         lb1.lisp  lbfgs-daxpy.lisp  lbfgs-lisp.system  lbfgs.mac          mcsrch.lisp  rtest_lbfgs.mac  sdrive.lisp
..  f2cl-lbfgs.lisp  lb2.lisp  lbfgs-ddot.lisp   lbfgs.lisp         maxima-lbfgs.lisp  mcstep.lisp  run-lbfgs.lisp
hacker@commands~an-epic-filesystem-quest:/usr/share/maxima-sage/5.42.2/share/lbfgs$ cat .POINTER
Yahaha, you found me!
The next clue is in: /usr/lib/python3/dist-packages/sage/algebras/__pycache__

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/maxima-sage/5.42.2/share/lbfgs$ cd /usr/lib/python3/dist-packages/sage/algebras/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/algebras/__pycache__$ ls -a
.                                         commutative_dga.cpython-38.pyc                q_system.cpython-38.pyc
..                                        free_algebra.cpython-38.pyc                   quantum_matrix_coordinate_algebra.cpython-38.pyc
DOSSIER                                   free_algebra_element.cpython-38.pyc           quaternion_algebra.cpython-38.pyc
__init__.cpython-38.pyc                   free_algebra_quotient.cpython-38.pyc          quaternion_algebra_element.cpython-38.pyc
affine_nil_temperley_lieb.cpython-38.pyc  free_algebra_quotient_element.cpython-38.pyc  rational_cherednik_algebra.cpython-38.pyc
algebra.cpython-38.pyc                    free_zinbiel_algebra.cpython-38.pyc           schur_algebra.cpython-38.pyc
all.cpython-38.pyc                        group_algebra.cpython-38.pyc                  shuffle_algebra.cpython-38.pyc
askey_wilson.cpython-38.pyc               hall_algebra.cpython-38.pyc                   tensor_algebra.cpython-38.pyc
associated_graded.cpython-38.pyc          iwahori_hecke_algebra.cpython-38.pyc          weyl_algebra.cpython-38.pyc
catalog.cpython-38.pyc                    jordan_algebra.cpython-38.pyc                 yangian.cpython-38.pyc
cellular_basis.cpython-38.pyc             nil_coxeter_algebra.cpython-38.pyc            yokonuma_hecke_algebra.cpython-38.pyc
clifford_algebra.cpython-38.pyc           orlik_solomon.cpython-38.pyc
cluster_algebra.cpython-38.pyc            orlik_terao.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/algebras/__pycache__$ cat DOSSIER
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/include/config/dm

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/algebras/__pycache__$ cd /opt/linux/linux-5.4/include/config/dm
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/dm$ ls -a
.  ..  .REVELATION  mirror.h  zero.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/dm$ cat .REVELATION
Tubular find!
The next clue is in: /usr/share/javascript/mathjax/jax/output/SVG/fonts/STIX-Web/Latin/Bold
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/dm$ cd /usr/share/javascript/mathjax/jax/output/SVG/fonts/STIX-Web/Latin/Bold
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/SVG/fonts/STIX-Web/Latin/Bold$ ls -a
.  ..  Main.js  SECRET
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/SVG/fonts/STIX-Web/Latin/Bold$ cat SECRET
Lucky listing!
The next clue is in: /opt/pwndbg/.venv/lib/python3.8/site-packages/certifi-2025.8.3.dist-info/licenses

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/SVG/fonts/STIX-Web/Latin/Bold$ cd /opt/pwndbg/.venv/lib/python3.8/site-packages/certifi-2025.8.3.dist-info/licenses
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/certifi-2025.8.3.dist-info/licenses$ ls -a
.  ..  LICENSE  TEASER
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/certifi-2025.8.3.dist-info/licenses$ cat TEASER
Tubular find!
The next clue is in: /usr/share/racket/pkgs/web-server-lib/web-server/managers

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/certifi-2025.8.3.dist-info/licenses$ cd /usr/share/racket/pkgs/web-server-lib/web-server/managers
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/web-server-lib/web-server/managers$ ls -a
.  ..  .WHISPER  compiled  lru.rkt  manager.rkt  none.rkt  timeouts.rkt
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/web-server-lib/web-server/managers$ cat .WHISPER
Lucky listing!
The next clue is in: /usr/share/locale/vi/LC_MESSAGES

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
```
3. As the next one is trapped you have to use cat along with absolute path
```bash
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/web-server-lib/web-server/managers$ cat /usr/share/locale/vi/LC_MESSAGES/MESSAGE-TRAPPED
Tubular find!
The next clue is in: /usr/lib/ipxe/qemu
```
4. After using `cd` to go to the final clue and using `cat` to read the file we get the flag.
```bash
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/web-server-lib/web-server/managers$ cd /usr/lib/ipxe/qemu
hacker@commands~an-epic-filesystem-quest:/usr/lib/ipxe/qemu$ ls -a
.                             compat-256k-efi-pcnet.rom    efi-eepro100.rom  efi-vmxnet3.rom   pxe-ne2k_pci.rom
..                            compat-256k-efi-rtl8139.rom  efi-ne2k_pci.rom  pxe-e1000.rom     pxe-pcnet.rom
INSIGHT                       compat-256k-efi-virtio.rom   efi-pcnet.rom     pxe-e1000e.rom    pxe-rtl8139.rom
compat-256k-efi-e1000.rom     efi-e1000.rom                efi-rtl8139.rom   pxe-eepro100.rom  pxe-virtio.rom
compat-256k-efi-ne2k_pci.rom  efi-e1000e.rom               efi-virtio.rom    pxe-ne2k_isa.rom  pxe-vmxnet3.rom
hacker@commands~an-epic-filesystem-quest:/usr/lib/ipxe/qemu$ cat INSIGHT
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{Q8yXKS4dYjGDrZfemoOLChyngGG.QX5IDO0wSM3gjNzEzW}
```
## What i learned
1. How navigate around the command line.
2. How to read a file without making the directory of the file the current directory.
## References
https://pwn.college/linux-luminarium/commands/ - An Epic Filesystem Quest.

# Making directories
This challenge is about creating directories from the command line.
## My solve
**Flag** `pwn.college{swuvTc9H1rcZEkh-UAo0AcVhSS6.QXxMDO0wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~making-directories:~$
```
2. Use `mkdir` command along with the argument `/tmp/pwn` and 'cd' into the new directory.
```bash
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
```
3. Using `touch` create the file `college` and run `/challenge/run` to get the flag value.
```bash
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{swuvTc9H1rcZEkh-UAo0AcVhSS6.QXxMDO0wSM3gjNzEzW}
```
## What i learned
1. How to create new directories using `mkdir`.
2. The syntax of mkdir `mkdir directory_name`.
## References
https://pwn.college/linux-luminarium/commands/ - Making directories.

# Finding files
This challenge is about using the `find` command to search for files using the command line.
## My solve
**Flag** `pwn.college{Y8cB5JIvBXlWiDVwyAyNwdCeGrf.QXyMDO0wSM3gjNzEzW}`
1. Connect to the dojo host using ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~finding-files:~$ 
```
2. Use `find` command to search for the flag.
``` bash
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/sphinx/locale/el/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
```
3. Use `grep` command in each of the absolute paths searching for the argument `pwn.college`. (I found the flag in the second absolute path.)
```bash
hacker@commands~finding-files:~$ grep pwn.college /usr/share/sphinx/locale/el/flag
pwn.college{Y8cB5JIvBXlWiDVwyAyNwdCeGrf.QXyMDO0wSM3gjNzEzW}
```
## What i learned
1. How to use `find` to search for a file.
2. Syntax of flag i used `flag / -name absolute_path`.
## References
https://pwn.college/linux-luminarium/commands/ - Finding files

# Linking Files
This challenge required you to link two files in order to acquire the flag value
## My solve
**Flag** `pwn.college{4wCC4IVr4Nc1WxD1AoTUACX0IDa.QX5ETN1wSM3gjNzEzW}`
1. Connect the dojo host using the ssh command.
```bash
hunaid@Hunaids-MacBook-Pro ~ % ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~linking-files:~$
```
2. Use `ln -s` to link `/flag` and `/home/hacker/not-the-flag`
```bash
hacker@commands~linking-files:~$ ln -s /flag /home/hacke
r/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{4wCC4IVr4Nc1WxD1AoTUACX0IDa.QX5ETN1wSM3gjNzEzW}
```
## What i learned 
1. The command `ln -s` can be used hard link to files to read the same content from both the files.
2. Syntax `ln -s file_to_copy_from file_to_copy_to`.
## References
https://pwn.college/linux-luminarium/commands/ - Linking files

