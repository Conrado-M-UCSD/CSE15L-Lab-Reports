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

3. ...and you've now installed VSCode on your computer! After selecting theme settings, your app will be open to a screen similar to what's shown below. 

![Image](/imgs/vscode-main-page.png)

---

## Task 2: Establishing A Remote Connection to IENG6 Servers

IENG6 are the servers provided by UCSD for students to access remotely. In order to connect to the server, we must run commands on our client system which grant us a Secure Shell (SSH) into the servers. Once enrolled in an applicable course, students are given an account to access the server from. The general format for these usernames is: csxxyyzz where x is the course number (i.e. 15L for CSE15L), y is the quarter taken (i.e. sp22 for a course taken in Spring 2022) and z will be the unique account letters (i.e. ab, .., yz, etc). An example student account might be `cs15lsp22EZ'. 

1. Visit the [UCSD ETS Account Lookup](https://sdacs.ucsd.edu/~icc/index.php) website to find your ieng6 account. Once you have your cs15l account, head to the [UCSD Global Password Reset](https://sdacs.ucsd.edu/~icc/password.php) website to chane your password, which will now be set for your cs15l ieng6 account. (NOTE: Password changes can take some time, so don't be worried if the change is not immediately reflected)

2. Open VSCode select the "Terminal" then "New Terminal" tab from the menu along the top of the app window (or use the hotkey shortcut __Ctrl+Shift+\'__)

3. Here, we'l be running this command: 

    `ssh (YOUR-STUDENT-ACCOUNT-HERE)@ieng6.ucsd.edu`

4. After doing so, you should be prompted to enter your password. Enter your newly set password here (password will not appear when being typed, this is _okay_ and a _normal_ security feature. See image below).

    ![Image](/imgs/ssh_password.png)

5. Congrats, you're now connected to your student account on ieng6! We can now continue with the rest of the lab.


## Task 3: Running Commands From Your IENG6 Account

While it's cool to be able to connect to a computer remotely, what purpose does it serve? One reason we've connected to ieng6 is to run commands. Within our account's directories, we can copy, rename, delete, list, or transfer files! Let's try some of these commands. 

1. We first want to see what folders exist in our starting directory. 
Type the command: `ls -c`. What was the result? 


## Task 4: Copying Files To/From The Remote Server Using SCP


## Task 5: Setting Up Passwordless Login Using SSH Keys


## Task 6: Optimizing Remote Acitivities

