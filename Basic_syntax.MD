### Always try to give this commented line before scripts-
```
# Author: John Doe
# Created: 7th July 2020
# Last Modified: 7th July 2020
# Description: Creates a backup in ~/bash_course folder of all files in the home directory
# Usage: backup_script
```
---
### How to add script folder path to enviroment variable-
     see it later
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

