# 1.CHANGING FILE OWNERSHIP
change the file ownership of a file

## MY SOLVE 
**FLAG :** `pwn.college{0QaiNGTLFongSZm6Bhx-94aRbV6.QXxEjN0wSNxkjNzEzW}`
```
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{0QaiNGTLFongSZm6Bhx-94aRbV6.QXxEjN0wSNxkjNzEzW}
hacker@permissions~changing-file-ownership:~$ ls -l /flag
-r-------- 1 hacker root 60 Oct 10 19:23 /flag
```
simply used the `chown` command to change the owner of the flag file to hacker user,and read it.

## WHAT I LEARNED
`ls -l` is used to view the permissions of a file. `chown` to change owner. `chown [username] [file]`

## REFERENCES 
none.



# 2. GROUPS AND FILES 

## MY SOLVE 
**FLAG :** `pwn.college{0hfVRady3775sMNws2lYbHLCfJy.QXxcjM1wSNxkjNzEzW}`
```
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{0hfVRady3775sMNws2lYbHLCfJy.QXxcjM1wSNxkjNzEzW}
```
simply used the `chgrp` command to change the group of the file to hacker, because hacker has the permission to read the flag file.

## WHAT I LEARNED
`chgrp` is used to change group of a file. Files have both an owning user and group. A group can have multiple users in it, and a user can be a member of multiple groups. Being in a group is basically access to that file.

## REFERENCES 
none.



