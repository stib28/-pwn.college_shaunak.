# 1.Listing Processes
find the flag in the process list

## MY SOLVE 
**FLAG:** `pwn.college{UeNnsddP41uBzsMHVU-e_3DriSc.QX4MDO0wSNxkjNzEzW}`
```
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 14:36 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 14:36 ?        00:00:00 /run/dojo/bin/sleep 6h
root         132       1  0 14:36 ?        00:00:00 /challenge/19140-run-8042
root         135     132  0 14:36 ?        00:00:00 sleep 6h
hacker       146       1  0 14:36 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.
hacker       150     146  0 14:36 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       160     150  0 14:36 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:~$ ps -aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.1  0.0   1056   640 ?        Ss   14:36   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/do
root           7  0.0  0.0 231708  2560 ?        S    14:36   0:00 /run/dojo/bin/sleep 6h
root         132  0.0  0.0   4132  2560 ?        S    14:36   0:00 /challenge/19140-run-8042
root         135  0.0  0.0   2744  1600 ?        S    14:36   0:00 sleep 6h
hacker       146  0.0  0.0  37072 21760 ?        Sl   14:36   0:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --i
hacker       150  0.0  0.0 231940  4160 pts/0    Ss   14:36   0:00 /run/dojo/bin/bash --login
hacker       161  0.0  0.0 233600  3840 pts/0    R+   14:37   0:00 ps -aux
hacker@processes~listing-processes:~$ /challenge/19140-run-8042
Yahaha, you found me! Here is your flag:
pwn.college{UeNnsddP41uBzsMHVU-e_3DriSc.QX4MDO0wSNxkjNzEzW}
Now I will sleep for a while (so that you could find me with 'ps').
```
simply used the `ps` command folllowed by the `ef` argument to find out the program which has the file, namely challenge file.

## WHAT I LEARNED 
we can list running processes using the ps command. By default it just lists all the processes running in the terminal. We can use arguments to modify and get better outputs.

## REFERENCES 
none.



# 2.KILLING PROCESSES
kill a program to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{Qz9irEnNvkGain7rcnS5-opj5gN.QXyQDO0wSNxkjNzEzW}`
```
hacker@processes~killing-processes:~$ ps -aux | grep dont_run
hacker       136  0.0  0.0 231576  3520 ?        Ss   15:09   0:00 /challenge/dont_run
hacker       181  0.0  0.0 230696  2560 pts/0    S+   15:10   0:00 grep --color=auto dont_run
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{Qz9irEnNvkGain7rcnS5-opj5gN.QXyQDO0wSNxkjNzEzW}
hacker@processes~killing-processes:~$ 
```
simply used the `ps` command folllowed by the `aux` argument ( to show PIDs ) and used grep to find PID of dont run program. Then killed the program using `kill` and ran `/challenge/run  ` to get flag.

## WHAT I LEARNED 
we can terminate processes using the `kill` command.

## REFERENCES 
none.



# 3.INTERRUPTING PROCESSES
interrupt a process to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{AbqshEXRewMNbB0JnqhwVf7chTD.QXzQDO0wSNxkjNzEzW}`
```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{AbqshEXRewMNbB0JnqhwVf7chTD.QXzQDO0wSNxkjNzEzW}
```
ran the program and used ctrl - c as instructed.

## WHAT I LEARNED 
we can terminate the process that is clogging our terminal using this command.

## REFERENCES 
none.



# 4.KILLING MISBEHAVING PROCESSES.
kill the misbehaving process and obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{4pFbatNIar0q5FiX66DjM5BpHIM.0FNzMDOxwSNxkjNzEzW}`
```
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{4pFbatNIar0q5FiX66DjM5BpHIM.0FNzMDOxwSNxkjNzEzW}
```
used `ps -aux` to get all the processes. Found the decoy misbehaving process and killed it. Ran `/challenge/run` which also sent decoys along with actual flag.. Ran it again to obtain flag.

## WHAT I LEARNED 
THe decoys are present because the process was terminated when the flags already reached the pipe. Therefore the conten tmust flow outside the flag.

## REFERENCES 
none.



# 5.SUSPENDING PROCESSES
suspend a process to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{05RLeIE-YUu1WPO2RYKieDpKGUZ.QX1QDO0wSNxkjNzEzW}`
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         162     151  0 17:07 pts/1    00:00:00 bash /challenge/run
root         164     162  0 17:07 pts/1    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         162     151  0 17:07 pts/1    00:00:00 bash /challenge/run
root         169     151  0 17:08 pts/1    00:00:00 bash /challenge/run
root         171     169  0 17:08 pts/1    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{05RLeIE-YUu1WPO2RYKieDpKGUZ.QX1QDO0wSNxkjNzEzW}
```
simply ran run first, suspended it to the background to make a copy of it, ran run again.

## WHAT I LEARNED 
wecan suspend processes to the background with Ctrl-Z.

## REFERENCES 
none.



# 6.RESUMING PROCESSES
suspend and resume a process to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{Q4HHck08A3AGj2ELsKxKtt9DI3d.QX2QDO0wSNxkjNzEzW}`
```
hhacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg /challenge/run
/challenge/run
I'm back! Here's your flag:
pwn.college{Q4HHck08A3AGj2ELsKxKtt9DI3d.QX2QDO0wSNxkjNzEzW}
Don't forget to press Enter to quit me!

Goodbye!
hacker@processes~resuming-processes:~$ 
```
simply ran run first, suspended it to the background then resumed it using `fg` command followed by argument of process.

## WHAT I LEARNED 
we can resume suspended processes with `fg` command.

## REFERENCES 
none.



# 6.BACKGROUNDING PROCESSES
run a process in the background to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{QEr4mNLmX3kvB6DgCQYGjgEDazM.QX3QDO0wSNxkjNzEzW}`
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         161 S+   bash /challenge/run
root         163 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                
hacker@processes~backgrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ /challenge/run


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         161 S    bash /challenge/run
root         171 S    sleep 6h
root         172 S+   bash /challenge/run
root         174 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{QEr4mNLmX3kvB6DgCQYGjgEDazM.QX3QDO0wSNxkjNzEzW}
```
simply ran run first, suspended it to the background then resumed it in the background using `bg` command followed by argument of process.

## WHAT I LEARNED 
we can resume suspended processes in the background with `bg` command.

## REFERENCES 
none.


# 7.FOREGROUNDING PROCESSES
foreground a background process

## MY SOLVE 
**FLAG:** `pwn.college{cgm1cGrTySqGMnWEbndg0QxbrLT.QX4QDO0wSNxkjNzEzW}`
```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.

hacker@processes~foregrounding-processes:~$ fg /challenge/run
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{cgm1cGrTySqGMnWEbndg0QxbrLT.QX4QDO0wSNxkjNzEzW}
hacker@processes~foregrounding-processes:~$ 
```
simply ran run first, suspended it to the background then resumed it in the foreground using `fg` command followed by argument of process.

## WHAT I LEARNED 
we can resume suspended processes in the foreground with `fg` command.

## REFERENCES 
none.



# 8.STARTING BACKGROUNDED PROCESSES
background a process without suspending

## MY SOLVE 
**FLAG:** `pwn.college{4EfqQUcY3FSzhkZnAK_U1MWjXiZ.QX5QDO0wSNxkjNzEzW}`
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 159
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{4EfqQUcY3FSzhkZnAK_U1MWjXiZ.QX5QDO0wSNxkjNzEzW}
```
simply shifted the program to the background using `&` after the process

## WHAT I LEARNED 
use `&` to background a process without suspending it.

## REFERENCES 
none.



# 9. PROCESS EXIT CODES 
get exit code to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{cFyghkeKuEWo9myE916jBcP_n0e.QX5YDO1wSNxkjNzEzW}`

```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
206
hacker@processes~process-exit-codes:~$ /challenge/submit-code
You must run /challenge/submit-code with the exit code you retrieved from 
/challenge/get-code as the first argument:

Usage: /challenge/submit-code [EXIT_CODE]
hacker@processes~process-exit-codes:~$ /challenge/submit-code 206
CORRECT! Here is your flag:
pwn.college{cFyghkeKuEWo9myE916jBcP_n0e.QX5YDO1wSNxkjNzEzW}
```
ran the mentioned program first, then printed the exit code using `echo $?` then used it with the process to get flag.

## WHAT I LEARNED 
commands that succeed typically return 0 and commands that fail typically return a non-zero value, most commonly 1 but sometimes an error code that identifies a specific failure mode. Exit code given by `$?`

## REFERENCES 
none.




