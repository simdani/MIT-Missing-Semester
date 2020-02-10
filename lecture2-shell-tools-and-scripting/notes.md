# Lecture 2: Shell tools and Scripting

Variable assigning (spaces are important)

```Bash
foo = bar
echo $foo
echo "Hello"
echo "Value is $foo"

mcd () { # make and cd to dir
    mkdir -p "$1"
    cd "$1"
}

source mcd.sh # execute and load script
```

- \$0 - Name of the script
- $1 to $9 - Arguments to the script. \$1 is the first argument and so on.
- \$@ - All the arguments
- \$# - Number of arguments
- \$? - Return code of the previous command
- $$
  $$
- !! - Entire last command, including arguments.
- \$\_ - Last argument from the last command.

true code is 0
false code is 1

conditionals (||, &&)

```Bash
false || echo "Oops fail" # Oops fails
false && echo "This will not print
```

Assigning output to variables

```Bash
foo=$(pwd)
echo $foo
```

```Bash
#!/bin/bash

echo "Starting program at $(date)" # Date will be substituted

echo "Running program $0 with $# arguments with pid $$"

for file in $@; do
    grep foobar $file > /dev/null 2> /dev/null
    # When pattern is not found, grep has exit status 1
    # We redirect STDOUT and STDERR to a null register since we do not care about them
    if [[ $? -ne 0 ]]; then
        echo "File $file does not have any foobar, adding one"
        echo "# foobar" >> "$file"
    fi
done

```

Wildcards
You can use ? and \* match one ar any amount of characters respectively
Curly braces {} - Whenever you have a common substring in a series of commands you can use curly braces for bash to expand this automatically.

shellcheck # checks syntax sh syntax

Finding

```Bash
find . -name src -type d # find src directory
find . -path '**/test/*.py' -type f # find files
find . -mtime -1 # modified in last day
find . -name "*.tmp" -exec rm {} \; # remove all rm files
locate tmp # find from index
grep foobar mcd.sh
grep -R foobar .
rg "import requests" -t py ~/scratch
```

Ripgrep # https://github.com/BurntSushi/ripgrep

```Bash
history # show command line history
history 1 | grep convert
tree
```

For faster navigation

fzf https://github.com/junegunn/fzf
broot https://github.com/Canop/broot
nnn https://github.com/jarun/nnn
autojump https://github.com/wting/autojump
