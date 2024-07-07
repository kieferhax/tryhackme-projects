# OhSINT
Are you able to use open source intelligence to solve this challenge?
[OhSINT](https://tryhackme.com/r/room/ohsint)

## Task 1 - OhSINT
What information can you possibly get with just 1 photo?

*Let's download the task file*

### Question 1 - What is this user's avatar?

#### Question Hint - exiftool is your friend.  Who is the author of the image? Do they have social media accounts?

*Let's download and install Exiftool to our machine*
*Once exiftool has completed installation, verify via terminal by typing `exiftool`*
*Let's analyze the task file .jpg file we downloaded using exiftool*

`exiftool WindowsXP_1551719014755.jpg`

![Running exiftool against task file](tryhackme-projects/OhSINT/assets/exiftool1.png)