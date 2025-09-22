# 1.THE ROOT 
invoke the pwn program using its absolute path to capture that flag.

## MY SOLVE
**FLAG:** `pwn.college{APfUNYX36qhzCfvfGfftMdQ01Kx.QX4cTO0wSNxkjNzEzW}`

invoked the absolute path using /pwn command.

## WHAT I LEARNED

The Linux filesystem is a "tree" with its root as `/`. The root of the filesystem is a directory, and every directory can contain other directories and files. We refer to files and directories by their path.Every piece of path is demarcated with `/`.This style of path, one that starts with the root directory, is referred to as an "absolute path".

## REFERENCES 
none.


# 2.PROGRAM and ABSOLUTE PATHS
invoke absolute path of a file in a directory.

## MY SOLVE
**FLAG:** `pwn.college{01rZnfV6PTq100M0MobCzYbMhac.QX1QTN0wSNxkjNzEzW}`

invoked the absolute path of the run file which was in `challenge` directory which waa inturn in `/`  using `/challenge/run` .

## WHAT I LEARNED

there can be multiple directories in directories all starting from the `root`. Learned to access a file in a directory using its absolute path.

## REFERENCES 
none.

# 3.POSITION THY SELF
execute a program from a specific path.

## MY SOLVE 
**FLAG:** `pwn.college{Akaz_M8ojaCLJM3BvIMhUy6fMmF.QX2QTN0wSNxkjNzEzW}`

changed directory to the `/sys/kernel` directory using the `cd` command and then ran `/challenge/run` program to obtain the flag.

## WHAT I LEARNED 

using the `cd` command to switch between directories and set as current directory. The `~` before the $ mentions the current directory we're in.

## REFERENCES 
none.


# 4.POSITION ELSEWHERE 
change to a different directory and run the program.

## MY SOLVE
**FLAG:** `pwn.college{cpUujFuMw0XP0umqP-dNr__kiSs.QX3QTN0wSNxkjNzEzW}`

changed directory to the `/usr/include` directory using the `cd` command and then ran the `/challenge/run` program to obtain the flag.

## WHAT I LEARNED 

using the `cd` command to navigate around directories and passing paths as argument to it.

##REFERENCES 
none.


# 5.POSITION YET ELSEWHERE 
change ot a different directory and run the program.

## MY SOLVE
**FLAG:** `pwn.college{g2MKVRimmmL_l5VFeRjtneeKEhx.QX4QTN0wSNxkjNzEzW}`
changed directory to the `/home` directory using `cd` and then ran `/challenge/run` program to obtain the flag.

## WHAT I LEARNED 

using the `cd` command to navigate around directories and passing paths as argument to it.

## REFERENCES 
none.

# 6.IMPLICIT RELATIVE PATHS,FROM /
using a relative path and running the program to obtain the flag.

## MY SOLVE
**FLAG:** `pwn.college{cha1A8oq5eZZjQts_MR9UIoD6rp.QX5QTN0wSNxkjNzEzW}`
changed directory to the root `/` directory using the `cd` command. Then ran the `challenge/run` program using its absolute path to obtain the flag.

## WHAT I LEARNED
The difference between absolute path and relative path. Relative paths do not start at the root, and interpreted relative to the current working directory which was not the case for asbolute paths.Therefore relative paths depend on the directory we're in at the time of writing command lines.

##REFERENCES 
none.

# 7.EXPLICIT RELATIVE PATHS,FROM /
using implicit entries for relative paths to obtain flag. run from `/challenge` directory.

##  MY SOLVE 
**FLAG:** `pwn.college{M0rRQd_bHAYA1TSWAhRnjSCg0_Z.QXwUTN0wSNxkjNzEzW}`
changed directory to `/` using `cd /`. Then used the relative path `./challenge/run` to obtain the flag.

## WHAT I LEARNED
The two implicit entries `.` and `..`. The entry `.` refers to the same directory and hence the following mean the same. naked path is a relative path that does not begin with ./ .
```
/challenge
/challenge/.
/challenge/./././././././././
/./././challenge/././
```

## REFERENCES 
none.

# 8.IMPLICIT RELATIVE PATH
run a program in the given directory with its naked path using implicit entries to obtain flag.

## MY SOLVE
**FLAG:** `pwn.college{kHxKovbHslXfOKOnVanKmZMWReR.QXxUTN0wSNxkjNzEzW}`
changed directory to `/challenge` using `cd /challenge`. Then used the relative path `./run` to obtsain the flag.

## WHAT I LEARNED 
Linux avoids automatically looking in the current directory when a "naked" path is provided, acts as a safety function. To tell linux that i want to explicitly run a program with naked path, implicit entries like `./` will be used.

## REFERENCES 
none.

# 9.HOME SWEET HOME
obtain the flag which gets copied to the file specified by us as an argument, with mentioned constraints.
```
Your argument must be an absolute path.
The path must be inside your home directory.
Before expansion, your argument must be three characters or less.
```

## MY SOLVE 
**FLAG:** `pwn.college{IPKyFQKQymrO-5RqXQzW8dWAMAg.QXzMDO0wSNxkjNzEzW}`

firstly checked contents of home directory by `ls /home` where the hacker directory was mentioned. According to the constraints the argument must be 3 charcters or less, hence the absolute path `/home/hacker` cannot be used. However `~` stands for the home directory,so we can use this. Input any letter and write `/challenge/run ~/f` to obtain the flag which gets copied to the file `f`. Here, /challenge/run is a command and ~/f being the argument.

## WHAT I LEARNED 
typically, shell session will start with  home directory as the current working directory.The ~ in the prompt is the current working directory, with ~ being shorthand for the home directory. Whenever ~ is provided as the start of an argument in a way consistent with a path, it will expand it to home directory. Expansion of ~ is an absolute path. `cd` will use home directory as the default destination.

## REFERENCES
none.
