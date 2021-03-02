## variable declaration and access example:
```
foo="some data"
echo $foo
```

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