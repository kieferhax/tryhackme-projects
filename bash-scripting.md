# Welcome to introductory bash scripting

## Introduction

### What is bash?
Bash is a scripting language that runs within the terminal on most Linux distros, as well as macOS. Shell scripts are a sequence of bash commands within a file, combined together to achieve more complex tasks than simple one-liner and are especially useful when it comes to automating sysadmin tasks such as backups.

Topics covered include:

- Bash syntax
- Variables
- Using parameters
- Arrays
- conditionals

[Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html)

## Our first simple bash scripts
First, let's lay out some structure.

A bash script always starts with the following line of code at the top of the script.

```
#!/bin/bash
```

This is so your shell (whatever type it may be) knows that it needs to run your file using bash in the terminal

Lets get into some basic examples.

```
#!/bin/bash

echo "Hello World!"
```

This will return the string "Hello World!" The command `echo` is used to output text to the screen, the same way as `print` in python. I suggest you test this out in your terminal to get the hang of bash.

You can also perform normal Linux commands insider your bash scripts and it will be executed if formatted correctly. For example, we can run the command `ls` inside our bash scripts and we will see the output when we run the file. So lets make it do this!

```
#!/bin/bash

echo "Hello World"
whoami
id
```

To run a bash script we must first give it executable permissions.

`Chmod +x yourfile.sh`

And then we run it using `./`

