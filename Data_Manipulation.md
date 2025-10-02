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
extract information on specific columnns of a vast data using commands.

## MY SOLVE 
**FLAG:** `pwn.college{YstsAIYUydADDGb4psrZZ2kOb87.01NxEzNxwSNxkjNzEzW} `
```
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run
29900 p
14938 w
31881 n
13802 .
6645 c
15475 o
25265 l
30608 l
16135 e
27086 g
32095 e
6579 {
24961 Y
6150 s
29013 t
7792 s
1234 A
9672 I
31864 Y
14603 U
15012 y
3585 d
4028 A
13686 D
2976 D
18196 G
6504 b
11308 4
1262 p
24024 s
18632 r
19267 Z
20808 Z
25602 2
27534 k
28024 O
30535 b
25291 8
10027 7
4673 .
5490 0
9634 1
27931 N
2546 x
8345 E
14863 z
12361 N
6998 x
26975 w
23680 S
24184 N
11914 x
3561 k
16776 j
25951 N
32392 z
13668 E
29724 z
25361 W
32062 }
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{YstsAIYUydADDGb4psrZZ2kOb87.01NxEzNxwSNxkjNzEzW}
```
firstly, ran the program to print the altered flag. What we can see is, there are random numbers in column 1 and letters of our flag in column 2. So used thr `cut` command, used `-d` which is column specifier, then `" " ` which states the separation between column 1 and column 2, `-f` states the column we need. Then put it all together by deleting the new line like in the previous challenge.

## WHAT I LEARNED 
Sometimes, we want to grab specific columns of data, we used cut command. The -d argument specifies the column delimiter (how columns are separated). The -f argument specifies the field number (which column to extract).

## REFERENCES 
none.


# 6. SORTING DATA 
sort the data obtained in an order to obtsain flag.

## MY SOLVE 
**FLAG:** `pwn.college{MlQ0BxK2BXcZyJMK9P2WoxaEJzO.0FM0MDOxwSNxkjNzEzW} `
```
hacker@data~sorting-data:~$ sort -r /challenge/flags.txt
pwn.college{MlQ0BxK2BXcZyJMK9P2WoxaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.college{MlQ0BxK2BXcZyJMK9P2WoxaEJzO.0FM0MDOxwSNxkjNzEyW}
pwn.college{MlQ0BxK2BXcZyJMK9P2WoxaEJzO.0FM0MDOxwSNxkiNzEzW}
pwn.college{MlQ0BxK2BXcZyJMK9P2WoxaEJzO.0FM0MDOxwRNxkjNzEzW}
pwn.college{MlQ0BxK2BXcZyJMK9P2WoxaEJzO.0FL0MDOxwSNxkjNzEzW}
pwn.college{MlQ0BxK2BXcZyJMK9P2WowaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.college{MlQ0BxK2BXcZyJMK9O2WoxaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.college{MlQ0BxK2BXcZyJMK8P2WoxaEJzO.0FM0LDNwwSNxkjNzEzV}
pwn.college{MlQ0BxK2BXcZyJMJ9P2WoxaEJzO.0FL0MDOxwSNxkjNzEzW}
pwn.college{MlQ0BxK2BXcZyIMK9P2WoxaEJzO.0FM0MCOxwRMxkiNzEzW}
pwn.college{MlQ0BxK2BXcYxJMK9P2WoxaEIzO.0FM0MDOxvSNxkjNzEzW}
pwn.college{MlQ0BxK1BXcZyJMK9P2WoxaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.college{MlQ0BxJ2BXcZyJMK9P2WoxaEIzO.0FL0MDOwwSNxkjNzEyW}
pwn.college{MlQ0BwK2BXcZyJLK9P1WoxaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.college{MlQ0BwK2BWbZyJMK9P2WoxaEJzO.0EM0MCOwwSNxjjNyEzV}
pwn.college{MlQ0AxK2BXcZyJMK9O2WoxaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.college{MkQ0BxJ2BXcYyJMK9P2VoxaEJzO.0FM0MDNxwSNwkiMyEzW}
pwn.college{MkQ0AxK2BWcYyJMK9P2VoxaDJyO.0FL0MCOxwRMxkjMzEzV}
pwn.college{MkQ0AwK2AXcZxJMJ9P2WoxaDJzO.0EM0LCOwwRNxkjNzEyV}
pwn.college{LlQ0BxK1BXcZyJMK9P2WoxaEJzO.0FM0MDOxwRNxkjNzEzW}
pwn.college{LlQ0BxJ2AXcYxIMK9P1WoxaDJyO.0FM0MCOxwSNwjjMzDzW}
pwn.college{LlQ0AxK2BXbYyJMK9P2WnxaEJyO.0FL0MDOxwSNxkjMzDzW}
pwn.collegd{MlQ0BxK2BXcZyJMK9P2WnxaDJzO.0FM0MDOxwSNxkjNzEyV}
pwn.collegd{MlQ0BxK2BXcZyJLJ9P2WoxaEJzO.0EM0MDOxwSMxkjMzEzW}
pwn.collegd{MkQ0BxK1BXbZxJMK9P2WoxaEJzO.0FM0MDOxvSNxjjNzDzW}
pwn.colldgd{MlQ0BxK1BXcZyJMK9P2VoxaEIyO.0FM0MDOxwSNxkiMzDzW}
pwn.colkege{MlQ0BxK2BXcZyJMK9P2VoxaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.colkege{MlQ0BxK2AXcZyJMK9P2WoxaEJzO.0FM0MDOxvSMxkjNzEzW}
pwn.colkege{MlQ0BxK2AXcZyJMK9P2WnxaEJyN.0FM0MDOxwRMwkjNzDzW}
pwn.colkege{MlQ0BwK2BXcZyJMK9P2WoxaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.colkege{MlQ0BwK2AWcZyJMK9P2WoxaEJzO.0FM0MDNxvRNxkjMzEyW}
pwn.colkege{MkP0BxJ2BXcYyJMK9O2WoxaEIzN.0FL0LCOxwRNwkjNzEzV}
pwn.coklege{MlQ0BxK2BXcZyJMK9P2WoxaEJzO.0FM0MDOxwSNxkjNzEzW}
pwn.coklege{MlQ0BxK2BXcZyJMK9P2WoxaEJzO.0EM0MDOxwRNxkjNzEzW}
pwn.coklefe{LlQ0BwJ2AXcZyIMK8P2VowaEJzO.0FM0MDOxwSNwkjMyEzW}
pwn.coklefe{LlP0BxK1BXcZyJLK8P2VowaDIyO.0EM0LDOxvRMxkiMzDyW}
pwn.cokkege{LlQ0BxK2AWcYyIMJ9O2WoxaDJzO.0EM0MDOxwSMxjjNzEzW}
pwn.cokkdge{MlQ0AxK2AXcYyJMK8P2WnxaEJyO.0EM0LCOxvSMwkjMzDzW}
pwn.cnllege{MlQ0BwK2BWbYyIMK9O2VowaDJyO.0EM0MCOxwSNxkiMyEzV}
pwn.cnllege{MlP0BxJ2BXcZyIMK9P1WoxaEJzN.0FM0MCNxvSNwkjNzDyW}
pwn.cnlldge{LlQ0BxK2BXbZyIMK9P2VowaEJyN.0FM0LDOwwSMxkjNyEzW}
pwn.cnlkegd{MlQ0BxK2AXbZyILK9P2VoxaEIzO.0FL0MCOxwSMxkjMzDzW}
pwn.cnlkefd{LlQ0AxK2BXcYyJMJ9P2VoxaDJyO.0EM0LCNxwRNxjiNzEzW}
pwn.bollege{MlQ0BxK2BXcZyJMK9O2WoxaEJzO.0FM0MDOxwRNxkjNzEzV}
pwn.bollegd{MkQ0AxK2BWcZyIMJ9O1WoxaEJzO.0FM0MDOxwRNwkiMzEzW}
pwn.bollefd{MlQ0BxK1BXbYxJLK8P1WnxaEJzN.0FM0MDOxvSMxjjNzEzW}
pwn.bolldgd{MkQ0AxK2BWcZyJLK9O1VoxaEJzO.0FM0LDOwwSNxjjNzEzW}
pwn.bolkege{LlP0BxK1BWcZyJMK9P2WoxaEJzN.0FM0MDOxwSNwkjNyEyW}
pwn.bolkegd{MlP0AxK2AXcYyJMK9P2WoxaDJyO.0FL0MDNwwRNxkiNzEyW}
pwn.boklefe{LkP0BxK1BWcZyIMJ9O2VoxaDJzO.0FL0MDOxwSNxjiNyEzW}
pwn.boklefd{LlP0AwK1AXcZxJMK9P1WoxaEJzO.0EM0LCNxvSNxkjMzDyW}
pwn.bokkefe{MlQ0BxJ2AWcZyJLJ9P2VowaEJzN.0EL0LDOxwSNxkjNzEzW}
pwn.bnllege{MlP0BwK1BXcZyJMK9O2VowaDIyN.0EM0MDNxvSNxjjNzEzW}
pwn.bnklegd{LlQ0BxJ2BXbYyJMK9O2WoxaEJzO.0FL0MCNwwSNxkjNyDzW}
pwm.college{MlQ0BxK2BXbZxJMK9O2WoxaEJzO.0FM0MDNxwSNwkjNzDzW}
pwm.college{MlQ0BxK1BXcZxIMK9P2WnxaEIzO.0FM0MDOxwRNxkjNzEzW}
pwm.collefe{MlQ0BxK2AXcZyJMK9P1WoxaEIzO.0FM0MDOxvSNxkjNzEzW}
pwm.colldge{LlQ0BxK2BXbZyJMK9P2WnwaEJzO.0FM0MDNxwSNxjjNzEzV}
pwm.colldgd{MlP0BxK1BXbZxJMK9P2WoxaEJzO.0FM0MDNxwRMxkjNzEzW}
pwm.colkdge{MlP0AxK2BXbZxJMK8O2WnxaDJyO.0FL0LDOwwSNxkiMzEyW}
pwm.cokkefe{MlQ0BxK2BWcYyJMK9O2VoxaEJzO.0FM0MDOxwSNxkiNzEzV}
pwm.cokkdge{MlQ0AxK2AXcZyJMK9P1WowaEJzN.0FM0LCNwwSNxkiNzDzV}
pwm.cnllege{MkQ0AxK2BXcZyJMK8P2WnxaEJzO.0FM0MCOxwSMwkjNzEzW}
pwm.cnlldge{MlP0BwJ2BWcZxJLK9O2WoxaDIzO.0FL0MDOxwSNxjjNyEzW}
pwm.bollege{LlQ0BxK2AWcZyIMK8P2WoxaDJzO.0FM0LDOxvSNwkjNzDyW}
pwm.boklefe{LkQ0BxK2BWcZyJMK9P1VoxaEJzO.0FL0MDNxwRMxkjNzDyW}
pwm.bnlldge{MlQ0BxK2BXcZyJMK9P2WoxaEIzO.0FM0MCOxvSMxkjNzEzW}
pvn.college{MlQ0BxK2BXcZyJLK9P2WoxaEJyO.0FM0MDNxvRNxkjNzDyW}
pvn.college{MlQ0BxK2BXcZyJLK9P2WowaDJzO.0FL0MDOwwRNxkjNzEyW}
pvn.college{MlQ0BxK2BXbYxJLK8P2WowaDJzO.0FL0MCOxvSNxkjNyEzW}
pvn.collegd{LkQ0BxK2AXcZyJMK9P2WoxaEIyO.0EM0MDOwwSNwkiNzEzV}
pvn.collefe{MlQ0BxK2BWcZxJLK9P1VoxaDJzO.0FM0MDOxwSMxkiNyDyW}
pvn.collefe{MkQ0BxK2AXcZyILJ9P2WoxaEIzO.0FM0MDNxvSNwkjNyEzV}
pvn.colldgd{MlQ0AxK2AXcZyJMK9P1WoxaDJzO.0EM0MDOxwSNxkjNyEzW}
pvn.colkefe{MkP0BwJ2BXcZxJMJ9O2VowaDJzO.0FM0MDOwwRNwkiMyEyW}
pvn.coklege{MlQ0BxJ2BXcZxJMJ8P2VoxaEJzO.0EM0LDOxwSMxkjMzDzV}
pvn.bollege{MlQ0BwK2BWcYyJMK9P2VnxaEJzO.0EM0MDOxwSNxkjNzEyW}
pvn.bokldgd{LlP0BwJ2BXbZxIMK8P2WnxaEIyO.0FM0LDNxwSNxjiNyEzV}
pvn.bnlkdge{MkP0BwK1BXbZyIMK9O1WnxaEJzN.0FL0MDOwwRMxkiNzEzW}
pvm.college{LlQ0BwK2BXbZyJMK9P2WnxaEJzO.0FL0LDOwwRMxkjMzDzW}
pvm.bollegd{MkP0AwK2BWcYyJMK8P1WoxaEJzO.0EL0MDOwvSNwkiNzEzW}
own.collefe{MlQ0AwK1BXcZyJLJ9P2WoxaDJyN.0EM0MCOxwSNxkjNyEzW}
own.collefe{LlQ0BxK2BXcZyJLK9P1VoxaEJzN.0FM0MDOxwSMxkjMzEyW}
own.colldgd{MlQ0BwK2AWcZyJMJ9P2VnxaEJzO.0FM0LDOxwRNxjjNzEzV}
own.colldgd{MkQ0BxK2BXcZyIMK8P2WoxaEJzO.0FL0LDOxwSNxkjNzEzW}
own.coklege{LlQ0BxK2BWcZxJLJ9O1VoxaDIyN.0FM0LDOxvSMwkiNzEzV}
own.coklefe{MlP0BwK2BXcZyILK9P2WnwaEJyO.0FL0LDNxwSNwjjMzEzW}
own.bollege{MlQ0BxK1AXcZyJMK9P2WowaEJzN.0FL0MDOxvRNxjjMyEzW}
own.bolldge{LkQ0AwK1AWcZyIMJ9P2WoxaEJyO.0FM0MCOxwSNwjjNzEyW}
own.bolkdgd{MlP0AxK1BWcZyJMK9O2VoxaEJzO.0FM0MDNxwSMwjiMyDzW}
own.bokkege{MlQ0BxK1AWbZyILJ9P2WoxaEIyO.0EM0LDNxwSNxjiMzEzV}
owm.college{MlQ0BxJ2BXcZyJMK8O1WoxaEJyO.0EL0LDOxwSMxjjNzEzV}
owm.cnlldfe{LlP0AxK2BXcZyIMK8O2WnwaDJzN.0FM0LDOxwSMxkiMyEyW}
owm.cnlkege{MlQ0AxK1BXcYyIMK9P2WoxaEJzN.0FM0MDOxwRNxkjNyEzW}
owm.bollefd{MlQ0BwK1BXbYyJMK8O1WoxaEIzO.0FM0MCNxvRMwkjMzEzV}
ovn.college{MlQ0BxJ2BWcZyJMK9P2WoxaEJzO.0FM0MDOxwSMxkjNzEzW}
ovn.bollefe{MlQ0AxK2BXbYxJLK9O2WoxaDIzO.0FM0LDNxwRMwkjNzEyW}
ovn.bnklegd{LlQ0BxK2BXcYxJMJ8P1WoxaEJyO.0FM0LCNwvRMxkjNyEyW}
ovm.colldgd{LkQ0BxJ2BWcYyJLJ9O2WnxaEJzN.0FM0MDOxwRNxkjNyEyW}
ovm.coklege{MlP0BxJ2AWcYyJMK9P1WoxaEIzO.0FM0MDOxwSNwkiNzDyW}
ovm.bnlkege{MlP0BxK2BXcZyJMJ8O2WnxaEJyO.0FM0MDNwwRNwkiNyEzW}
hacker@data~sorting-data:~$ 
```
it was mentioned that once the contents are sorted, the flag will be in the last. Therefore used the modifier `-r` along with the command `sort` to sort into a `Z-A` order instead of a regular alphabetical order.

## WHAT I LEARNED 
Files (or output lines of commands) aren't always in the order we need them. The sort command helps us organize data. It reads lines from input (or files) and outputs them in sorted order. By default, sort orders lines alphabetically.  We can add modifiers to the command to change the order.

## REFERENCES 
none.



