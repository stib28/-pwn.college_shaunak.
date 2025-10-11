# 1.LAUNCHING SCREEN
screen command

## My solve
**Flag:** `pwn.college{slPuNndzP9bnK-5mkFaM6baCxVB.0VN4IDOxwSNxkjNzEzW}`

we use the screen command and then type exit or press ctrl D to terminate the new screen

```
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{slPuNndzP9bnK-5mkFaM6baCxVB.0VN4IDOxwSNxkjNzEzW}
hacker@terminal-multiplexing~launching-screen:~$
```

## What i learned
screen command is used to open a new terminal inside a terminal.

## REFERENCES
none.



# 2.DETACHING AND ATTACHING
detach and attach screen

## My solve
**Flag:** `pwn.college{0rcWd11Yd1aEAr4SJccmZyr2-uS.0lN4IDOxwSNxkjNzEzW}`

we use ctrl A then press d to detach from a screen and then give the command 'screen -r' to reattach

```
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 147.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 147.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
Yes! Flag is: pwn.college{0rcWd11Yd1aEAr4SJccmZyr2-uS.0lN4IDOxwSNxkjNzEzW}
hacker@terminal-multiplexing~detaching-and-attaching:~$
```

## What i learned
we can use ctrl A then press d to detach from a screen and then give the command 'screen -r' to reattach. ctrl A is the acivation key for all shortscuts of the new screen

## REFERENCES
none



# 3.FINDING SESSIONS
screen name argument

## My solve
**Flag:** `pwn.college{MsVPY8gh4109bT6pjaQCnrela17.01N4IDOxwSNxkjNzEzW}`

we reattach to the screen which has the file by passing the name as an argument

```
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
        156.pts-0.terminal-multiplexing~launching-screen        (Remote or dead)
        144.session_dc3543c3875e13cd    (Detached)
        147.session_d570bf9bd2da4686    (Detached)
        150.session_b29dc538d9f2ef3b    (Detached)
4 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 147.session_d570bf9bd2da4686
Congratulations! You found the right session!
pwn.college{MsVPY8gh4109bT6pjaQCnrela17.01N4IDOxwSNxkjNzEzW}
```

## What i learned
we can reattch to a particular screen by passing its name as an argument to the 'screen -r' command

## REFERENCES 
none.


# 5.Detaching and Attaching (tmux)
tmux command

## My solve
**Flag:** `pwn.college{s5cFWnWbfkIpBM-JswWE1C5Mm4Y.0VO4IDOxwSNxkjNzEzW}`

we use the tmux command to start a new terminal and then detach and reattch from it

```bash
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux attach
Congratulations, here is your flag: pwn.college{s5cFWnWbfkIpBM-JswWE1C5Mm4Y.0VO4IDOxwSNxkjNzEzW}
```

## What i learned
tmux works the same as screen with the only difference that shortcuts in tmux start with ctrl B instead of ctrl A

# REFERENCES
none



# 6.Switching windows (tmux)
tmux shortcuts

## My solve
**Flag:** `pwn.college{0f4dlHTEJKoc6f0nSKjsxV4UyMV.0FM5IDOxwSNxkjNzEzW}`

we attach to tmux and then press 'ctrl B + 0' to go to window 0 and get our flag

```
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{oCCg8MNJtsajzwXZGSTUZx0FI8z.0FM5IDOxwCN1gjNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{0f4dlHTEJKoc6f0nSKjsxV4UyMV.0FM5IDOxwSNxkjNzEzW}
```

## WHAT I LEARNED
Ctrl-B c - Create a new window
Ctrl-B n - Next window
Ctrl-B p - Previous window
Ctrl-B 0 through Ctrl-B 9 - Jump to window 0-9
Ctrl-B w - See a nice window picker

## REFERENCES 
none.
