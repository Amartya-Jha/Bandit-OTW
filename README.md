
# Bandit@OverTheWire

## Level 0

`ssh bandit0@bandit.labs.overthewire.org -p 2220` to connect.

`ls` : check the files in directory

`cat README.md` : to read the file.

pass for level 1: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

## Level 1

`ls`: there a file named "-".

`cat ./-`: to open the file.

pass for lvl 2: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Level 2

`ls`: there's a file with spaces

`cat spaces\ in\ this\ filename`

pass for lvl 3: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Level 3

`ls` : there's a dir named inhere.

`ls` again but it's empty.

`ls -al` : list all files, and there's a hidden file    

`cat .hidden` : and we get pass.

pass for next lvl: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Level 4

`ls`: there's 1 dir "inhere"

`cd inhere`

`ls`: there multiple files, but our pass is in the only human readable file

`file ./*`: give's data type of all the fines in the dir. and our pass is in "-file07"

pass for lvl 5: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Level 5
Given: human readable, 1033 bytes size and non executable.

`find -readable -size 1033c ! -executable` 

our pass is in "./maybehere07/.file2"

pass for lvl 6 is: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Level 6

Given: owned by user bandit7, 
owned by group bandit6, 
33 bytes in size

`find / -user bandit7 -group bandit6 -size 33c `  
we get a list of file for which we dont have permission for but there's one password file in between

"/var/lib/dpkg/info/bandit7.password" this is where our pass is.

pass for lvl 7 is: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S.

## Level 7

Given: pass is next to the word "millionth"

`cat data.txt | grep millionth`

pass for lvl 8 is: TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Level 8

Given: The password for the next level is stored in the file data.txt and is the only line of text that occurs only once


`sort data.txt | uniq -c | grep '^ *1 '`

pass for lvl 9 is: EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Level 9

Given: The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

`strings data.txt | grep =`

pass for lvl 10 is: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Level 10

Given: The password for the next level is stored in the file data.txt, which contains base64 encoded data

`cat data.txt | base64 -d`

pass for lvl 11 is : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Level 11

Given: The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

`cat data.txt | tr a-zA-Z n-za-mN-ZA-M`

`tr`: translate, changine a to m, because a is the 1st character and m is 13th, so a-m becomes n-z and n-z becomes a-m.

Pass for lvl 12 is: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv.

## Level 12

Given: The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

`mv` : move

`rm`: remove

check the data type, change extension to that data type and then decompress using respective tool. Repeat till you get the pass.

pass for lvl 13: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
