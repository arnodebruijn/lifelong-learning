Shell scripting
==============

Shell boilerplate
-----------------
Start shell scripts with these sane defaults

```sh
#!/bin/sh

# Treat unset variables as an error, and exit immediately when any command fails
set -euo pipefail
```


Standard streams
----------------

Every Linux programs has three streams opened when it starts. These are attached to the users terminal, or we can make use of them as special file descriptors

| Type    | Symbol | Purpose                                                                            |
| ------- | ------ | ---------------------------------------------------------------------------------- |
| stdin   | 0<     | Standard input, comes from the keyboard for instance.                              |
| stdout  | 1>     | Standard output, created at processing time, goes to the console or your terminal  |
| stderr  | 2>     | Standard error, commands output errors here                                        |

* Use ```<``` or ```0<``` to take input from a file instead of the keyboard, for example with an interactive program that requires user input ```ftp test.com < commands.txt```
* Use ```>``` or ```1>``` to redirect standard output to a file
* Use ```>>``` if you want the output to be appended to a file
* Use ```|``` to feed the output of one process to the input of the next one ```cat /proc/cpuinfo | grep vmx```
* Use the ```tee``` command to output both to a file and forwards on the pipeline ``` ls | tee output.txt```
* Use ```!!``` to execute the last command
* Use ```'``` (single quotes) to preserve the literal value
* Use ```"``` (double quotes) for interpolation



Conditional expressions
-----------------------
* An if some_command; then construct tests whether the exit status of a list of commands is 0 (0 means success)
* if [ ... ]; then construct evaluates the expression between square brackets, and checks if true



Command reference
-----------------

| Command | Description                                                                 | Example                                       |
|---------|-----------------------------------------------------------------------------|-----------------------------------------------|
| &       | Run the previous command in the background                                  | ls &                                          |
| &&      | Logical AND                                                                 | if [ "$foo" -ge "0" ] && [ "$foo" -le "9"]    |
| \|\|    | Logical OR                                                                  | if [ "$foo" -lt "0" ] \|\| [ "$foo" -gt "9" ] |
| ^       | Start of line                                                               | grep "^foo"                                   |
| $       | End of line                                                                 | grep "foo$"                                   |
| =       | String equality (cf. -eq)                                                   | if [ "$foo" = "bar" ]                         |
| !       | Logical NOT                                                                 | if [ "$foo" != "bar" ]                        |
| $$      | PID of current shell                                                        | echo "my PID = $$"                            |
| $!      | PID of last background command                                              | ls & echo "PID of ls = $!"                    |
| $?      | exit status of last command                                                 | ls ; echo "ls returned code $?"               |
| $#      | Number of arguments passed to function                                      |                                               |
| $0      | Name of current command (as called)                                         | echo "I am $0"                                |
| $1      | Name of current command's first parameter                                   | echo "My first argument is $1"                |
| $9      | Name of current command's ninth parameter                                   | echo "My ninth argument is $9"                |
| $@      | All of current command's parameters (preserving whitespace and quoting)     | echo "My arguments are $@"                    |
| $*      | All of current command's parameters (not preserving whitespace and quoting) | echo "My arguments are $*"                    |
| -eq     | Numeric Equality                                                            | if [ "$foo" -eq "9" ]                         |
| -ne     | Numeric Inquality                                                           | if [ "$foo" -ne "9" ]                         |
| -lt     | Less Than                                                                   | if [ "$foo" -lt "9" ]                         |
| -le     | Less Than or Equal                                                          | if [ "$foo" -le "9" ]                         |
| -gt     | Greater Than                                                                | if [ "$foo" -gt "9" ]                         |
| -ge     | Greater Than or Equal                                                       | if [ "$foo" -ge "9" ]                         |
| -z      | String is zero length                                                       | if [ -z "$foo" ]                              |
| -n      | String is not zero length                                                   | if [ -n "$foo" ]                              |
| -nt     | Newer Than                                                                  | if [ "$file1" -nt "$file2" ]                  |
| -d      | Is a Directory                                                              | if [ -d /bin ]                                |
| -f      | Is a File                                                                   | if [ -f /bin/ls ]                             |
| -r      | Is a readable file                                                          | if [ -r /bin/ls ]                             |
| -w      | Is a writable file                                                          | if [ -w /bin/ls ]                             |
| -x      | Is an executable file                                                       | if [ -x /bin/ls ]                             |
