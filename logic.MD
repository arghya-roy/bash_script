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
## if - else condition -
#### Syntax - [ EXPRESSION ]


