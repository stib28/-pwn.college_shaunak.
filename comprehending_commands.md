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


# 3.MORE CATTING PRACTICE
reading a file with its absolute path present in a random directory.

## MY SOLVE
**FLAG:** `pwn.college{srSvxZiDYDxAap8BUQgtgtoPFW0.QXwITO0wSNxkjNzEzW}`
```
hacker@commands~more-catting-practice:~$ cat /usr/lib/dbus-1.0/flag
pwn.college{srSvxZiDYDxAap8BUQgtgtoPFW0.QXwITO0wSNxkjNzEzW}
```
the absolute path of the flag was clearly mentioned. Simply plugged in the absolute path as argument to the `cat` command.

## WHAT I LEARNED 
using `cat` to read a file with its absolute path.

## REFERENCES 
none.


# 4.GREPPING FOR A NEEDLE IN A HAYSTACK
use grep command to search for the flag

## MY SOLVE 
**FLAG:** `pwn.college{00F8sgBvBxNmCz1b6dryVDRasDV.QX3EDO0wSNxkjNzEzW}`
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{00F8sgBvBxNmCz1b6dryVDRasDV.QX3EDO0wSNxkjNzEzW}

```
used the grep command with the mentioned text and path of the file as argument.

## WHAT I LEARNED 
sometimes, files are too big for cat command, so `grep` is used to search for the contents of the file. grep will search the file for lines of text containing the given string to search and print them to the console.

## REFERENCES 
none.


# 5.COMPARING FILES 
use `diff` command to find the difference between two files to obtain flag.

## MY SOLVE 
**FLAG:**  `pwn.college{ksQTH0hBhaHsIeN1j7BZjORFOKH.01MwMDOxwSNxkjNzEzW}`
```
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
4a5
> pwn.college{ksQTH0hBhaHsIeN1j7BZjORFOKH.01MwMDOxwSNxkjNzEzW}
```
used the `diff` command to compare the two given files line by line and find the difference to get the flag. First file contains 100 fake flags, second contains 100 fake and one real flag. Simply the different line is printed.

## WHAT I LEARNED 
finding similiarities by eye balling two files is hard and not feasible, the command `diff` is used to compare the files line by line. The command exactly tells us the difference and prints it. `XcX` tells us that theres a difference in the X line of first and second file. `XaY` tells us that after line X of first file, line Y was added in second file, the difference being the Y line.

## REFERENCES 
none.


