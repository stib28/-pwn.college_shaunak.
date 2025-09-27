# 1.MATCHING WITH *
change directory using globbing 

## MY SOLVE 
**FLAG:** `pwn.college{wbEcQ-x-W1sZvjsj1UZc9nM8PH_.QXxIDO0wSNxkjNzEzW}`
```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{wbEcQ-x-W1sZvjsj1UZc9nM8PH_.QXxIDO0wSNxkjNzEzW}
```
simply used `/ch*` to change directory and then ran the program.

## WHAT I LEARNED
when the shell encounters the `*` glob it replaces it with possible missing characters of files. The * matches any part of the filename except for / or a leading . character.

## REFERENCES 
none.


# 2.MATCHING WITH ?
change directory using  `?` globbing 

## MY SOLVE 
**FLAG:** `pwn.college{g9_ytM7rmAHEWTKXJWd1HOx8Zpp.QXyIDO0wSNxkjNzEzW}`
```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{g9_ytM7rmAHEWTKXJWd1HOx8Zpp.QXyIDO0wSNxkjNzEzW}
```
simply followed the given instructions and replaced letters c and l with `?` to change directory and then ran the program.

## WHAT I LEARNED
when the shell encounters the `?` glob it replaces it with possible one single missing character of files. SIngle character wildcard.

## REFERENCES 
none.


# 3.MATCHING WITH []
run a program using `[]` globbing 

## MY SOLVE 
**FLAG:** `pwn.college{ww2GolmFPy3Nsh0lVACZRW6U4hR.QXzIDO0wSNxkjNzEzW}`
```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{ww2GolmFPy3Nsh0lVACZRW6U4hR.QXzIDO0wSNxkjNzEzW}
```
simply followed the given instructions and used the [] globbing with the mentioned letters as an argument to bracket glob the files.

## WHAT I LEARNED
The square brackets are a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets.

## REFERENCES 
none.


# 4.MATCHING PATHS WITH []
glob bracket files using their path.

## MY SOLVE 
**FLAG:** `pwn.college{cjB2l0b6I1Xw0FUQ9lQqu5eRUgF.QX0IDO0wSNxkjNzEzW}`
```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[absh]
You got it! Here is your flag!
pwn.college{cjB2l0b6I1Xw0FUQ9lQqu5eRUgF.QX0IDO0wSNxkjNzEzW}
```
simply followed the given instructions and ran the program with the absolute paths of the files using bracket globbing.

## WHAT I LEARNED
Globbing happens on a path basis, so we can expand entire paths with our globbed arguments. 

## REFERENCES 
none.


# 5.MULTIPLE GLOBS
run program with argument of multiple globs.

## MY SOLVE 
**FLAG:** `pwn.college{0Zm8djX8LrtRgPxc0WniaDeIcDK.0lM3kjNxwSNxkjNzEzW}`
```
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{0Zm8djX8LrtRgPxc0WniaDeIcDK.0lM3kjNxwSNxkjNzEzW}
```
 followed the given instructions and to cover very word containing p, we'll use an asterisk before and after p, since * refers to anything or even nothing. 

## WHAT I LEARNED
Bash supports the expansion of multiple globs in a single word. The `*` refers to anything, even nothing.

## REFERENCES 
none.




