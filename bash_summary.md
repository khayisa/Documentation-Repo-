# Bash Scripting Tutorial Summary 
 ### **What is a Bash script?**

 A Bash script is a file containing a series of commands that can be executed by the Bash shell. It allows us to automate tasks, manipulate files, and interact with the operating system.
 ## Basic Commands
 1. **Navigating the Directory** use the following commands 
    - `pwd ` to Print working directory<br>
    - `ls` to List directory contents <br>
    - `cd` <directory> to Change directory

 
 2. **File Operation** use the following commands 
    - `touch <file>` to create a new file
    - `mkdir <directory>` to create a new directory
    - `rm <file>` to remove a file
    - `rm -r <directory>` to remove a directory and its contents

3. **Viewing and editig files** use the following commands 
    - `cat <file>` to view file contents
    - ` nano <file>` to edit file with nano editor

4. **Getting Help** use the following command 
   - `nano <command>` to show manual for a command



## Piping 


Piping in Git Bash (and Unix-like systems) allows you to pass the output of one command as input to another command. This is useful for chaining commands together to perform more complex operations. Here's a guide on how to use piping effectively in Git Bash:

### Basic Syntax

The basic syntax for piping is:

```bash
command1 | command2
```

This takes the output of `command1` and uses it as the input for `command2`.

### Common Use Cases

#### 1. **Viewing Command Output with `less`**

You can use `less` to view long outputs page by page.

```bash
ls -l | less
```

#### 2. **Filtering Output with `grep`**

`grep` is used to search for specific patterns in the output.

```bash
ls -l | grep ".txt"
```

#### 3. **Counting Lines, Words, and Characters with `wc`**

`wc` (word count) can count the number of lines, words, and characters in the output.

```bash
ls -l | wc -l
```

#### 4. **Sorting Output with `sort`**

`sort` is used to sort the output alphabetically or numerically.

```bash
ls -l | sort
```

#### 5. **Removing Duplicates with `uniq`**

`uniq` is used to remove duplicate lines from sorted output.

```bash
ls -l | sort | uniq
```

### Advanced Piping Examples

#### 1. **Combining Multiple Commands**

You can combine multiple commands using pipes to perform complex operations.

```bash
cat file.txt | grep "pattern" | sort | uniq
```

#### 2. **Using `cut` to Extract Columns**

`cut` is used to extract specific columns from the output.

```bash
cat file.txt | cut -d " " -f 1
```

In this example, `-d " "` specifies the delimiter as a space, and `-f 1` specifies that we want the first column.

#### 3. **Finding and Counting Unique Words in a File**

```bash
cat file.txt | tr ' ' '\n' | sort | uniq -c | sort -nr
```

- `tr ' ' '\n'` translates spaces to newlines, effectively splitting the text into words.
- `sort` sorts the words alphabetically.
- `uniq -c` counts the occurrences of each unique word.
- `sort -nr` sorts the words by frequency in descending order.

### Redirecting Output to a File

In addition to piping, you can redirect the output of a command to a file using the `>` operator.

```bash
ls -l > output.txt
```

You can also append to a file using `>>`.

```bash
ls -l >> output.txt
```

### Combining Piping and Redirection

You can combine piping and redirection to save the output of a series of piped commands to a file.

```bash
cat file.txt | grep "pattern" | sort | uniq > result.txt
```

 

 

 ## Variables 

### 1. **Creating Variables**

To create a variable, you simply assign a value to a name. There should be no spaces around the `=` sign.

```bash
# String variable
NAME="John Doe"

# Numeric variable
AGE=30
```

### 2. **Using Variables**

To use the value of a variable, prefix the variable name with a dollar sign `$`.

```bash
echo "Name: $NAME"
echo "Age: $AGE"
```

### 3. **Environment Variables**

Environment variables are variables that are available to any child processes of the shell. You can set an environment variable using the `export` command.

```bash
export MY_VAR="This is an environment variable"
echo $MY_VAR
```

### 4. **Reading User Input into Variables**

You can use the `read` command to get input from the user and store it in a variable.

```bash
echo "Enter your favorite color:"
read COLOR
echo "Your favorite color is $COLOR"
```

 
### 5. **Arithmetic Operations**

You can perform arithmetic operations using the `let` command, double parentheses `(( ))`, or the `expr` command.

```bash
# Using let
let RESULT=5+3
echo $RESULT

# Using double parentheses
RESULT=$(( 5 + 3 ))
echo $RESULT

# Using expr
RESULT=$(expr 5 + 3)
echo $RESULT
```

### 6. **String Operations**

You can concatenate strings and manipulate them in various ways.

```bash
# Concatenation
GREETING="Hello"
TARGET="World"
MESSAGE="$GREETING, $TARGET!"
echo $MESSAGE

# String length
echo ${#MESSAGE}

# Substring
echo ${MESSAGE:0:5}
```

### 7. **Conditional Statements with Variables**

You can use variables within conditional statements.

```bash
if [ "$AGE" -gt 20 ]; then
  echo "You are older than 20."
else
  echo "You are 20 or younger."
fi
```

### 8. **Arrays**

Bash supports one-dimensional arrays.

```bash
# Creating an array
FRUITS=("Apple" "Banana" "Cherry")

# Accessing array elements
echo ${FRUITS[0]}
echo ${FRUITS[1]}
echo ${FRUITS[2]}

# Length of an array
echo ${#FRUITS[@]}

# Adding an element to an array
FRUITS+=("Date")
echo ${FRUITS[@]}
```

 






  
 

