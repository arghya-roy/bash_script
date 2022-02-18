---
### assign a output of a command inside a variable -
#### Syntax
```
variable_name=$(command)
```
**remember**- there would be no space in both side of = side. command should be wrapped by single first bracket. give $ sign before first bracket.
#### Example-
```
#!/bin/bash
hi=$(echo "ar")  # echo "ar" gives a output ar, then this ar will be assign to hi variable.
echo "${hi}"  # it will show ar as a output
```
---
