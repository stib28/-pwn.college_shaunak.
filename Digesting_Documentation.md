# 1.LEARNING FROM DOCUMENTATION
pass a given argument to a program to obtain flag.

## MY SOLVE 
**flag:** `pwn.college{wyq7jd-ePeREGI5E1DAIQIGtVvS.QX0ITO0wSNxkjNzEzW}`
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{wyq7jd-ePeREGI5E1DAIQIGtVvS.QX0ITO0wSNxkjNzEzW}
```
simply used the argument `--giveflag` as mentioned in the documentation of the program `/challenge/challenge` to obtain the flag.

## WHAT I LEARNED 
The need for documentation of a program is figure out and write down how to use the prorgams, mentioning the arguments to be used in the command lines.

## REFERENCES 
none.


# 2.LEARNING COMPLEX USAGE 
provide argument to argument of a command to obtain the flag.

## MY SOLVE
**FLAG:** `pwn.college{4SLL7ANByTLXnzecWmFG_YSOBvc.QX1ITO0wSNxkjNzEzW}`
```
cker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{4SLL7ANByTLXnzecWmFG_YSOBvc.QX1ITO0wSNxkjNzEzW}.
```
We are aware that that the absolute path to the flag file is `/file`. As mentioned in the description of the program, we are supposed to provide the path as an argument to the argument `--printfile` which allows us to print arbitrary files to the terminal.

## WHAT I LEARNED 
Some complex commands take arguments to their arguments. The argument `--printfile`  allows us to print arbitrary files to the terminal.


# 3.READING MANUALS
Read the contents of the manual of a command to obtain flag

## MY SOLVE 
**flag:** `pwn.college{cx2OQTENWv62BzHGfRWw9V2SbMK.QX0EDO0wSNxkjNzEzW}`
```
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --cxvzfw 262
Correct usage! Your flag: pwn.college{cx2OQTENWv62BzHGfRWw9V2SbMK.QX0EDO0wSNxkjNzEzW}
```
used the `man` command to open the manual of the command `challenge`. In the manual, it was clearly mentioned the the program and argument to run to obtain the flag. argument was `--cxvzfw NUM`, prints the flag if NUM is 262.

## WHAT I LEARNED 
man is short for manual, and will display the manual of the command that is passed as an argument. We can scroll around the manpage with arrow keys and PgUp/PgDn. When done reading the manpage, we can hit q to quit. Manpages are stored in a centralized database, this database lives in the /usr/share/man directory. The arguments to the man command arent paths but the entries itself.

## REFERENCES 
none.


# 4.SEARCHING MANUALS
search for the correct argument in the manual to obtaian flag.

## MY SOLVE 
**FLAG:** `pwn.college{Uz99a26apJ1esI53gvvKEoQTMxs.QX1EDO0wSNxkjNzEzW}`
```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --eocri
Initializing...
Correct usage! Your flag: pwn.college{Uz99a26apJ1esI53gvvKEoQTMxs.QX1EDO0wSNxkjNzEzW}
```
opened the challenge manual using the `man` command. Then searched for the correct argument using `/flag` in the manual. Used `n` to switch to the next mention of `flag` keyword.

## WHAT I LEARNED 
we can search for particular keywords using `/keyword` and `n` to switch up, `N` to switch down, `q` to exit the manual, `?` to search backwards.

## REFERENCES 
none.


# 5.SEARCHING FOR MANUALS
search inside the `man` manual to get hints to obtain the flag.

## MY SOLVE 
**FLAG:** `pwn.college{I9FjEwNaxY0JDJsprAk5NAN1_Ui.QX2EDO0wSNxkjNzEzW}`
```
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
jwaxsprkiw (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man jwaxsprkiw
hacker@man~searching-for-manuals:~$ /challenge/challenge --jwaxsp 905
Correct usage! Your flag: pwn.college{I9FjEwNaxY0JDJsprAk5NAN1_Ui.QX2EDO0wSNxkjNzEzW}
```
firstly, used the `man man` commandline as instructed. Inside the manual, read the synopsis. Then searched using `/` for `keyword`. There it was mentioned i could use my keyword as argument to `man -k`. This searches for manual man pages with the name. Did that with the keyword being `challenge`(mentioned hidden `challenge` man page in the question). Received a command, used `man` for the command and then obtained simple instrcutions to get the flag like in the previous question.

## WHAT I LEARNED 
` man -k *keyword*` is the simplest way to search for hidden manuals with names. `man man` teaches the advanced use of the command itself.

## REFERENCES
none.


# 6.HELPFUL PROGRAMS
read a program's documentation which does not have a manual, with special command to get flag.

## MY SOLVE 
**FLAG:** `pwn.college{cl1FHiOI-P8VhQngTG3AEHcQUgS.QX3IDO0wSNxkjNzEzW}`
```
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 183
hacker@man~helpful-programs:~$ /challenge/challenge -g 183
Correct usage! Your flag: pwn.college{cl1FHiOI-P8VhQngTG3AEHcQUgS.QX3IDO0wSNxkjNzEzW}
```
The only program we have been dealing with is `/challenge/challenge`. So i used `--help` as argument to obtain documentation for the program. As clearly mentioned in the doc, used `-g` and `-p` to obtain the flag.

## WHAT I LEARNED 
A lot of programs will not have manuals but might tell how to run the program with special arguments like `--help`,`help`,`-h`,`-?`,`/?`.

## REFERENCES 
none.


# 7. HELP FOR BUILTINS
get information for shell builtins to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{8SJvEMYFnUXLJCAtkLwxBgc7GUw.QX0ETO0wSNxkjNzEzW}`
```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "8SJvEMYF".
hacker@man~help-for-builtins:~$ /challenge --secret 8SJvEMYF
hacker@man~help-for-builtins:~$ challenge --secret 8SJvEMYF
Correct! Here is your flag!
pwn.college{8SJvEMYFnUXLJCAtkLwxBgc7GUw.QX0ETO0wSNxkjNzEzW}
```
mentioned that the `challenge` command is now a shell builtin instead of a program. Therfore cannot invoke its documentation with `man` or `--help` therefore we use the command `help` to obtain information regarding the given builtin `challenge`. After that, simple instructions will give us the flag.

## WHAT I LEARNED 
Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs. Using `help` we get the list of all builtins in the shell.

## REFERENCES 
none.
