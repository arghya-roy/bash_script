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

**need to use [ ] for below -** </br>
`-eq` `[ 2 -eq 2 ]` Successful if the two numbers are equal </br>
`-ne` `[ 2 -ne 2 ]` Successful if the two numbers are not equal </br>
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
`arg1 -eq arg2` True if arg1 equal to arg2 </br>
`arg1 -ne arg2` True if arg1 not equal to arg2 </br>
`arg1 -lt arg2` True if arg1 less than arg2 </br>
`arg1 -le arg2` True if arg1 less than or equal to arg2 </br>
`arg1 -gt arg2` True if arg1 greater than arg2 </br>
`arg1 -ge arg2` True if arg1 greater than or equal to arg2 </br>

**need to use [[ ]] for below -** </br>

`string1 == string2` True if the strings are equal. It will perform pattern matching when used with the [[ command. The = notation should be used with the test command for POSIX   conformance. </br>
`string1 = string2` (same as string1 == string2 ). </br>
`string1 != string2` True if the strings are not equal. </br>
`string1 =~ regex` True if the strings match the Bash regular expression regex. Captured groups are stored in the BASH_REMATCH array variable. </br>
`string1 < string2` True if string1 sorts before string2 lexicographically. </br>
`string1 > string2` True if string1 sorts after string2 lexicographically. </br>
`=` `[[ $a = $b ]]` Successful if the two strings are equal </br>
`!=` `[[ $a != $b ]]` Successful if the two strings are not equal </br>
`-z` `[[ -z $c ]]` Successful if a string is empty </br>
`-n` `[[ -n $c ]]` Successful if a string is not empty </br>




---
## if - else condition -
start and end using the reserved words “if” and “fi”. </br>
check the exit status of a command and only runs the command if a certain condition is true.
### syntax -
There are four types of syntax - </br>
**1) if ( command );** </br>
**2) if (( command ));** </br>
**3) if [ command ];** </br>
**4) if [[ command ]];** </br>

## 1) if ( command ); - Not use too much-
Using single parentheses in bash scripting creates a subshell. When combined with the if statement, the subprocess finishes before continuing the program. The if analyzes the exit status and acts accordingly. </br>
In this commands running inside if does not keep its result, it works as a local command or local variable. we will understand in after reading the below example.
```
outer_variable=Defined
echo Before if:
echo inner_variable = $inner_variable
echo outer_variable = $outer_variable
if (
        echo Inside subshell:
        inner_variable=Defined
        echo inner_variable = $inner_variable
        outer_variable=Changed
        echo outer_variable = $outer_variable
)
then
        echo After then:
        echo inner_variable = $iner_variable
        echo outer_variable = $outer_variable
fi
echo After fi:
echo inner_variable = $inner_variable
echo outer_variable = $outer_variable
```
The program does the following: </br>

Line 1 creates a variable called outer_variable in which we store a string Defined. </br>
Lines 2-4 print the variables to the console. At this moment, outer_variable has a string stored in it, while inner_variable is blank. </br>
Line 5 starts the if statement and a sub-process, delimited by single parentheses. </br>
Line 6-11 store a string inside the inner_variable and change the outer_variable to a different string. Both values print to the console, and the sub-process ends with an exit code. In this case, the sub-process ends successfully with an exit code 0. </br>
Line 12-16 execute after the sub-process and print the variable values. However, the values change back to what they were before the if statement. The sub-process only stores the values locally and not globally. </br>
Lines 16-19 run after the commands in the then clause. The values remain unchanged outside the statement. </br>
#### Output will be -
```
Before if:
inner_variable = 
outer_variable = Defined
Inside subshell:
inner_variable = Defined
outer_variable = Changed
After then:
inner_variable = 
outer_variable = Defined
After fi:
inner_variable = 
outer_variable = Defined
```
## 2) if (( command )); - Arithmetic evaluation and C-style variable manipulation
The double parentheses construct in bash allows: </br>
**Arithmetic evaluation.** Defining a variable as a=$(( 1+1 )) calculates the equation and sets a to 2. </br>
**C-style variable manipulation.** For example, incrementing variables with (( a++ )). </br>
```
variable=4
echo Before first if: $variable
if (( variable++ ))
then
        echo Incremented ++ style: $variable
fi
echo After first if: $variable
if (( variable=variable+1 ))
then
        echo Incremented arithmetically $variable
fi
echo After second if: $variable
```
#### Output will be 
```
Before first if: 4
Incremented ++ style: 5
After first if: 5
Incremented arithmetically 6
After second if: 6
```
#### Remember - 
Double parentheses only works for mathematical equations. if you want to compare some integer then
you have to use [ ] , (( )) does not work for this case.

##### There are some example which you can pass inside double parentheses
`if (( var1=$(( 2+2 )) ));` </br>
`if (( var1=$(( 2-2 )) ));` </br>
`if (( var1=$(( 2/2 )) ));` </br>
`if (( var1=$(( 2%2 )) ));` </br>
`if (( var1=$(( 2*2 )) ));` </br>

## 2) if [ command ]; - compare numbers and testing
Comparing numbers and testing whether a file exists or other testing. 
</br>
#### There are some example which you can pass inside single third bracket.

`-eq` `[ 2 -eq 2 ]` Successful if the two numbers are equal </br>
`-ne` `[ 2 -ne 2 ]` Successful if the two numbers are not equal </br>
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
`arg1 -eq arg2` True if arg1 equal to arg2 </br>
`arg1 -ne arg2` True if arg1 not equal to arg2 </br>
`arg1 -lt arg2` True if arg1 less than arg2 </br>
`arg1 -le arg2` True if arg1 less than or equal to arg2 </br>
`arg1 -gt arg2` True if arg1 greater than arg2 </br>
`arg1 -ge arg2` True if arg1 greater than or equal to arg2 </br>
