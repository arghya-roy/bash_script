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
`-a file` True if file exists. </br>
`-b file` True if file exists and is a block special file . </br>
`-c file` True if file exists and is a character special file . </br>
`-d file` True if file exists and is a directory. </br>
`-e file` True if file exists. </br>
`-f file` True if file exists and is a regular file. </br>
`-g file` True if file exists and its set-group-id bit is set. </br>
`-h file` True if file exists and is a symbolic link. </br>
`-k file` True if file exists and its “sticky” bit is set. </br>
`-p file` True if file exists and is a named pipe (FIFO). </br>
`-r file` True if file exists and is readable. </br>
`-s file` True if file exists and has a size greater than zero. </br>
`-t fd` True if file descriptor fd is open and refers to a terminal. </br>
`-u file` True if file exists and its set-user-id bit is set. </br>
`-w file` True if file exists and is writable. </br>
`-x file` True if file exists and is executable. </br>
`-G file` True if file exists and is owned by the effective group id. </br>
`-L file` True if file exists and is a symbolic link. </br>
`-N file` True if file exists and has been modified since it was last read. </br>
`-O file` True if file exists and is owned by the effective user id. </br>
`-S file` True if file exists and is a socket. </br>
`file1 -ef file2` True if file1 and file2 refer to the same device and inode numbers. </br>
`file1 -nt file2` True if file1 is newer (according to modification date) than file2 , or if file1 exists and file2 does not. </br>
`file1 -ot file2` True if file1 is older than file2 , or if file2 exists and file1 does not. </br>
`-o optname` True if the shell option optname is enabled (see set -o for a list of options). </br>
`-v varname` True if the shell variable varname is set (has been assigned a value, even an empty value). </br>
`-R varname` True if the shell variable varname is set and is a name reference. </br>
`-z string` True if the length of string is zero. </br>
`-n string` True if the length of string is non-zero. </br>
`string1 == string2` True if the strings are equal. It will perform pattern matching when used with the [[ command. The = notation should be used with the test command for POSIX   conformance. </br>
`string1 = string2` (same as string1 == string2 ). </br>
`string1 != string2` True if the strings are not equal. </br>
`string1 =~ regex` True if the strings match the Bash regular expression regex. Captured groups are stored in the BASH_REMATCH array variable. </br>
`string1 < string2` True if string1 sorts before string2 lexicographically. </br>
`string1 > string2` True if string1 sorts after string2 lexicographically. </br>
`arg1 -eq arg2` True if arg1 equal to arg2 </br>
`arg1 -ne arg2` True if arg1 not equal to arg2 </br>
`arg1 -lt arg2` True if arg1 less than arg2 </br>
`arg1 -le arg2` True if arg1 less than or equal to arg2 </br>
`arg1 -gt arg2` True if arg1 greater than arg2 </br>
`arg1 -ge arg2` True if arg1 greater than or equal to arg2 </br>



---
## if - else condition -
start and end using the reserved words “if” and “fi”. </br>
check the exit status of a command and only runs the command if a certain condition is true.
### syntax -
There are four types of syntax - </br>
1) if ( command ); </br>
2) if (( command )); </br>
3) if [ command ]; </br>
4) if [[ command ]]; </br>
