## CHAINING COMMANDS WITH LIST OPERATORS
**LIST** - When you put one or more commands on a given line. </br>
**LIST OPERATORS** - Types of control operators that enable us to create lists of commands that operate in different ways.
#### LIST OPERATORS - 
#### command1 & command2  - 
Sends command1 into a subshell to run “asynchronously” in the background, and continues to process 
command2 in the current shell.

#### command1 ; command2  - 
Runs command1 and command2, i.e. one after the other. The shell will wait for command1 to </br>
complete before starting command2. 

#### command1 && command2 -  
The “and” operator. The shell will only run command2 if command1 is
successful (i.e. returns an exit code of 0). 

#### command1 || command2 -  
The “or” operator. The shell will only run
command2 if command1 is unsuccessful (i.e. returns a non-zero exit code).

---
### TEST COMMANDS + CONDITIONAL OPERATORS:
“a command that can be used in bash to compare
different pieces of information”
#### Syntax - [ EXPRESSION ]


`-eq` `[ 2 -eq 2 ]` Successful if the two numbers are equal </br>
`-ne` `[ 2 -ne 2 ]` Successful if the two numbers are not equal </br>
`=` `[ $a = $b ]` Successful if the two strings are equal </br>
`!=` `[ $a != $b ]` Successful if the two strings are not equal </br>
`-z` `[ -z $c ]` Successful if a string is empty </br>
`-n` `[ -n $c ]` Successful if a string is not empty </br>
`-e` `[ -e /path/to/file ]` Successful if a file system entry /path/to/file exists </br>
`-f` `[ -f /path/to/file ]` Successful if a file system entry /path/to/file exists and is a regular file </br>
`-d`  `[ -d /path/to/dir ]` Successful if a file system entry /path/to/file exists and is a directory </br>
`-x` `[ -x /path/to/file ]` Successful if a file system entry /path/to/dir exists and is executable by the current user </br>

---
## if - else condition -
start and end using the reserved words “if” and “fi”. </br>
check the exit status of a command and only runs the command if a certain condition is true.
### syntax -
`if [ $number -gt 0 ];` or if command 
