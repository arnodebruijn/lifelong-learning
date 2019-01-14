Operations
==========

Brace expansion
---------------
Generate arbitrary strings from a series of comma separated strings or a sequence expression between a pair of braces. Example:
cp -v file1.txt{,.bak}

Commandline manipulation
-------------------------
C^A       go to the beginning of the line
C^E       go to the end of the line
!!        repeat last command
!#        the entire command line typed so far
!$        the last argument
!string   the most recent command in the history list beginning with string

Ctrl + k – delete from cursor to the end of the command line
Ctrl + u – delete from cursor to the start of the command line
Ctrl + w – delete from cursor to start of word (i.e. delete backwards one word)
Ctrl + y – paste word or text that was cut using one of the deletion shortcuts (such as the one above) after the cursor
Ctrl + xx – move between start of command line and current cursor position (and back again)
Alt + b – move backward one word (or go to start of word the cursor is currently on)
Alt + f – move forward one word (or go to end of word the cursor is currently on)
Alt + d – delete to end of word starting at cursor (whole word if cursor is at the beginning of word)
Alt + c – capitalize to end of word starting at cursor (whole word if cursor is at the beginning of word)
Alt + u – make uppercase from cursor to end of word
Alt + l – make lowercase from cursor to end of word
Alt + t – swap current word with previous
Ctrl + f – move forward one character
Ctrl + b – move backward one character
Ctrl + d – delete character under the cursor
Ctrl + h – delete character before the cursor
Ctrl + t – swap character under cursor with the previous one

Shell redirections
------------------
>   redirect output to overwrite
>>  redirect output to append
<   redirect input to overwrite

Miscellaneous
-------------
`${PWD##*/}`    last directory in current path
0 STDIN
1 STDOUT
2 STDERR
2>&1                redirects STDERR to STDOUT

Regular expressions
-------------------
The regular expression engine produces the left most match for any regular expression. This is because of the way the engine progresses through the string (left to right and advances the regex on first hit until it can go no further, then potentially backtracks)

Quantifier | Legend       |  Example      | Sample Match
-----------|--------------|---------------|--------------
`*`        | zero or more | `A*B*C*`      | AAACC
`+`        | one or more  | `\w-\w+`      | A-b1_1
`?`        | once or none | `plurals?`    | plural
`{2}`      | exactly two  | `\D{2}`       | AB
`{1,4}`    | one to four  | `\d{1,4}`     | 156
`{4,}`     | four or more | `\w{4,}`      | reg_ex_tut


diff
----
Prescriptively tells you how to change the first file to make it match the second

First line is formatted like so:
  [line numbers first file][a(dd),c(hange),d(elete)][line numbers second file]

For example:
  ```2,4c2,4```
means: "Lines 2 through 4 in the first file need to be changed to match lines 2 through 4 in the second file."

<   lines from the first file
>   lines from the second file
--- separates the two files

For a side-by-side diff use ```sdiff``` or ```diff -y```
You can also compare directory contents with diff
