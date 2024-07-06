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

## Arrays
For this module, it is suggested to follow along in the attackbox or a standard linus terminal to make it easier to understand.

Arrays are used to store multiple pieces of data in one variable, which can then be extracted by using an index. Most commonly notated as `var[index_position]`.

Arrays use indexing meaning that each item in an array stands for a number.

In the array `['car', 'train', 'bike', 'bus']` each item has a corresponding index.

All indexes start at position 0.

| item  | index |
|-------|-------|
| car   |   0   |
| train |   1   |
| bike  |   2   |
| bus   |   3   |

Now we have covered this, let's make an array in bash.

The syntax is as follows.

We have the variable name, in our case 'transport'.

We then wrap each item in brackets leaving a space between each item.

`transport=('car', 'train', 'bike', 'bus')`

We can then echo out all the elements in our array like this:

`echo "${transport[@]}"`

You can try this in your own terminal and see what it outputs.

Where the "@" means all arguments, and the [] wrapper around it specifies its index.

So what if we wanted to print out the item `train`?

We would simply type:

`echo "${transport[1]}"`

Because the train is at index position 1.

The last thing we will cover is if we want to change an element, or delete it. If we wanted to remove an element we would use the `unset` utility.

`unset transport[1]`

This now removes the `train` item, if we wanted to we could echo it back out and see that it is indeed gone,

Now lets set it to something else. We can do:

`transport[1]='trainride'`

If we echo the array the we get:

`car trainride bike bus`

So we successfully managed to swap out an element in our array!

As a little side project try building on your previous project of a biography maker, include arrays so that you can store multiple names and multiple facts about the person. Then in the next module we can expand even further.

Given the array please answer the following questions

`cars=('honda', 'audi', 'bmw', 'tesla')`

## Conditionals
When we talk about conditionals it means that a certain piece of code relies on a condition being met, this is often determined with relational operators, such as equal to, greater than, and less than.

We will make a simple "if" statement to check if a variable is equal to a value, we will also make a script that checks if a file exists and that it is writeable, if it is we will write a message to that file, if not writeable it will delete it and make a new one. A lot of new things will be taught here so pay attention.

First, we will discuss the basic syntax of an if statement.

All if statements look like so:

```
#!/bin/bash

if [some condition]
then
  do something
else
  do something different
fi
```
Let's look at an example:

```
#!/bin/bash

const=10
if [$count -eq 10]
then
  echo "true"
else
  echo "false"
fi
```

If statements always use a pair of brackets and in the case of the [] we need to leave space on both sides of the text (the bash syntax). We also always need to end the if statement with `fi`.

Here a variable is being declared as 10 and in the top line of the if statement the variable $count is being compared to the integer 10.

If they are equal then it outputs **true**, if its false it outputs **false**. As we know 10 is equal to 10 so it outputs true.

the **-eq** is one way of doing this, you could also use **"="**

| Operator | Description                                                                                                                          |
| -eq      | Checks if the value of two operands are equal or not; if yes, then the condition becomes true.                                       |
| -ne      | Checks if the value of two operands are equal or not; if values are not equal, then the condition becomes true.                      |
| -gt      | Checks if the value of left operand is greater than the value of right operand; if yes, then the condition becomes true.             | 
| -lt      | Checks if the value of left operand is less than the value of right operand; if yes, then the condition becomes true.                |
| -ge      | Checks if the value of left operand is greater than or equal to the value of right operand; if yes, then the condition becomes true. |

So now let's use this to make a little script that compares an input (a parameter) and check it against a value to check if it's true or not. A guessing game if you will.

```
#!/bin/bash

value="guessme"
guess=$1
if [ "$value = "$guess" ]
  then
echo "The are equal"
else
  echo "They are not equal"
fi
```