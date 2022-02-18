### Always try to give this commented line before scripts-
```
# Author: John Doe
# Created: 7th July 2020
# Last Modified: 7th July 2020
# Description: Creates a backup in ~/bash_course folder of all files in the home directory
# Usage: backup_script
```
---
### How to add script folder path to enviroment variable-   see it later
                 
---
### Variables-
There are mainly two types of variable-  </br>
#### 1) shell variable- variable name would be always capital. </br>
some of examples- </br>
**HOME** Absolute path to the current user's home directory  </br>
**PATH** List of directories that the shell should search for executable files  </br>
**USER** The current user's username  </br>
**HOSTNAME** The name of the current machine  </br>
**HOSTTYPE** The current machine's CPU architecture  </br>
**PS1** The terminal prompt string  </br>
#### 2) user defined variable-  </br>
name=value (no quoatation)</br>
Note 1: There should be no spaces around the equals sign </br>
Note 2: Names of user-defined variables should be all lowercase </br>
### How to take output of a variable or parameter Expansion or variable expansion-
1) Simple Syntax: $Variable_name     // this is correct.  </br>
2) Advanced Syntax: ${Variable_name}  // this is also correct. it is a best prectise to use this.
### variable/parameter Expansion 
${Variable_name^} </br>
Convert the first character of the parameter to uppercase </br>
</br>
${Variable_name^^} </br>
Convert all characters of the parameter to uppercase </br>
</br>
{Variable_name,} </br>
Convert first character of the parameter to lowercase </br>
</br>
${Variable_name,,} </br>
Convert all characters of the parameter to lowercase </br>
</br>
${#Variable_name} </br>
Display how many characters the variable’s value contains </br>
</br>
${Variable_name : offset : length} </br>
The shell will expand the value of the parameter starting at
character number defined by “offset” and expand up to a length
of 'length'

---
### assign a output of a command inside a variable -
#### Syntax
```
variable_name=$(command)
```
**remember**- there would be no space in both side of = side.<br /> command should be wrapped by single first bracket.<br /> give $ sign before first bracket.
#### Example1-
```
#!/bin/bash
hi=$(echo "ar")  # echo "ar" gives a output ar, then this ar will be assign to hi variable.
echo "${hi}"  # it will show ar as a output
```
#### Example2-
```
#!/bin/bash
hi=$(curl https://api.github.com/users/defunkt)
echo "${hi}"
```
---
### Arithmetic Expansion -
it is helping us to solve mathematical problem. But it cannot solve equation with decimal number. to solve decimal number we need to use BC.
#### Syntax
echo $(( expression ))
#### Example 1-
a=$(( 2+2 ))
echo $a
#### Example 2-
echo $(( 2+2 ))
**ARITHMETIC OPERATORS RANKED IN ORDER OF PRECEDENCE (HIGHEST PRECEDENCE FIRST):** </br>




