# 1. BECOMING ROOT WITH SU
become root user and read flag 

## MY SOLVE 
**FLAG:** `pwn.college{MOPpuMV39fGtd14svzfYnkPg5eZ.QX1UDN1wSNxkjNzEzW} `
```
hacker@users~becoming-root-with-su:~$ su
Password: 
su: Authentication failure
hacker@users~becoming-root-with-su:~$ 
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{MOPpuMV39fGtd14svzfYnkPg5eZ.QX1UDN1wSNxkjNzEzW}
```
enter the root user using `su` and enter password. Simply cat the file to get flag.

## WHAT I LEARNED 
su defaults to launching a shell as a specified user, learned how to become ROOOT.

## REFERENCES 
none.



# 2.OTHER USERS WITH SU
switch to other user and get flag.

## MY SOLVE 
**FLAG:** `pwn.college{UylbcUkVgOgNOGL90uHW4PCuPKZ.QX2UDN1wSNxkjNzEzW} `
```
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{UylbcUkVgOgNOGL90uHW4PCuPKZ.QX2UDN1wSNxkjNzEzW}
```
enter the given user using `su` and the gievn user as argument and enter password. Simply cat the file to get flag.

## WHAT I LEARNED 
learned to login with a different user 

## REFERENCES 
none.



# 3.CRACKING PASSWORDS
switch to other user and get flag.

## MY SOLVE 
**FLAG:** `pwn.college{0kVBu86UEuPAXVTP0XvVd7bUDbA.QX3UDN1wSNxkjNzEzW}`
```
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:21 100% 2/3 0.04587g/s 267.1p/s 267.1c/s 267.1C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{0kVBu86UEuPAXVTP0XvVd7bUDbA.QX3UDN1wSNxkjNzEzW}
```
Used JOhn The Ripper to crack the password simply provide the mentioned process as argument to John. We obtain the real password and i use `su` to loginn to zardus and obtain flag.

## WHAT I LEARNED 
John the Ripper cracked Zardus' leaked password hash to find the real password.

## REFERENCES 
none.



# 4.USING SUDO
use sudo to get flag

## MY SOLVE 
**FLAG:** `pwn.college{IPfBtZcOoNI6VAz4DOT6lVb_R1g.QX4UDN1wSNxkjNzEzW}`
```
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{IPfBtZcOoNI6VAz4DOT6lVb_R1g.QX4UDN1wSNxkjNzEzW}
```
simply used the sudo command followed by the argument to read the flag to read it as root user.

## WHAT I LEARNED 
sudo defaults to running a command as the root user. sudo checks policies to determine whether the user is authorized to run commands as root

## REFERENCES 
none.



