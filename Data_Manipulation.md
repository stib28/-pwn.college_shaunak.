# 1.TRANSLATING CHARACTERS
delete a character to obtain flag

## MY SOLVE 
**FLAG:** `pwn.college{43eMtdTbHmPQOyoQ-N-D8yR6jVf.01MxEzNxwSNxkjNzEzW}`
```
hacker@data~translating-characters:~$ /challenge/run 
Your case-swapped flag:
PWN.COLLEGE{43EmTDtBhMpqoYOq-n-d8Yr6JvF.01mXeZnXWsnXKJnZeZw}

hacker@data~translating-characters:~$ /challenge/run | tr 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz' 'abcdefghijklmnopqrstuvwxyzABCDEF
GHIJKLMNOPQRSTUVWXYZ'
yOUR CASE-SWAPPED FLAG:
pwn.college{43eMtdTbHmPQOyoQ-N-D8yR6jVf.01MxEzNxwSNxkjNzEzW}

hacker@data~translating-characters:~$ /challenge/run | tr 'A-Za-z' 'a-zA-Z'
yOUR CASE-SWAPPED FLAG:
pwn.college{43eMtdTbHmPQOyoQ-N-D8yR6jVf.01MxEzNxwSNxkjNzEzW}
```
ran the program to obtain the modified flag first. Clearly i needed to switch the cases of all the alphabets. So listed all the aplhabets from A-Z in caps first followed by the same in lowercase, and the same in argument two but in the opposite order so that it gets switched. Obviously, its difficult to list out all the letters in a case like this, so i used chatgpt to find if there was any shorter method, turns out i can abbreviate it as `a-z`, representing lowercase alphabets from a to z.

## WHAT I LEARNED 
the command `tr` which translates the characters given as argument 1 to the characters mentioned in argument two. It can also handle multiple characters, with the characters in different positions of the first argument replaced with associated characters in the second argument.

## REFERENCES 
none.


# 2. DELETING CHARACTERS 
delete a character to obtain flag

## MY SOLVE 
**FLAG:** `pwn.college{U_hVHFoy91GX9zXpg5iHZgi9k1u.0FNxEzNxwSNxkjNzEzW} `
```
hacker@data~deleting-characters:~$ /challenge/run
Your character-stuffed flag:
p^%w%n^.^%c^%o^%l^l^%eg^e%{%U^_^h%VH^%Foy^%91^GX%9^%z%Xpg^5iHZg%i^9^%k%1^%u^%.%0^%F^%Nx^%E^%z^%Nxw^%S%Nx%k^%jN^z^%E^z^%W}^%^%
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{U_hVHFoy91GX9zXpg5iHZgi9k1u.0FNxEzNxwSNxkjNzEzW}
hacker@data~deleting-characters:~$  
```
ran the program to obtain the modified flag first. Noticed `%^` being the unwanted characters. Used the command `tr -d %^` to get rid of the unwanted characters

## WHAT I LEARNED 
tr can also translate characters to nothing (i.e., delete them). This is done via a -d flag and an argument of what characters to delete.

## REFERENCES 
none.


# 3. DELETING NEWLINES 
delete line separators in flag.

## MY SOLVE 
**FLAG:** `pwn.college{EIxAhDYv95TlO0yujZG2hpOyESg.0VNxEzNxwSNxkjNzEzW}`
```
hacker@data~deleting-newlines:~$ /challenge/run
Your line-split flag: 
p
wn.
co
l
l
e
ge
{
EIxA
h
DY
v9
5
T
l
O
0
yuj
Z
G
2hpO
yE
S
g.0
V
Nx
E
z
N
xw
S
N
x
kj
Nz
E
z
W
}
hacker@data~deleting-newlines:~$ /challenge/run | tr -d "\n"
Your line-split flag: pwn.college{EIxAhDYv95TlO0yujZG2hpOyESg.0VNxEzNxwSNxkjNzEzW} 
```
ran the program to obtain the modified flag first. We are aware that `\n` is the line escape sequence. Therefore used the `tr` command like in the previous challenge to delete the new lines in the flag.

## WHAT I LEARNED 
tr can also translate characters to nothing (i.e., delete them). This is done via a -d flag and an argument of what characters to delete.

## REFERENCES 
none.


# 4.EXTRACTING THE FIRST LINES WITH HEAD
grab first few lines of a vast data and pipe it to a program for flag.

## MY SOLVE 
**FLAG:** `pwn.college{coFzBPrcHoM2hiQgjsCTAFBpI_n.0lNxEzNxwSNxkjNzEzW} `
```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7
SECRET-CODE-30539
SECRET-CODE-32357
SECRET-CODE-8494
SECRET-CODE-24331
SECRET-CODE-21101
SECRET-CODE-3297
SECRET-CODE-17732
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{coFzBPrcHoM2hiQgjsCTAFBpI_n.0lNxEzNxwSNxkjNzEzW}
```
simply ran the program and piped it to modify it and print the first 7 lines of the data using `head -n x ` command listing the first `x` lines. Got that, and then simply piped it to to the program mentioned.

## WHAT I LEARNED 
To grab just the early output of very verbose programs, we will use head! The head command is used to display the first few lines of its input. By default, it shows the first 10 lines, but we can control this with the -n option.

## REFERENCES 
none.


# 5.EXTRACTING SPECIFIC SECTIONS OF TEXT 
grab first few lines of a vast data and pipe it to a program for flag.

## MY SOLVE 
**FLAG:** `pwn.college{coFzBPrcHoM2hiQgjsCTAFBpI_n.0lNxEzNxwSNxkjNzEzW} `
```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7
SECRET-CODE-30539
SECRET-CODE-32357
SECRET-CODE-8494
SECRET-CODE-24331
SECRET-CODE-21101
SECRET-CODE-3297
SECRET-CODE-17732
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{coFzBPrcHoM2hiQgjsCTAFBpI_n.0lNxEzNxwSNxkjNzEzW}
```
simply ran the program and piped it to modify it and print the first 7 lines of the data using `head -n x ` command listing the first `x` lines. Got that, and then simply piped it to to the program mentioned.

## WHAT I LEARNED 
To grab just the early output of very verbose programs, we will use head! The head command is used to display the first few lines of its input. By default, it shows the first 10 lines, but we can control this with the -n option.

## REFERENCES 
none.


# 6. SORTING DATA 
grab first few lines of a vast data and pipe it to a program for flag.

## MY SOLVE 
**FLAG:** `pwn.college{coFzBPrcHoM2hiQgjsCTAFBpI_n.0lNxEzNxwSNxkjNzEzW} `
```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7
SECRET-CODE-30539
SECRET-CODE-32357
SECRET-CODE-8494
SECRET-CODE-24331
SECRET-CODE-21101
SECRET-CODE-3297
SECRET-CODE-17732
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{coFzBPrcHoM2hiQgjsCTAFBpI_n.0lNxEzNxwSNxkjNzEzW}
```
simply ran the program and piped it to modify it and print the first 7 lines of the data using `head -n x ` command listing the first `x` lines. Got that, and then simply piped it to to the program mentioned.

## WHAT I LEARNED 
To grab just the early output of very verbose programs, we will use head! The head command is used to display the first few lines of its input. By default, it shows the first 10 lines, but we can control this with the -n option.

## REFERENCES 
none.



