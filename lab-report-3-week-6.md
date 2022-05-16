[Return to Homepage](https://Conrado-M-UCSD.github.io/CSE15L-Lab-Reports/index.html)
# Lab Report 3: Increasingly Efficient!

So far, our lab activities have leveraged our skills in many common workflow scenarios, like connecting to a remote server and making use of GitHub for verion control and continuous integration. For many tasks that one would complete using these skills, there are ways we can spend less time on the "in-betweens" of software devolpment and focus on the main task at hand. In this Lab Report, I'll explore some of the ways this can be done. Specifically, I'll be *Streamlining My SSH Configuration*, *Setting up GitHub Access from ieng6*, and *copying whole directories using `scp -r`*. So let's get started!


## Task 1: Streamlining SSH Configuration

Logging into our specific ieng6 account can be tedious and can take up a large chunk of time (especially when I forget my account name or type it incorrectly :D. In order to speed up this process, I streamlined my ssh connection by configuring. Here are the photos 

**Contents of my SSH config file:**

![image](imgs/lr3/task%201/contents-of-config.png)

**Logging into server for ssh with alias:**

![image](imgs/lr3/task%201/ssh.success.png)

**Connecting to server for scp using alias:**

![image](imgs/lr3/task%201/scp.success.png)

With these changes, we can now access our remote server account in much less time compared to before. 

## Task 2: Setting Up GitHub Access From ineg6 Account 

It may also be helpful to enable access to our GitHub account from ieng6, so I'll now demonstrate how I was able to do this. 

First, I followed [this tutorial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to generate a freesh pair of ssh keys on my remote ieng6 account. After this was done, I added these new keys to my ssh agent. Then, I was able to edit a file from the repo and add, commit, then push the newly edited file. The small changes to README.md can be seen in [this commit](https://github.com/Conrado-M-UCSD/CSE15L-Lab-Reports/commit/126b887bb2ffc68c67dad5b2d20be4becf7623d3). 

Image showing my ssh public and private keys stored on my remote ieng6 account: 

![image](imgs/lr3/task%202/ssh_key_on_ieng6.png)

Image showing my public key added to GitHub: 

![image](imgs/lr3/task%202/ssh_key_on_github.png)

Image of a successful sequence of git add, git commit, and git push: 

![image](imgs/lr3/task%202/git_commit_and_push_from_ieng6.png)

Image of resulting commit reflected on the repo: 

![image](imgs/lr3/task%202/commit_from_ieng6_diff.png)

And now we've done it! Now we can perform clones, commits, and pushes from the remote ieng6 account!


## Task 3: Copying Whole Directories

We can also speed up our tasks by copying whole directories using `scp -r` which will recursively copy the contents of the specified directory. This method is greatly prefered over having to scp each individual file (especially when working with many files and directories). 

**Copying markdown-parse directory with scp -r:**

![image](imgs/lr3/task%203/scp-r-success.png)

**Running tests with copied markdown-parse files:**

![image](imgs/lr3/task%203/run_tests.png)

**Running all commands in one line:** 

![image](imgs/lr3/task%203/all_in_one.png)
