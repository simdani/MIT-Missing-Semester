# Lecture 1: Course Overview + The Shell

Environmental variable - dynamic-named value that can affect the way running processes will behave on a computer.

```Bash
echo $PATH # Bash will show though these paths till it finds command we re looking for.
which echo # Shows what program will be run
``` 

absolute path - refers to complete details needed to locate a file or folder, starting from the root element

```Bash
pwd # Show working directory
cd # Navigating through system
cd ~ # Brinds to home directory
cd - # Navigate to previous directory
ls # list files in given directory
ls -l # list files with more info (permissions, owners)
```

Getting help
```Bash
ls --help # Shows how to use ls command
man ls # Shows manual page for ls command
```

File/Folder permissions (read, write, execute)

```Bash
mv # Rename/move file to completely different directory
cp # lets you copy a file
rm # remove file
rmdir # remove empty directory
mkdir # create empty directory
```

Removal is not recursive by default in unix

ctrl + L - clears terminal screen and moves to top

Every program has input and ouput streams. Shell gives us a way to rewire streams (<) - rewire the input (>) - rewire the output into this file.

```Bash
echo hello > hello.txt # Creates hello.txt file with hello text
cat hello.txt # prints the content of file
cat < hello.txt
cat < hello.txt > hello2.txt # hello.txt content to hello2.txt
cat < hello.txt >> hello2.txt # >> appends
```

Pipe character (|) - take output and make it input (not just for text data)
```Bash
ls -l / | tail -n1 # pipe wires them together
ls -l / | tail -n1 > ls.txt
curl --head --silent google.com | grep -i content-length | cut --delimiter = ' ' -f2 # print google.com content length
```

Root user - super user (can do anything on system)
```Bash
sudo # do the following command as root user
sudo su # switch to root
tee # reads standard input and writes it to both standard output and one or more files, effectively duplicating its input
```