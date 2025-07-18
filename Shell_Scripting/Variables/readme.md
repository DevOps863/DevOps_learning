# variables
* Variables follows dry Princple
    DRY --> don't repeat yourself


* create a variable and assign value to it...

* wherever you are using instead of value, replace it with variable name..


## variable-name=value

1. declaring inside the script
2. how to execute a command inside shell script and take the output
3. you can always get the values of variables from command line

### 1-variables.sh
```
#!/bin/bash

echo "Hello Team, I am implementing varibales in this script"

var1=Bhargav
var2=sumati

echo "$var1: Hi $var2"
echo "$var2: Hi $var1, How are you"
echo "$var1: Hi I am doing good $var2, How are you?"
echo "$var2: I am good $var1, Thanks for asking"
```
* Color can be added to the output of shell scripts using ANSI escape sequences.
* The most common way to use color is with the echo command and the -e option, which enables interpretation of backslash escapes.
```
echo -e "\e[1;31mThis text is red and bold.\e[0m"
echo -e "\e[44;37mThis text is white on a blue background.\e[0m"
```
## Foreground Colors (30-37):
```
30: Black
31: Red
32: Green
33: Yellow
34: Blue
35: Magenta
36: Cyan
37: White
```
### 2-colors.sh
```
#!/bin/bash
GREEN='\e[32m'
BLUE='\e[34m'
NC='\e[0m' # No colour

echo "Hello Team, I am implementing varibales in this script"

var1=Bhargav
var2=sumati

echo -e "$GREEN $var1: Hi $var2 $NC"
echo -e "$BLUE $var2: Hi $var1, How are you $NC"
echo -e "$GREEN $var1: I am doing good $var2, How are you? $NC"
echo -e "$BLUE $var2: I am good $var1, Thanks for asking $NC"
```

## shell script run the command inside $() and stores the output into variable called DATE.

```
#!/bin/bash
DATE=$(date)
echo " This script is executed at timestamp:$DATE"
```

## We can pass the variables from command line as well. 
* $0 --> Script name
* $1 --> First variable 
* $2 --> Second variable ....

**basic_args.sh**
```
#!/bin/bash
GREEN='\e[32m'
BLUE='\e[34m'
NC='\e[0m' # No colour

echo "Hello Team, I am implementing varibales in this script"

var1=$1
var2=$2

echo -e "$GREEN $var1: Hi $var2 $NC"
echo -e "$BLUE $var2: Hi $var1, How are you $NC"
echo -e "$GREEN $var1: I am doing good $var2, How are you? $NC"
echo -e "$BLUE $var2: I am good $var1, Thanks for asking $NC"
```
## command to run
```
sh basic_args.sh Bhargav Ram
```
## Output
```
Hello Team, I am implementing varibales in this script
 Bhargav: Hi Ram
 Ram: Hi Bhargav, How are you
 Bhargav: I am doing good Ram, How are you?
 Ram: I am good Bhargav, Thanks for asking
```
## Write a script to add two numbers.

**Addition.sh**
```
#!/bin/bash

NUM1=$1
NUM2=$2
SUM=$((NUM1 + NUM2))

echo "SUM of two numbers is : $SUM"
```

* I need to connect to a DB using username and password. I can't hardcode the password in the script. So we can use the read command to prompt the user to enter the password.

```
read -s username
```
**DB_Connect.sh**
```
#!/bin/bash

echo "Enter the username:"
read USERNAME

echo "Enter the password"
read -s PASSWORD

# s --> -s option used to hide the password from terminal. It won't show on terminal when you type it.

echo "Connected to DB successfully"
```


