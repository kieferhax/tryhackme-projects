# OhSINT
Are you able to use open source intelligence to solve this challenge?
[OhSINT](https://tryhackme.com/r/room/ohsint)

## Task 1 - OhSINT
What information can you possibly get with just one photo?

*Note: This challenege was updated on 2024-02-01. If you are following any older walkthroughs, expect a small change*

Lets download the Task File and take a look.

![Downloaded Task File](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/WindowsXP_1551719014755.jpg?raw=true)

Hmmm... It's just a screenshot of a WindowsXP desktop... Or is it???

If we click the 'Hint' button next to question 1 a pop-up windows states: "exiftool is your friend. Who is the author of the image? Do they have any social media accounts?"

Lets install exiftool and run it against the task file.

![Running exiftool against task file](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/exiftool1.png?raw=true)

We see the copyright belongs to an "Owoodflint."

Lets Google "Owoodflint" and see what we can find!

![Owoodflint Google search results](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/owoodflint-search.png?raw=true)

Wow! We got a few interesting results from our Google search! We found the following:
- X/Twitter account
- GitHub account
- GitHub repo - people_finder
- Wordpress blog

Lets take a closer look at everything and see what else we can find!

### X/Twitter account
![Twitter account](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/twitter.png?raw=true)

### GitHub account
![GitHub account](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/github-profile.png)

### GitHub repo
![GitHub repo](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/github-repo.png)

### Wordpress blog
![Wordpress blog](https://github.com/kieferhax/tryhackme-projects/blob/main/OhSINT/assets/wordpress.png)

Wow! We've discovered a lot of open source information out there in the wild wild west of the world wide web.

Let's see if we can answer some of these questions now!

## Question 1 - What is this user's avatar?
Looking back at the Twitter account we see an avatar of a cat.

**Answer - Cat**

## Question 2 - What city is this person in?
Looking at the Twitter account again, we see the location is set to 'Space' however this does not work. 

Lets take a look at the hint.  The hint mentions "BSSID + Wigle.net"

Taking a closer look at Owoodflint's Twitter posts reveals some interesting information, specifically a BSSID `B4:5D:50:AA:86:41`

Let surf on over to Wigle.net and see what we can find with this BSSID.

The address returned for the BSSID search is `15 Charles II Street, London, GB, SW1Y4QU`

**Answer - London**



## Question 3 - What is the SSID of the WAP he connected to?
Unileverwifi

## Question 4 - What is his personal email address?
owoodflint@gmail.com

## Question 5 - What site did you find his email address?
Github

## Question 6 - Where has he gone on holiday?
New York

## Question 7 - What is the person's password?
