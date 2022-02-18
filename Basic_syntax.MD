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
a=$(( 2+2 )) </br>
echo $a
#### Example 2-
echo $(( 2+2 )) </br> 
echo $(( 2-2 )) </br>
echo $(( 2*2 )) </br>
echo $(( 2/2 )) </br>
echo $(( 2%2 )) </br>
echo $(( 5/2 )) // as a outout of this it gives 2 but the answer would be 2.5, so this method cannot solve decimal related problem. </br>
                   to overcome this problem we use BC Command.
</br>
**ARITHMETIC OPERATORS RANKED IN ORDER OF PRECEDENCE (HIGHEST PRECEDENCE FIRST):** </br>
</br>
![Name](https://github.com/arghya-roy/bash_script/blob/main/Screenshot%20(364).png "i")

---
### BC COMMAND -
#### Syntax-
**Using the bc command for normal equation**
echo “expression” | bc
**Using the scale variable to control the number decimal places shown**
echo “scale=value; expression” | bc
**example1-**
```
echo "12/5" | bc
```
If we run the above command then also it gives 2, but it needs to give 2.4
to get the correct output we have to use scale before expression-
```
echo "scale=2; 12/5" | bc
```
scale=2 means it gives 2.40, it we write scale=3 then it gives 2.400

---
### Tidle Expansion -
we can that this a shortcut of some must useful command line or variable </br>
`~` = It shows the current user's home directory path. Means It is Exactly same as $HOME </br>
`~username` like `~ec2-user` if username refers to a valid user, give the path to that 
user's home directory. </br>
`~+` It gives the present working directory same as $PWD command. </br>
`~-` It gives my previous working directory, same as $OLDPWD. </br>

---
### Brace Expansion - 
A way of automatically generating text according to a
certain pattern.
**Example-**
```
echo {1,2,3,4,5}                   // it print 1 to 5
echo {1..5}                       // it also print 1 to 5
echo {a..e}                       // it print a to e
echo {1..5..2}                    // it print 1 3 5, means it skips 2 numbers.
echo Month{01..12}                // it print month01 to month12
touch file{1..5}.txt              // it creates folder from file1.text to file5.text
mkdir folder1                      // creayes directory
touch folder1/file{1..2}.txt      // it created file1.txt and file.txt inside folder1.
```

