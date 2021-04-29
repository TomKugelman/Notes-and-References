## variable declaration and access example:
### Standard vairable declaration
```
foo="some data"
echo $foo
```
### System variable commands
`set` sets an env variable

`env` dunno

`printenv` 

## Conditional example:
```
if [ $foo -lt 5 ]
then
    echo $foo
else
    echo 'no foo'
fi
```

### Comparison Operators (don't forget hyphens)

- `-lt` = less than
- `-gt` = greater than
- `-eq` = equal to
- `-ne` = not equal to
- `-le` = less than or equal to
- `-ge` = greater than or equal to
- `-z` = is null

For string comparisons use standard `==` and `!=`

## Loops examples

### For Loops
```
for var in $iterable
do
    echo $var
done
```

### While/Until loops 
Execute WHILE the conditional is true (meaning it will be false at the end) or execute UNTIL the condition is true (meaning it is false at the start) (don't forget spaces between brackets)
```
while/until [ $var -lt 5 ]
do 
    echo $var
    # Remember to incrament/decrement
    var=$((var + 1))
done
```

## Input Examples
### Prompt user for input
```
echo "Guess a number"
read number
echo "You guessed $number"
```

### On shell script call
```
./script.sh red green blue
```
```
echo $1 #red
echo $2 #green
echo $3 #blue
```
Or with a for loop
```
for color in "$@"
do
  echo $color
done
```

### Files as variables
```
# Uses Regex and will grab all subdirectories of <directory>
files=/some/directory/* 
```

## Aliases
You can add arguments to the alias the same way you would calling the script normally
```
alias name_of_alias='./script_name.sh'
```

## Printing or outputting

`printf` for formatted output

`echo` for standard output

`echo 'cat file.txt | awk '{print $2}'

#!/bin/sh


# Basic Shell Scripting

# Rules:
#
# Unless explicitly and otherwise requested...
#
# * assume POSIX shell; avoid Bashisms
#
# * assume POSIX commands; avoid GNUisms
#
# * print to stdout
#
# * create all temporary files and/or directories under $TMPDIR
#
# * create all other files and/or directories under current working directory

################################################################################

################################################################################

# print the current working directory full path
echo $pwd

# list the contents of the current working directory
ls

# print the current user's home directory
echo $HOME

# list the contents of the current user's home directory
ls ~

# print the current user's username
whoami

# print current working directory's parent directory (non-POSIX command ok)
cd ..
echo $pwd
cd -

# list the contents of the current working directory's parent directory
ls ..

# print the current date and time
date

# print the current date and time for UTC
date --utc

# create a temporary file (non-POSIX command ok)
mktemp

# create a temporary directory (non-POSIX command ok)
mktemp -d

# print a temporary path without creating it (non-POSIX command ok)
mktemp -u

# XXXX create a temporary file within the current working directory (non-POSIX
# command ok)

# create a tempfile under /tmp with a prefix of your own choosing
mktemp -t foo.XXXXXXX

# create a temporary file with prefix "foobar." and at least 6 random trailing
# characters (non-POSIX command ok)
mktemp -t foobar.XXXXXX

# print the exit status of the last command
echo $?

# create three empty files: "date.txt", "home.txt", "qux.txt"
touch date.txt home.txt qux.txt

# write the current date into "date.txt"
date >> date.txt

# write the current user's home directory into "home.txt"
echo $HOME >> home.txt
# write the current user's username into "user.txt"
whoami >> qux.txt

# using a for-loop, for each of the files "date.txt", "home.txt", and
# "user.txt", print its full path and content
dirs=(date.txt home.txt qux.txt)

for file in $dirs
do
  realpath $file
  cat $file
done

# create an empty file called "-leading-hyphen.txt"


# list all of the *.txt files in the current working directory
ls | grep *.txt

# print the line, word, and byte counts for _each_ of the previous *.txt files
# and the accumulated total

# print the line, word, and byte counts for _all_ of the previous *.txt files
# (only the accumulated total)

# print the file and/or file system status of "date.txt" (non-POSIX command ok)

# print the total size, in bytes, of "user.txt" (non-POSIX command ok)

# create all path components of the directory ./mystuff/textfiles.d

# copy all text files into ./mystuff/textfiles.d

# recursively find all text files, print each full path, and reverse-sort the
# resulting list (non-POSIX command ok)

# check to see if the file "/usr/share/dict/words" exists; if so, print
#
# "file exists: /usr/share/dict/words"
#
# else print
#
# "file missing: /usr/share/dict/words"

# print all words in /usr/share/dict/words that begin with "x"

# print all words in /usr/share/dict/words that begin with "x" and contain only
# lowercase letters

# print the first three words in /usr/share/dict/words that contain "foo"
# (non-POSIX options ok)

# print the quantity of words in /usr/share/dict/words that contain "bar"

# print a comma-delimited list of words in /usr/share/dict/words that begin
# with "zool"

# use non-POSIX "seq" to print the integers 1..8, one on each line

# use non-POSIX "seq" to print the integers 0..7, one on each line

# use non-POSIX "seq" to print the positive integers divisible by 7 that are
# less than 100

# use non-POSIX "seq" to count the positive integers divisible by 7 that are
# less than 1000000

# use non-POSIX "seq" to print the integers 0..15 as lines of up to 4
# space-delimited strings

# use non-POSIX "seq" to print the integers 0..63 as lines of up to 8
# space-delimited strings

# use non-POSIX "seq" to print the largest integer divisible by 127 and less
# than 65536

# print the file name of the current terminal

# print all settings of the current terminal

# print only the speed of the current terminal

# print the current process identifier (PID)

# print the process status for the current PID

# print the currently executing script

# print the full path to the currently executing script (non-POSIX command ok)

# check (quietly) if the current environment has the "dd" command ; if yes,
# then print
#
# "found command: dd"
#
# else print
#
# "missing command: dd"

# print the full path of the dd command executable

