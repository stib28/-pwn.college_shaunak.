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


# 4.REDIRECTING ERRORS 
redirect errors to a file and get flag.

## MY SOLVE 
**FLAG:** `pwn.college{QXcUHogPX4SGlOk7VER2HoELdgh.QX3YTN0wSNxkjNzEzW}`
```
hacker@piping~redirecting-errors:~$ /challenge/run 1> myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{QXcUHogPX4SGlOk7VER2HoELdgh.QX3YTN0wSNxkjNzEzW}

hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
```
the instructions clearly ask us to run the program and redirect the output and errors to 2 files. Did this using FD numbers, 1> for stdoutput and 2> for stderrors.

## WHAT I LEARNED 
A File Descriptor (FD) is a number that describes a communication channel in Linux. 0 for stdinput, 1 for stdoutput, 2 for stderrors. a `>` without a number implies `1>`. Furthermore, we can redirect multiple file descriptors at the same time.

## REFERENCES 
none.


# 5.REDIRECTING INPUT 
redirect a file to a program( input redirection) to get flag

## MY SOLVE 
**FLAG:** `pwn.college{ovqF_i6-_43m5v4X27ZRmdJlyzI.QXwcTN0wSNxkjNzEzW}`
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ cat PWN
COLLEGE
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{ovqF_i6-_43m5v4X27ZRmdJlyzI.QXwcTN0wSNxkjNzEzW}
```
the instructions clearly ask us to return a standard input file to the program, and the file must read a word. Used `echo` to redirect output word to the file and then redirected the file as input to the program using `<`.

## WHAT I LEARNED 
we can redirect input to programs! This is done using `<`.

## REFERENCES 
none.


# 6.GREPPING STORED RESULTS 
redirect the output of a program to a file and grep to find the flag.

## MY SOLVE 
**FLAG:** `pwn.college{MA8UIf8dtkokhCaFyanqoDQVKcO.QX4EDO0wSNxkjNzEzW}`
```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep 'pwn.college' /tmp/data.txt
pwn.college{MA8UIf8dtkokhCaFyanqoDQVKcO.QX4EDO0wSNxkjNzEzW}
```
the instructions clearly ask us to redirect the output of the program to a file, do that using `>`. Now to read and find the flag in the content, i used grep with the keyword of `pwn.college` since all flags start with that.

## WHAT I LEARNED 
 we can grep the redirected output to a file to read it.

## REFERENCES 
none.


# 7. GREPPING LIVE OUTPUT
find out the flag from a program output without redirecting its contents to a file.

## MY SOLVE 
**FLAG:** `pwn.college{owDaxuG9kXLqj-CXG3FNDtDuDG4.QX5EDO0wSNxkjNzEzW}`
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep 'pwn.college'
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{owDaxuG9kXLqj-CXG3FNDtDuDG4.QX5EDO0wSNxkjNzEzW}
```
the instructions clearly ask us to find the flag without redirecting the output of the program to a file, did this using the `|` operator. Grepped for the keyword `pwn.college` as flags begin with that.

## WHAT I LEARNED 
It turns out that we can "cut out the middleman" and avoid the need to store results to a file to read it. We can do this using the pipe `|` operator. . Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe. Left gives output, right gives input.

## REFERENCES 
none.


# 8.



