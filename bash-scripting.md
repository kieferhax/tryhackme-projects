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

## Parameters
We will now look at one of the main features of bash and that is using parameters.

We will first look at parameters specified using the command line when running the file. These come in many forms but often have the "$" prefix because a parameter is still a variable.

Lets start by declaring a parameter that is going to be our first argument when running our bash script.

```
#!/bin/bash

name=$1
echo $name
```

We can run our script with `./example.sh Alex`

And sure enough we get returned with "Alex"

So what if we wanted the 2nd argument? Wel the process is very simple and we simply add a `$2` instead of `name=1$`.

Then we run with `./example.sh Alex Tony`

What do you think the terminal would return?

It would return "Tony"

What if we didn't want to supply them like this however, and instead it would let us type in our name in a more interactive way, we can do this using `read`

```
#!/bin/bash

echo Enter your name
read name
echo "Your name is $name"
```

This code will hang after its ran, this gives you the opportunity to type in your name.

And we can see that is worked!

Maybe try making a little biography maker, where you take the name, age, and job as parameters. Store them inside a variable and then output them to the screen inside a sentence.

However there is so much more that you can do with parameters and I advice you to play around with them, after all practice is what makes you better.