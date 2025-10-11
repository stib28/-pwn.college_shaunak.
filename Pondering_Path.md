# 1.THE PATH VARIABLE
use of PATH variable

## My solve
**Flag:** `pwn.college{QPYww1H58NRGqMZetu_zaQ-ddv7.QX2cDM1wSNxkjNzEzW}`

we clear the path variable by assigning it to null. with the path cleared, the challenge program will be unable to locate rm and fail to delete

```
hacker@path~the-path-variable:~$ export PATH=""
hacker@path~the-path-variable:~$ ls
bash: ls: No such file or directory
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{QPYww1H58NRGqMZetu_zaQ-ddv7.QX2cDM1wSNxkjNzEzW}
```

## What i learned
PATH is a shell variable that stores a bunch of directory paths in which the shell will search for the programs corresponding to commands

## REFERENCES
none.



# 2.SETTING PATH
setting new PATH

## My solve
**Flag:** `pwn.college{YGcsoHJk82UXVk8Yt666qh9PtgD.QX1cjM1wSNxkjNzEzW}`

we set the add a new path for '/challenge/more_commands/' and then get our flag

```
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{YGcsoHJk82UXVk8Yt666qh9PtgD.QX1cjM1wSNxkjNzEzW}
```

## What i learned
we can add or replace directories in the list of PATH

## REFERENCES
none.



# 3.FINDING COMMANDS
'which' command for flag

## My solve
**Flag:** `pwn.college{wdDLS0fjRlrBdLaQvCBQjfUzu3u.01NzEzNxwSNxkjNzEzW}`

we use the which command on win to get the location and cat our flag

```
hacker@path~finding-commands:~$ which win
/challenge/paths/5684/win
hacker@path~finding-commands:~$ /challenge/paths/5684/flag
bash: /challenge/paths/5684/flag: Permission denied
hacker@path~finding-commands:~$ cat /challenge/paths/5684/flag
pwn.college{wdDLS0fjRlrBdLaQvCBQjfUzu3u.01NzEzNxwSNxkjNzEzW}
```

## What i learned
which looks at each directory in $PATH in order and prints the first file it finds whose name matches the argument you passed.

## REFERENCES
none.


# 4.ADDING COMMANDS
custom commands

## My solve
**Flag:** `pwn.college{cfYN_9BuWn_HvbHadjc8G1xIrvV.QX2cjM1wSNxkjNzEzW}`

we set the win command to the PATH list and then get our flag 

```bash
hacker@path~adding-commands:~$ echo "cat /flag" > win
hacker@path~adding-commands:~$ chmod +x win
hacker@path~adding-commands:~$  export PATH="$(pwd):$PATH"
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{cfYN_9BuWn_HvbHadjc8G1xIrvV.QX2cjM1wSNxkjNzEzW}
```

## What i learned
we can add custom commands to the PATH list

# REFERENCES
none



# 5.HIJACKING COMMANDS
custom commands

## My solve
**Flag:** `pwn.college{8usxaMOLFK5TqlmK4qIshaG6a7W.QX3cjM1wSNxkjNzEzW}`

we set 'cat /flag' to rm and add it too the PATH list

```
hacker@path~hijacking-commands:~$ echo "cat /flag" > rm
hacker@path~hijacking-commands:~$ chmod +x rm
hacker@path~hijacking-commands:~$ export PATH="$(pwd):$PATH"
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/rm. Executing!
pwn.college{8usxaMOLFK5TqlmK4qIshaG6a7W.QX3cjM1wSNxkjNzEzW}
```

## What i learned
clever use of adding commands to PATH lists

## REFERENCES
used google for chmod command
