# 1.PRINTING VARIABLES 
print a variable to the shell to get flag.

## MY SOLVE 
**FLAG:** `pwn.college{crwvA9tQ_I_QbKNJUfkFTkv62qB.QX3UTN0wSNxkjNzEzW}`
```
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{crwvA9tQ_I_QbKNJUfkFTkv62qB.QX3UTN0wSNxkjNzEzW}
```
simply read the instructions and print the variable by using echo command and inserting a `$` before the variable name, where `$` just marks the current working directory.

## WHAT I LEARNED 
printing a variable using `echo` command.

## REFERENCES 
none.


# 2.SETTING VARIABLES
set value to a  variable to get flag.

## MY SOLVE 
**FLAG:** `pwn.college{suM8oMXqnI0i04sY-iDw4Id27mY.QX5UTN0wSNxkjNzEzW}`
```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{suM8oMXqnI0i04sY-iDw4Id27mY.QX5UTN0wSNxkjNzEzW}
```
simply read the instructions and set the variable using `VARIABLE=NAME`, no gaps.

## WHAT I LEARNED 
setting a value to a variable.

## REFERENCES 
none.


# 3.MULTI WORD VARIABLES 
set a multi word variable to get flag.

## MY SOLVE 
**FLAG:** `pwn.college{Mtag5VOWuVNEjpvs0IJio1jIxAD.QXwYTN0wSNxkjNzEzW}`
```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Mtag5VOWuVNEjpvs0IJio1jIxAD.QXwYTN0wSNxkjNzEzW}
```
simply read the instructions and set the multi word variable using quotes `VARIABLE="NAME"`, no gaps.

## WHAT I LEARNED 
setting a  multi word value to a variable, quotes must be used.

## REFERENCES 
none.


# 4.EXPORTING VARIABLES
export a variable to obtain flag

## MY SOLVE 
**FLAG:** `pwn.college{MjYUcKbFDPM8SNcnKM71uQ-YK5q.QXyYTN0wSNxkjNzEzW}`
```
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{MjYUcKbFDPM8SNcnKM71uQ-YK5q.QXyYTN0wSNxkjNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
simply read the instructions and set 2 values to 2 variables, exported one variable. export using `export` command.

## WHAT I LEARNED 
exporting a variable. By default, variables that are set in a shell session are local to that shell process. Other commands wont inherit them. `sh` is a  a minimal shell implementation that is invoked as a child of the main shell process. When we export variables, they are passed into the environment variables of child processes.

## REFERENCES 
none.


# 5.PRINTING EXPORTED VARIABLES
using `env` command to print all the exported variables to get flag.

## MY SOLVE 
**FLAG:** `pwn.college{guUa6nRD0v-81ajer51uwuzbMvT.QX4UTN0wSNxkjNzEzW}`
```
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=ec3cd5c2ca8c0a20e164b656f4f00f2a6169e5ca505da7533ecce250de7deb49
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{guUa6nRD0v-81ajer51uwuzbMvT.QX4UTN0wSNxkjNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```
simply printed all the exported variables in the shell using the `env` command. 

## WHAT I LEARNED 
`env` prints all the exported variables in the shell along with their values.

## REFERENCES 
none.


# 6.STORING COMMAND OUTPUT 
store the output of a command directly into the variable and read it for the flag.

## MY SOLVE 
**FLAG:** `pwn.college{gE6mga6BrOlEv0mkMSMZNQ2rlZk.QX1cDN1wSNxkjNzEzW}`
```
hacker@variables~storing-command-output:~$ PWN=$( /challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{gE6mga6BrOlEv0mkMSMZNQ2rlZk.QX1cDN1wSNxkjNzEzW}
```
simply read the output of the command directly into the variable using `$()`, and then used echo to print the variable to get flag.

## WHAT I LEARNED 
storing the output of a command directly into the variable using `$()`. `VARIABLE=$(COMMAND)`.

## REFERENCES 
none.


# 7.READING INPUT
Set the value of variable by taking input from the user 

## MY SOLVE 
**FLAG:** `pwn.college{k3U-rD8lSeuVp9FkMI5brCt7pv8.QX4cTN0wSNxkjNzEzW}`
```
hacker@variables~reading-input:~$ echo $PWN

hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{k3U-rD8lSeuVp9FkMI5brCt7pv8.QX4cTN0wSNxkjNzEzW}
```
firstly checked the value of the variable. Clearly, the ouput was nothing. So, i used `read` command to input the value given by the user(me) to the variable. This set the variable.

## WHAT I LEARNED 
setting the variable using input from the user.

## REFERENCES 
none.


# 8.READING FILES
read a file into a variable directly to obtain flag

## MY SOLVE 
**FLAG:** `pwn.college{k2YO-u5ijNOb8pJXCePnu0uPO6X.QXwIDO0wSNxkjNzEzW}`
```
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{k2YO-u5ijNOb8pJXCePnu0uPO6X.QXwIDO0wSNxkjNzEzW}
```
simply followed the instructions and redirected the content of the file as input to `read PWN`, so when it reads PWN variable, it reads the file.

## WHAT I LEARNED 
reading a file directly into a variable without using cat, without having to use `echo VARIABLE=$(cat file)`.

## REFERENCES
none.






