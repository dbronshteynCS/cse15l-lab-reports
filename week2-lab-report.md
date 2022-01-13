# Week 2 Lab Report 
**Daniel Bronshteyn**
**PID: A16882179**


# *This is a tutorial on how to log into the ieng6*


## Installing VSCode

To install Visual Studio Code I went to the website [https://code.visualstudio.com/](https://code.visualstudio.com/). Once I was at the Visual Studio Code website I clicked the "Download Mac Universal Stable Build" button because I use macOS. After following the installation prompts, I was able to open the Visual Studio Code application. 

*Visual Studio Code Open Page*
![Visual Studio Code Open](Visual%20Studio%20Code%20Open.png)


## Remotely Connecting

To remotely connect to my course-specific account on ieng6, I first went to the website [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php) where I logged in using my credentials, went to my course-specific account on ieng6 (cse15lwi22ace), and reset my password to activate the account. Then I went to Visual Studio Code, opened the terminal, and typed in "ssh cse15lwi22ace@ieng6.ucsd.edu". After clicking the *return* key on my computer, I was prompted with "authenticy of host" message, to which I entered "yes", and when prompted for a password, I copied in the password that I created when activating my course-specific account through the password reset. 

![Remotely Connecting](Remotely%20Connecting.png)

>Terminal does not show the "authenticity of host" message in this screenshot because that message only happens the first time when SSHing into course-specific account from a computer 

## Trying Some Commands

Once I had logged into the ieng6 server, I tried out different commands in the Visual Studio Code terminal. Some of the commands I tried were  `pwd` (print working directory), `ls` (list files), `cd perl5` (change directory), `ls /home/linux/ieng6/cs15lwi22/cs15lwi22ace` (list files in directory), and `ls -a` (list all files). 

*Trying Some Commands in the Terminal*
![Trying Some Commands](Trying%20Some%20Commands.png)

## Moving files with `scp`

First I created a new file in Visual Studio Code called "WhereAmI.java" in the file "CSE15L" and pasted the code that was provided in the *Week 1 Lab* and compiled it by the command `javac WhereAmI.java` and ran it by `java WhereAmI` on my own computer. Seeing that it ran, I moved it to the ieng6 server using the command `scp WhereAmI.java cs15lwi22ace@ieng6.ucsd.edu:~/` and entered in my password for the account. Then I SSHed into the ieng6 server and ran the file on the server using `javac` and `java` commands. 

![Moving files with scp](Moving%20files%20with%20scp.png)

*Code for `WhereAmI.java`*
```
class WhereAmI {
    public static void main(String[] args) {
      System.out.println(System.getProperty("os.name"));
      System.out.println(System.getProperty("user.name"));
      System.out.println(System.getProperty("user.home"));
      System.out.println(System.getProperty("user.dir"));
    }
  }
```

## Setting an SSH Key

To create an ssh key, I first typed "ssh-keygen" into the Visual Studio Code terminal; this generated a public and private key. Then I entered the file in which I would save these keys, `/Users/danielbronshteyn/.ssh/id_rsa`, and when prompted for a passphrase, I left it empty by clicking *return* twice. Then after being shown that the SSH key was saved, I made a copy of the **public** key to the `.ssh` directory of my account on the ieng6 server through the following commands: 
```
$ ssh cs15lwi22ace@ieng6.ucsd.edu
$ (entered password)
$ mkdir .ssh
$ (logout)
$ scp /Users/danielbronshteyn/.ssh/id_rsa.pub cs15lwi22ace@ieng6.ucsd.edu:~/.ssh/authorized_keys
$ (entered password)
```
and then was able to log in with ssh without entering a password. 

**Setting an SSH Key**
![SSH Keys Override Pass](SSH%20Keys%20Override%20Pass.png)
>I originally set a passphrase for the ssh key when it should have been empty. That is why the override option appears in the screenshot for setting up an ssh key. The original screenshot with a passphrase is below. 

![SSH Keys](SSH%20Keys.png)

## Optimizing Remote Running

The edit I made to WhereAmI.java was adding a line that printed "HELLO WORLD!". After working through various different optimizations of making a local edit on "WhereAmI.java", copying it to the ieng6 server, and running it from the server, I created this command: `scp WhereAmI.java cs15lwi22ace@ieng6.ucsd.edu:~/; ssh cs15lwi22ace@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"`. The whole process is on one line where I first make a `scp` (copy to the server), and ssh in to the server where I compile and run WhereAmI.java. 

![Optimizing Remote Running](Optimizing%20Remote%20Running.png)

