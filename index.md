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

    ![Image](/imgs/ssh_logged_in.png)

## Task 3: Running Commands From Your IENG6 Account

While it's cool to be able to connect to a computer remotely, what purpose does it serve? One reason we've connected to ieng6 is to run commands. Within our account's directories, we can copy, rename, delete, list, or transfer files! Let's try some of these commands. 

1. We first want to see what folders exist in our starting directory. 
Type the command: `ls -a`. _What was the result?_
(See my result below, does your result look similar?)

    ![Image](/imgs/ls-a_result.png)

2. Now try this command: `mkdir NewDir` and then `ls -a`. 
_How does the new output compared to that from the previous step?_ (See my result below.)

    ![Image](/imgs/ls-a_of_NewDir.png)

3. As you can see, we are able to manipulate the files and directories on the server. Try `cd NewDir` and `ls -a`

4. Since we created an empty directory that we don't need on our server account, we should remove it. To return to the parent directory (one which contains current directory), try `cd ..`. Now trying `ls -c` should show us NewDir again. To remove it, try `rmdir NewDir'.

5. _But what if we wanted to delete a file, or a directory with a file in it?_ Great question, let's try it! Create a new directory using `mkdir NewerDir` then enter that directory using `cd NewerDir`. Here, we want to create a file using `touch testFile.txt` and then verify it exists using `ls`. Now that NewerDir is not empty, return to the parent directory `cd ..` then try to remove the directory as before `rmdir NewerDir`. _What happened?_

6. _Since that didn't work as expected, how can we delete directories with files inside?_ We can do so using a different command `rm -r -f NewerDir`. _What was the result?_ If we check the contents of the current directory `ls -c`, we can see that NewerDir is gone! _How did we do this?_ Using the `rm` command alone wouldn't work, so we added the options `-r` and `-f` to recursively and forcefully delete contents of the specified directory. 

    Nice job! You now have tried some of the most essential UNIX commands on a remote server!

## Task 4: Copying Files To/From The Remote Server Using SCP
The previous task shows us how to create and move files around on the remote server, which is great. But what can we do to copy files to the server or transfer files from the server? To do so, we'll be using SCP (Secure Copy) as our method to get a file from our client system to the server. Let's do it!

1. Create the file "fileToSend.txt" on your client system. Type some text here so we can confirm that all data is sent correctly. You can write whatever here. 

2. Now navigate to the location of "fileToSend.txt" in terminal using `cd`. Once in the directory of our new file, try `scp fileToSend.txt (YOUR-STUDENT-ACCOUNT-HERE)@ieng6.ucsd.edu:~/`

3. Once asked, enter your account's password. After the password is accepted, you should see the file's transfer status being updated on the left of your terminal (see image below). The speed will depend on the size of your file. 

    ![Image](/imgs/after_scp_status.png)

4. Looks good! To make sure everything is sent as we hoped, ssh back into your ieng6 account. Once here, run `ls` and you should see "fileToSend.txt". If so, try `cat fileToSend.txt`. The terminal should display the contents of the file (which you typed when the file was created). 

    Great work! Since the contents of the files on both the client and remoe computers match, we know we've successfully sent the file!

## Task 5: Setting Up Passwordless Login Using SSH Keys
By now, we've done plenty of useful tasks by making use of a remote connection to a server. As you've probably noticed, having to type in the password _every_ time gets old quickly. Although we don't have a "remember me" button to make this more convenient, we can mimick this behavior using SSH Keys. These keys will allow the server to recognize our client computer and automatically log us in. Sounds good? Let's get started!

1. From the client, try the command `ssh-keygen`. Then once the saved path is shown, press __enter__ to save keys to the default path. Then, when asked for a passphrase, press __enter__ to proceed without a passphrase and confirm this choice. You should see the key's fingerprints. 

    ![Image](/imgs/ssh-keygen-fingerprint.png)

2. Great! We can now copy the keys from our client machine to the server to enable passwordless login. SSH back into your ieng6 account. After providing your password (for the second to last time), try `mkdir .ssh`. After logging out of the server using `exit`, copy the files from the client to server using `scp /Users/(YOUR-USER-NAME)/.ssh/id_rsa.pub (YOUR-STUDENT-ACCOUNT-HERE)@ieng6.ucsd.edu:~/authorized_keys`(or replace path if other path was used during ssh-keygen). After entering your password (for the last time), try to ssh back into the server. _What happens?_

    Yay! You can now access your ieng6 remote account without needing to type in your password!

3. Log out of the remote server.

## Task 6: Optimizing Remote Acitivities
Isn't it great to ssh or scp without a password? Similarly, we can optimize other aspects of our remote access experience to make the process even quicker and more convenient. Let's check it out!

1. Create a java file on the client system. You can write whatever you wish here, but be sure it compiles and presents an output. (See my example below).

    ![image](/imgs/postcard-code.png)

2. Now, we would normally scp the file to ineg6, then use 2 separate ssh commands to compile then run our code. However, we can combine these steps into one by using semicolons ";" to separate each command. For my example, I would run: `scp postcard.java cs15lsp22abd@ieng6.ucsd.edu:~/; ssh cs15lsp22abd@ieng6.ucsd.edu javac postcard.java; ssh cs15lsp22abd@ieng6.ucsd.edu java postcard`

    ![Image](/imgs/postcard-result.png)

3. Now the command has been run... all at once! As you can see, this combined with our use of ssh keys saves us plenty of time. 

## Conclusion

Nice job! By this point, you have been able to set up your VSCode environment, connect to your ieng6 server account to run commands and copy files, generate and make use of ssh keys for passwordless login, and other ways to make accessing the server more convenient. I hope you enjoyed learning more about software tools and techniques!