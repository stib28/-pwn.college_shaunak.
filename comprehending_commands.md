# 1.Cat:not the pet, but command!
read a file present in the home directory with cat command to obtain flag.

## MY SOLVE
**FLAG:** `pwn.college{gpZTsezPTBbI2D6Uifej_hCxj9o.QXxcTN0wSNxkjNzEzW}`

clearly mentioned flag has been copied to the flag file. So open the the flag file using `cat flag`(present in home directory so need for path).
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{gpZTsezPTBbI2D6Uifej_hCxj9o.QXxcTN0wSNxkjNzEzW}
```

## WHAT I LEARNED 
the use of `cat` command is for reading out files. Cat will concatenate multiple files if provided multiple arguments. `cat file1 file2 ` reads both the contents of file1 and file2.

## REFERENCES 
none.


# 2.Catting absolute paths
reading a file that is not present in the home directory.

## MY SOLVE
**flag:** `pwn.college{k3bhKPKxUMhVEMfuYWS5qavkAG3.QX5ETO0wSNxkjNzEzW}`
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{k3bhKPKxUMhVEMfuYWS5qavkAG3.QX5ETO0wSNxkjNzEzW}
```
since its not in the main directory, to read the the file we can use its absolute path with the command `cat /flag`.

## WHAT I LEARNED 
using `cat` command to read a file not present in the main directory.

## REFERENCES 
none.

