# 1.CHAINING WITH SEMICOLONS
chaining commands using semi colon

## MY SOLVE
**FLAG:** `pwn.college{4FgV1dTcC60YYCUrW7cn_d07ibp.QX1UDO0wSNxkjNzEzW}`

```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{4FgV1dTcC60YYCUrW7cn_d07ibp.QX1UDO0wSNxkjNzEzW}
```
we use semicolon to chain the commands

## WHAT I LEARNED 
Basically, when we hit Enter, shell executes our typed command and, after that command terminates, gives us the prompt to input another command. The semicolon is analogous, just without the prompt and with us entering both commands before anything is executed

## REFERENCES
none.



## 2.BUILDING ON SUCCESS
chaining commands using &&

## My solve
**Flag:** `pwn.college{gwWR__4XqEpXRgnzBOea1HjDZPl.0lM0MDOxwSNxkjNzEzW}`

```
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{gwWR__4XqEpXRgnzBOea1HjDZPl.0lM0MDOxwSNxkjNzEzW}
```
we use '&&' to chain the commands

## What i learned
The && operator allows us to run a second command only if the first command succeeds (in Linux convention, this means it exited with code 0)

## REFERENCES 
none.



## 3.HANDING FAILURES
chaining commands using ||

## MY SOLVE 
**Flag:** `pwn.college{YZ0yWnR5C0HoctkAFyOP-MM64ig.01M0MDOxwSNxkjNzEzW}`

```
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{YZ0yWnR5C0HoctkAFyOP-MM64ig.01M0MDOxwSNxkjNzEzW}
```
we use '||' to chain the commands

## What i learned
the || operator allows you to run a second command only if the first command fails (exits with a non-zero code)

## REFERENCES 
none



# 4. YOUR FIRST SHEL SCRIPT
chaining commands into shel script

## My solve
**Flag:** `pwn.college{AQn8yLMFaKPZ_YCqT3wb2ABLuBV.QXxcDO0wSNxkjNzEzW}`

```
hacker@chaining~your-first-shell-script:~$ printf '/challenge/pwn\n/challenge/college\n' > x.sh
hacker@chaining~your-first-shell-script:~$ cat -n x.sh
     1  /challenge/pwn
     2  /challenge/college
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{AQn8yLMFaKPZ_YCqT3wb2ABLuBV.QXxcDO0wSNxkjNzEzW}
```
simply put the two programs in the shell script and ran it with bash.

## WHAT I LEARNED 
by convention, shell scripts are frequently named with a sh suffix. And then we can execute by passing it as an argument to a new instance of our shell (bash)! When a shell is invoked like this, rather than taking commands from the user, it reads commands from the file.

## REFERENCES 
none



## 5.REDIRECTING SCRIPT OUTPUT 
pipe commands into commands using shel script

## My solve
**Flag:** `pwn.college{sB1FykH14_6Iwx8goNmwhdXs2Rc.QX4ETO0wSNxkjNzEzW}`

```
hacker@chaining~redirecting-script-output:~$ { /challenge/pwn; /challenge/college; } | /challenge/solve; 
Correct! Here is your flag:
pwn.college{sB1FykH14_6Iwx8goNmwhdXs2Rc.QX4ETO0wSNxkjNzEzW}
```
we'll group the commands together and pipe their combined output directly to the solve command

## WHAT I LEARNED 
All of the various redirection methods work: > for stdout, 2> for stderr, < for stdin, >> and 2>> for append-mode redirection, >& for redirecting to other file descriptors, and | for piping to another command

## REFERENCES
none.



# 6.EXECUTABLE SHELL SCRIPTS
run script through path

## My solve
**Flag:** `pwn.college{ARnnMOsMkn2J006FBgDzuAmN59m.QX0cjM1wSNxkjNzEzW}`

we use The shebang, without it the system wont konw it should be run with bash. we give executable permission and run the script through its path

```
hacker@chaining~executable-shell-scripts:~$ echo '#!/bin/bash' > run_solve.sh
hacker@chaining~executable-shell-scripts:~$ echo '/challenge/solve' >> run_solve.sh
hacker@chaining~executable-shell-scripts:~$ chmod +x run_solve.sh
hacker@chaining~executable-shell-scripts:~$ ./run_solve.sh
Congratulations on your shell script execution! Your flag:
pwn.college{ARnnMOsMkn2J006FBgDzuAmN59m.QX0cjM1wSNxkjNzEzW}
```

## What i learned
we can directly call script file using its path if its executable

## REFERENCES
google



# 7.UNDERSTANDING SHEBANGS
through path

## My solve
**Flag:** `pwn.college{c2ONvuvidxpUjc9TIVkaNRKaNFZ.0VOzMDOxwSNxkjNzEzW}`

we use shebhang as the first line to let the shell know its a bash file 

```
hacker@chaining~understanding-shebangs:~$ echo '#!/bin/bash' > /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ echo "echo 'hack the planet'" >> /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{c2ONvuvidxpUjc9TIVkaNRKaNFZ.0VOzMDOxwSNxkjNzEzW}
```

## What i learned
There are a bunch of different types of programs, but if the program file starts with the characters #! (often termed a "shebang"), Linux treats the file as an interpreted program, and the contents of the rest of the line as the path to the interpreter. It then invokes the interpreter with the path to the program file as its only argument.

## REFERENCES 
none.



# 8.SCRIPTING WITH ARGUMENTS
arguments to scripts

## My solve
**Flag:** `pwn.college{slcwDug2fzzXf13vtjXh0EUJGNt.0VNzMDOxwSNxkjNzEzW}`

we accesss the arguments and reverse it

```bash
hacker@chaining~scripting-with-arguments:~$ echo '#!/bin/bash' > /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ echo 'echo "$2 $1"' > /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ bash ~/solve.sh pwn college
college pwn
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{slcwDug2fzzXf13vtjXh0EUJGNt.0VNzMDOxwSNxkjNzEzW}
```

## What i learned
scripts can also work with arguments. we can access arguments throught their position as $(postion)

## REFERENCES 
none.



# 9.SCRIPTING WITH CONDITIONALS
script conditions

## My solve
**Flag:** `pwn.college{QGZXCpH28WhiC-zoeYdobo-zRkm.0lNzMDOxwSNxkjNzEzW}`
```
hacker@chaining~scripting-with-conditionals:~$ echo '#!/bin/bash' > /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo 'if [ "$1" == "pwn" ]' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo 'then' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo '    echo "college"' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo 'fi' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ bash ~/solve.sh pwn
college
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag: pwn.college{QGZXCpH28WhiC-zoeYdobo-zRkm.0lNzMDOxwSNxkjNzEzW}
```
we use if to check for pwn and print college if condition is met

## What i learned
we can use if statements but they have to have proper syntax and proper spacing. the if command ends with fi

## REFERENCES 
none.



# 10.SCRIPTING WITH DEFAULT CASE 
write script correctly and run

## My solve
**Flag:** `pwn.college{QgCCrW4REn-LtI8nC-2qCRWj5CS.01NzMDOxwSNxkjNzEzW}`

use if and else

```bash
hacker@chaining~scripting-with-default-cases:~$ echo '#!/bin/bash' > /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ echo 'if [ "$1" == "pwn" ]' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ echo 'then' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ echo '    echo "college"' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ echo 'else' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ echo '    echo "nope"' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ echo 'fi' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ bash ~/solve.sh pwn
college
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{QgCCrW4REn-LtI8nC-2qCRWj5CS.01NzMDOxwSNxkjNzEzW}
```

## What i learned
we can use else condition to be the default condition if any other condition do not meet

## REFERENCES 
none



# 11.SCRIPTING WITH MULTIPLE CONDITIONS
using elif statements for script 

## My solve
**Flag:** `pwn.college{43Gke3VcjuXpjCB6hivHFOAe2Wk.0FOzMDOxwSNxkjNzEzW}`

```
hacker@chaining~scripting-with-multiple-conditions:~$ echo '#!/bin/bash' > /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'if [ "$1" == "hack" ]' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'then' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo '    echo "the planet"' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'elif [ "$1" == "pwn" ]' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'then' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo '    echo "college"' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'elif [ "$1" == "learn" ]' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'then' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo '    echo "linux"' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'else' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo '    echo "unknown"' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'fi' >> /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ bash ~/solve.sh pwn
college
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{43Gke3VcjuXpjCB6hivHFOAe2Wk.0FOzMDOxwSNxkjNzEzW}
```
used if else as per instructions to get flag.

## What i learned
we can use elif condition to check for other arguments which can be provided

## REFERENCES
none



# 12.READING SHELL SCRIPTS
reading scripts

## MY SOLVE
**Flag:** `pwn.college{kBR_QXN4Q3f-IY_ehYfzMhecwZT.0lMwgDOxwSNxkjNzEzW}`


```
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
CORRECT! Your flag:
pwn.college{kBR_QXN4Q3f-IY_ehYfzMhecwZT.0lMwgDOxwSNxkjNzEzW}
```
we cat the script and read what is the password argument need to get the flag

## WHAT I LEARNED
we learned to cat scripts and get information needed

## REFERENCES
none








