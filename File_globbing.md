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


# 6.MIXING GLOBS 
pass an argument to match 3 files to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{Em18HhDxatoPoMu2FbNH3058Xu4.QX1IDO0wSNxkjNzEzW}`
```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{Em18HhDxatoPoMu2FbNH3058Xu4.QX1IDO0wSNxkjNzEzW}
```
changed to the given directory. Now for the globbing part, clearly the 3 files differ with multiple letters, so no scope of using the `?` glob. So, picked the letters the 3 files start from and used `[]` glob folllowed by `*` since they have basically no similiarities.

## WHAT I LEARNED
usage of mixing of different blobs to access certain files.

## REFERENCES 
none.


# 7. EXCLUSIONARY BLOBBING 
using exlusision blobs to obtain files and get flag.

## MY SOLVE 
**FLAG:** `pwn.college{wINOpltetBZuN-10IRNbK-TLfCL.QX2IDO0wSNxkjNzEzW}`
```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{wINOpltetBZuN-10IRNbK-TLfCL.QX2IDO0wSNxkjNzEzW}
```
simply followed the instructions and used the `^` exclusion blob to exclude files starting with p,w,n and display them by following it with `*` blob.

## WHAT I LEARNED
concept of exclusion blobs, `[*]` and `[^]` used to exclude files starting with a particular letter.

## REFERENCES 
none.


# 8.TAB COMPLETION
auto-completion using tab key

## MY SOLVE 
**FLAG:** `pwn.college{wp6toBL-tHhIe_pHFXJ1wFTrlUd.0FN0EzNxwSNxkjNzEzW}`
```
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ 
pwn.college{wp6toBL-tHhIe_pHFXJ1wFTrlUd.0FN0EzNxwSNxkjNzEzW}
```
simply used tab to auto complete the path of the file.

## WHAT I LEARNED
usage of the tab key to autocomplete.

## REFERENCES 
none.


# 9.MULTIPLE OPTIONS FOR TAB COMPLETION 
auto-completion using tab key when multiple options of files available

## MY SOLVE 
**FLAG:** `pwn.college{c9ixx1AMfWsWO1zNIpFSeEBlv5o.0lN0EzNxwSNxkjNzEzW}`
```
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwn
No flag in this file!
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter  
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking     
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwn-flag
cat: /challenge/files/pwn-flag: No such file or directory
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{c9ixx1AMfWsWO1zNIpFSeEBlv5o.0lN0EzNxwSNxkjNzEzW}
```
firstly used tab to auto-expand on p, which gave me ` /challenge/files/pwn`. No flag in this, so using tab again prints files because multiple options to proceed. I spot`pwncollege-flag` and use cat to read the file and flag is obtained. 

## WHAT I LEARNED
 On using tab in case of files with similiar names, By default bash will auto-expand until the first point when there are multiple options. When we hit tab a second time, it'll print out those options. Other shells and configurations, instead, will cycle through the options.

## REFERENCES 
none.


# 10.TAB COMPLETION ON COMMANDS 
use of tab to auto complete commands 

## MY SOLVE 
**FLAG:** `pwn.college{ofXjItNB76VfewTS6YDdoy3x1hv.0VN0EzNxwSNxkjNzEzW}`
```
hacker@globbing~tab-completion-on-commands:~$ pwncollege-2131 
Correct! Here is your flag:
pwn.college{ofXjItNB76VfewTS6YDdoy3x1hv.0VN0EzNxwSNxkjNzEzW}
```
simply used tab to auto complete the command according to the instructions.

## WHAT I LEARNED
usage of the tab key to autocomplete commands.

## REFERENCES 
none.








