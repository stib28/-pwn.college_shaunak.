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
