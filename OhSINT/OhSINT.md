# OhSINT
Are you able to use open source intelligence to solve this challenge?
[OhSINT](https://tryhackme.com/r/room/ohsint)

## Task 1 - OhSINT
What information can you possibly get with just 1 photo?

*Let's download the task file and take a look*

![Downloaded Task File](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/WindowsXP_1551719014755.jpg?raw=true)

*Hmmmm... It's just a screen shot of a WindowsXP desktop... Or is it???*

### Question 1 - What is this user's avatar?

##### Question Hint - exiftool is your friend.  Who is the author of the image? Do they have social media accounts?

*Let's download and install Exiftool to our machine*<br>

*Once exiftool has completed installation, verify via terminal by typing `exiftool`*<br>

*Let's analyze the task file .jpg file we downloaded using exiftool*<br>

`exiftool WindowsXP_1551719014755.jpg`

![Running exiftool against task file](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/exiftool1.png?raw=true)

