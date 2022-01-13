# Week 2 Lab Report 
**Daniel Bronshteyn**
**PID: A16882179**
---

# *This is a tutorial on how to log into the ieng6*


## Installing VSCode

To install Visual Studio Code I went to the website [https://code.visualstudio.com/](https://code.visualstudio.com/). Once I was at the Visual Studio Code website I clicked the "Download Mac Universal Stable Build" button because I use macOS. After following the installation prompts, I was able to open Visual Studio Code application. 

*Visual Studio Code Open*
![Visual Studio Code Open](Visual%20Studio%20Code%20Open.png)


## Remotely Connecting

To remotely connect to my course-specific account on ieng6, I first went to the website [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php) where I logged in using my credentials, went to my course-specific account on ieng6 (cse15lwi22ace), and reset my password to activate the account. Then I went to Visual Studio Code, opened the terminal, and typed in "ssh cse15lwi22ace@ieng6.ucsd.edu". After clicking the *return* key on my computer, I was prompted with "authenticy of host" message, to which I entered "yes", and lastly, when prompted for a password, I copied in the password that I created when activating my course-specific account through the password reset. 

![Remotely Connecting](Remotely%20Connecting.png)

**Terminal does not show the "authenticity of host" message in this screenshot because that message only happens the first time when sshing into course-specific account from a computer* 

## Trying Some Commands

Once I had logged into the ieng6 server, I tried out different commands in the Visual Studio Code terminal. Some of the commands I tried were  `pwd` (print working directory), `ls` (list files), `cd perl5` (change directory), `ls /home/linux/ieng6/cs15lwi22/cs15lwi22ace` (list files in directory), and `ls -a` (list all files). 

*Trying Some Commands in the Terminal*
![Trying Some Commands](Trying%20Some%20Commands.png)

## Moving files with `scp`

To move files to the ssh, I used the `scp` command. First I created a new file in Visual Studio Code called "WhereAmI.java" and pasted the code that was provided in the *Week 1 Lab* and compiled it by the command `javac WhereAmI.java` and ran it by `java WhereAmI`. Seeing that it ran, I moved it to 

## Setting an SSH Key


## Optimizing Remote Running



