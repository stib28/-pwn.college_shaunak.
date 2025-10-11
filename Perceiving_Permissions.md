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



# 3.FUN WITH GROUP NAMES 

## MY SOLVE 
**FLAG :** `pwn.college{UVA0FcOWBmKs0y9tEozPB7jPOBl.QXycjM1wSNxkjNzEzW}`
```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp4115) groups=1000(grp4115)
hacker@permissions~fun-with-groups-names:~$ chgrp grp4115 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{UVA0FcOWBmKs0y9tEozPB7jPOBl.QXycjM1wSNxkjNzEzW}
```
simply used id and  the `chgrp` command to change the group of the file to mentioned name and read the flag.

## WHAT I LEARNED
we can use id to find group names.

## REFERENCES 
none.



# 4.CHANGING PERMISSIONS
 use chmod command to change permsission

## My solve
**Flag:** `pwn.college{krwG7hOuRmBqkOS_ub_wsxW348B.QXzcjM1wSNxkjNzEzW}`
```
hacker@permissions~changing-permissions:~$ chmod a+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{krwG7hOuRmBqkOS_ub_wsxW348B.QXzcjM1wSNxkjNzEzW}
```
we use the change mode command with argument 'a+r /flag' which says allow flag file read to everyone

## WHAT I LEARNED 
first character there is the file type. next three characters are user persmission. next three characters are the grp persmissions. next three characters are all other access permissions. (example: drwxr-xr-x)
r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
'-' nothing 
chmod (chamege mode) command is used to change persmission 
chmod [OPTIONS] MODE FILE
WHO+/-WHAT convention

## REFERENCES 
none.



# 5. EXECUTABLE FILES
execute using the chmod command

## My solve
**Flag:** `pwn.college{c7QKLW10i00BNiQ0eI59AyHRPFa.QXyEjN0wSNxkjNzEzW}`
```
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{c7QKLW10i00BNiQ0eI59AyHRPFa.QXyEjN0wSNxkjNzEzW}```

## What i learned
first character there is the file type. next three characters are user persmission. next three characters are the grp persmissions. next three characters are all other access permissions. (example: drwxr-xr-x)
r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
'-' nothing 
chmod (chamege mode) command is used to change persmission 
chmod [OPTIONS] MODE FILE
WHO+/-WHAT convention
```
we use the change mode command with argument 'a+x /challenge/run' which says allow the file to be executed by everyone

## WHAT I LEARNED 

first character there is the file type. next three characters are user persmission. next three characters are the grp persmissions. next three characters are all other access permissions. (example: drwxr-xr-x)
r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
'-' nothing 
chmod (chamege mode) command is used to change persmission 
chmod [OPTIONS] MODE FILE
WHO+/-WHAT convention

# REFERENCES 
none.

# 6.PERMISSION TWEAKING PRACTICE 
 use the chmod command multiple times

## MY SOLVE 
**FLAG:** `pwn.college{s57NoxqYx98rI5rQeB0WbDVFMYt.QXwEjN0wCN1gjNzEzW}`

we use the change mode command with suitable arguments to pass the challenge

```
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w----r--
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ug-r /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": -w----r--
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w-------
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-r /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": -w-------
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w--wx-wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod go+wx /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": -w--wx-wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -w-rwxrwx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod go+r /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": -w-rwxrwx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -w-rwx-wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-r /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": -w-rwx-wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -----x-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ug-rw /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": -----x-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -------wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-x /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": -------wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ------rwx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o+r /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod a+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{s57NoxqYx98rI5rQeB0WbDVFMYt.QXwEjN0wCN1gjNzEzW}
```

## WWHAT I LEARNED 
first character there is the file type. next three characters are user persmission. next three characters are the grp persmissions. next three characters are all other access permissions. (example: drwxr-xr-x)
r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
'-' nothing 
chmod (chamege mode) command is used to change persmission 
chmod [OPTIONS] MODE FILE
WHO+/-WHAT convention

# REFERENCES 
none.


# 8.THE SUID BIT 
set SUID permission

## MY SOLVE 
**FLAG:** `pwn.college{0UCyISIZQxlTI-G9nAhloIfirYE.QXzEjN0wSNxkjNzEzW}`

```
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root! 
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{0UCyISIZQxlTI-G9nAhloIfirYE.QXzEjN0wSNxkjNzEzW}
```
By adding the SUID bit using chmod u+s, we are telling the system: Anyone who runs this program should temporarily become the file's owner (root) while the program is running. When we execute it, you get a shell that is running with root privileges, allowing you to access and read any file on the system, including the flag.

## WHAT I LEARNED 
The SUID (Set User ID) bit is a special file permission in Linux. When an executable file with the SUID bit set is run, the process will execute with the permissions of the file owner, not the user who ran it.

## REFERENCES
none





