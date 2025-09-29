# 1.REDIRECTING OUTPUT 
redirect output to a file to get flag.

## MY SOLVE 
**FLAG:** `pwn.college{MFZoxqLB6PlSeai2FqLHNQGcsX0.QX0YTN0wSNxkjNzEzW}`
```
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{MFZoxqLB6PlSeai2FqLHNQGcsX0.QX0YTN0wSNxkjNzEzW}
```
simply used `echo PWN` to output `PWN` and then used `>` (standard output) to redirect it to the file

## WHAT I LEARNED 
`>` used to redirect standard outputs to files.

## REFERENCES 
none.


# 2.REDIRECTING MORE OUTPUT 
redirect output from any command to a file to get flag.

## MY SOLVE 
**FLAG:** `pwn.college{8o0m6EedQjRu8WevvojnKaLMzDB.QX1YTN0wSNxkjNzEzW}`
```
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{8o0m6EedQjRu8WevvojnKaLMzDB.QX1YTN0wSNxkjNzEzW}
```
simply used the program mentioned and redirected its standard output to the file to get flag.

## WHAT I LEARNED 
`>` used to redirect standard outputs from any command to files. /challenge/run still prints to the terminal, despite redirecting stdout. That's because it communicates its instructions and feedback over standard error, and only prints the flag over standard out!

## REFERENCES 
none.


# 3.APPENDING OUTPUT 
redirect output using append mode

## MY SOLVE 
**FLAG:** `pwn.college{Q99EXYil7DNUmYbjMega_Z80b78.QX3ATO0wSNxkjNzEzW}`
```
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 |
\|/ This is the first half:
 v
pwn.college{Q99EXYil7DNUmYbjMega_Z80b78.QX3ATO0wSNxkjNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!
```
the instructions clearly ask us to use append mode redirect to redirect output ( 2nd part of the flag) to the file mentioned.

## WHAT I LEARNED 
 `>` creates a new output file every time, deleting the old contents.Instead we can redirect output in append mode using >> instead of >, which wont delete but instead add the contents to the end of the file.

## REFERENCES 
none.
