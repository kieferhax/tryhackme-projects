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

## Variables
Variables in bash are fairly simple and we can create them like so:

```
#!/bin/bash

name="Jammy"
```

Where we give the value of `Jammy` and assign it to the variable `name`.

Please note that for variables to work you cannot leave a space between the variable name, the "=" and the value. They cannot have spaces between them.

So how would we now use our variables? Well its also very simple.

We have to add a `$` onto the front of our variable name in order to call it.

```
#!/bin/bash

name="Jammy"
echo $name
```

If we test this out in our terminal we get something like this:

`$ name="Jammy"`
`$ echo $name`
`Jammy`

This would output "**Jammy**" to the screen.

Variables make it much easier to store data and rather than typing out the same thing in multiple places we could simply insert our variables with $var and then declare that to a certain value making it easier to fall back on if you do something wrong and need to change it.