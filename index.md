# CSE 15 Lab Report Week 2
## By Conrado Martinez

In this document, you will learn how to install and make use of VSCode, connect to and run commands from IENG6, transfer files using scp, and generate SSH keys for passwordless login. 

**Let's get started!** 

--- 
## Task 1: Getting Started With VSCode

Visual Studio Code is an application that allows us to write code, see previews of markdown text, and run commands from our terminal. 
Now, we will cover the app's installation process. 
1. Visit the VSCode [download page](https://code.visualstudio.com/Download) and download the app which corresponds to your operating system version (in my case, I'll download the Windows 64-bit installer).

![Image](/imgs/vscode-download.png)

2. Once installer has downloaded, run the setup application to install VSCode on your system. 

3. ...and you've now installed VSCode on your computer!


---

## Task 2: Establish A Remote Connection to `IENG6` Servers

IENG6 are the servers provided by UCSD for students to access remotely. In order to connect to the server, we must run commands on our client system which grant us a Secure Shell (SSH) into the servers. Once enrolled in an applicable course, students are given an account to access the server from. The general format for these usernames is: csxxyyzz where x is the course number (i.e. 15L for CSE15L), y is the quarter taken (i.e. sp22 for a course taken in Spring 2022) and z will be the unique account letters (i.e. ab, .., yz, etc). An example student account might be `cs15lsp22EZ'. 

1. Visit the UCSD ETS password changing tool website to set a password for you ieng6 account (note: this must be done before logging into your student account and can take some time to set the new password, so it's recommended to do this before the lab sction). 

2. After entering this new password and waiting some time, open VSCode and take note of the `terminal` section. 

3. Here, we'l be running this command: 

    `ssh cs(YOURLOGINHERE)@ieng6.ucsd.edu`

4. After doing so, you should be prompted to enter your password. Enter your newly set password here (password will not appear when being typed, this is OKAY and a normal security feature). 

5. Congrats, you're now connected to your student account on ieng6! We can now continue with the rest of the lab.


## Task 3: Running Commands From Your `IENG6` Account

While it's cool to be able to connect to a computer remotely, what purpose does it serve? One reason we've connected to ieng6 is to run commands. Within our account's directories, we can copy, rename, delete, list, or transfer files! Let's try some of these commands. 

1. We first want to see what folders exist in our starting directory. 
Type the command: `ls -c`. What was the result? 


## Task 4: Copying Files To/From The Remote Server Using `SCP`


## Task 5: Setting Up Passwordless Login Using `SSH Keys`


## Task 6: Optimize Remote Acitivities

