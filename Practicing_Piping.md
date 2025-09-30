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
**FLAG:** `pwn.college{QARWrgX7KgDQVK8u5ViaKrD3cdi.0FOxEzNxwSNxkjNzEzW}`
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


# 8. GREPPING ERRORS 
grep through errors directly to get obtain flag

## MY SOLVE 
**FLAG:** `pwn.college{cI8s5ONPl1OjHzMpyxgJUqgOK1S.QX1ATO0wSNxkjNzEzW}`
```
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep 'pwn.college'
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{cI8s5ONPl1OjHzMpyxgJUqgOK1S.QX1ATO0wSNxkjNzEzW}
```
used the `>&` to redirect the standard errors to the standard output to use the `|` operator, then used grep with keyword to find the flag.

## WHAT I LEARNED 
The | operator redirects only standard output to another program, and there is no 2| form of the operator, It can only redirect standard output. Then shell has a `>&` to redirect one file descriptor to another allowing us to use | operator for standard errors.

## REFERENCES 
none.


# 9.FILTERING WITH GREP -V
invert grep through a file's standard output to find flag.

## MY SOLVE 
**FLAG:** `pwn.college{QARWrgX7KgDQVK8u5ViaKrD3cdi.0FOxEzNxwSNxkjNzEzW}`
```
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{QARWrgX7KgDQVK8u5ViaKrD3cdi.0FOxEzNxwSNxkjNzEzW}
```
the instructions clearly ask us to use invert grep in the standard output of the program to find flag. Used `|` to grep without storing the standard output and then `grep -v ` to invert search.

## WHAT I LEARNED 
While normal grep shows lines that MATCH a pattern, grep -v shows lines that do NOT match a pattern.

## REFERENCES 
none.


# 10. DUPLICATING DATA WITH TEE
intercept the data to be piped with a command to obtain flag

## MY SOLVE
**FLAG:** `pwn.college{wXFcgmDw40Z4jsfcoCvxbZYJ8L8.QXxITO0wSNxkjNzEzW}`
```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee code | /challenge/college
Processing...
WARNING: you are overwriting file code with tee's output...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat code 
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "wXFcgmDw"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret wXFcgmDw | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{wXFcgmDw40Z4jsfcoCvxbZYJ8L8.QXxITO0wSNxkjNzEzW}
```
simpled followed the instructions and used the tee command in between the 2 programs to print the standard output to a random file, code in this case. Then used the secret code and transferred the standard output to the other program using pipe operator.

## WHAT I LEARNED 
The tee command duplicates data flowing through our pipes to any number of files provided on the command line. Used while debugging, to know the contents being transferred from one pipe to other files.

## REFERENCES 
none.


# 11.PROCESS SUBSTITUTION FOR INPUT 
use process substitution to differentaiate between the outputs of 2 commands and get flag

## MY SOLVE
**FLAG:** `wn.college{ct1Bbcs0vgrhxzGPiC3OW4eIGnP.0lNwMDOxwSNxkjNzEzW}`
```
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
98a99
> pwn.college{ct1Bbcs0vgrhxzGPiC3OW4eIGnP.0lNwMDOxwSNxkjNzEzW}
```
simpled followed the instructions and used the `diff` command to differentiate between the standard outputs of the 2 commands by converting them into temporary files by using process substitution. `<(command)` this converts the command into a temp file. 

## WHAT I LEARNED 
to compare the outputs of two commands, isntead of saving each to a file and then differentiating, we can use process substitution to convert each to a temp file and diff them directly.We can hook input and output of programs to arguments of commands. This is done using Process Substitution. For reading from a command we use `<(command)`. When we write <(command), bash will run the command and hook up its output to a temporary file that it will create. This isn't a real file, like a named pipe.

## REFERENCES 
none.


# 12.WRITING TO MULTIPLE PROGRAMS 
duplicate output of a command as input to two commands to obtain flag.

## MY SOLVE
**FLAG:** `pwn.college{ItsuY3XHyK4x9dxK3HPe6N1NXSa.QXwgDN1wSNxkjNzEzW}`
```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
303612265315286784
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{ItsuY3XHyK4x9dxK3HPe6N1NXSa.QXwgDN1wSNxkjNzEzW}
```
simpled followed the instructions and firstly used the `|` operator to transfer the output of the mentioned command. Im using tee because we are duplicating the output to the input of multiple files spontaneously. Now im using output process substitution to write to a command ( basicaly give input to a command ) using the `>(command)` command, and this prints the output of the command on the left of the pipe on the screen, along wit the output of the commands on the left.

## WHAT I LEARNED 
learned process substitution for output using `>(command)` for outputs. We can duplicate data to two files using the `tee` command. For qriting to a command, (giving input) we use process subs. for output, hook up its input to a temporary named file.

## REFERENCES 
none.


# 13. SPLIT-PIPING STDERR AND STDOUT
redirect the stdoutput and stderror of a program to two programs. 

## MY SOLVE
**FLAG:** `pwn.college{Qt1nowVUZYE-MX-cEXAyB4z9c5k.QXxQDM2wSNxkjNzEzW}`
```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{Qt1nowVUZYE-MX-cEXAyB4z9c5k.QXxQDM2wSNxkjNzEzW}
```
we are given a program and we are to redirect both of its standard errors and standard output to 2 different programs. used the first program as command and redirected the stderror using simple truncation, had to convert it to a temporary file as im also using `|` after it. Simply redirect the output to the other program using pipe.

## WHAT I LEARNED 
application of process substitutions and redirecting different data  to multiple files. 

## REFERENCES 
none.

# 14.NAMED PIPES
Create a fifo, redirect output to it and read it to get flag.

## MY SOLVE
**FLAG:** `pwn.college{0SXdsQ-zxGlSgIkbZ0nJ8vlUqJP.01MzMDOxwSNxkjNzEzW}`
```
hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo!
Bash will now try to open the FIFO for writing, to pass it as the stdout of
/challenge/run. Recall that operations on FIFOs will *block* until both the
read side and the write side is open, so /challenge/run will not actually be
launched until you start reading from the FIFO!

--terminal 2--

hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at 
/tmp/flag_fifo! Here is your flag:
pwn.college{0SXdsQ-zxGlSgIkbZ0nJ8vlUqJP.01MzMDOxwSNxkjNzEzW}
```
simply read the instructions and created a new fifo using `mkfifo` and then redirected output of the program to it and then read it using `cat`.

## WHAT I LEARNED 
persistent named pipes that stick around on the filesystem are called FIFOs, which stands for First (byte) In, First (byte) Out. These are named pipes. We can examine them like files and they persist until deleted unlike temp files. Any process can be written to them by path. FIFOs "block" any operations on them until both the read side of the pipe and the write side of the pipe are ready. Some key differences between fifos and files. FIFOs pass data directly between processes in memory - nothing is saved to disk, Once data is read from a FIFO, it's gone, automatic synchronization, order of write and read dont matter.

## REFERENCES 
none.










