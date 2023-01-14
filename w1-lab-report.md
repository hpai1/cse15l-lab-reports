# Week 1 Lab Report 
*Hrithik Pai*


## Installing VS Code
VScode is a type of text editor that allows you to write and modify code which has a built-in terminal to execute commands.
1. To Install VScode, go to [this link](https://code.visualstudio.com/download) and download the version for your system
2. Launch the VScode application and ensure it has downloaded properly (should look similar to picture below)

![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%204.40.58%20PM.png)
> VS code home screen

## Finding your account details
Each student in this class has their own account to manage and edit files. 
To connect via SSH, you need to first connect to the server that is respective to your account. 
Follow the steps below to find and set-up your account. 
1. Click on [this link](https://sdacs.ucsd.edu/~icc/index.php) which takes you to the below website. 
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%204.45.33%20PM.png)
> UCSD Technology Account Lookup Homepage
2. Enter your UCSD username and student ID in the respective fields.
3. Locate your CSE 15l account username which starts with the letters "cs15l" as shown circled in the red circle below
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%204.47.56%20PM.png)
> UCSD Technology Site to find lab account details (Account name circled in red)
4. If this is your first time accessing this account, follow the below steps to set-up your password
5. Follow [this link](https://sdacs.ucsd.edu/~icc/password.php) and enter the required information. Note: your username is your CSE 15l account
6. By doing so, you should end up on the below site
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%204.54.38%20PM.png)
> Page to set-up password CSE15l account 

7. Enter your current password (UCSD password) and a new password for this account
8. Note that after doing this, it will take about 15 minutes for your new password to go into effect


## Connecting to remote ssh
SSH is a protocol that allows you to connect to a computer or server remotely. 
In this case, we are trying to connect to our ieng6 CSE15L account. 

1. Click on the two icons in the bottom bar on the bottom left of the screen. 
2. Open a terminal on VS Code by navigating to the terminal tab
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%205.35.28%20PM.png)
> VS Code window that shows open terminal and highlights bottom left icons
3. To connect to your account, enter the command `$ ssh cs15lwi23zzz@ieng6.ucsd.edu` without the "$" symbol 
4. Replace the 'zzz' in the above command with the letters in your account
5. If done correctly, the below prompt should appear
  ```
  The authenticity of host 'ieng6.ucsd.edu (128.54.70.238)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])?
  ```
6. Enter yes to confirm your connection
7. Next, enter your password. Note: it will not appear as you're typing for security reasons
8. If done right, the below should appear on the command line. 
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%205.14.12%20PM.png)
> VS Code terminal prompt after log-in is successful

## Entering Commands
Now, you are remotely connected to a back-end system from your local machine. 
To work on this system, you have to use the terminal and the various commands it supports
1. To show all the files on this system, use the command `$ ls`
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%205.14.12%20PM.png)
> Terminal output from the `$ ls` command that shows contents of working directory
2. We can see that there is one file and one directory. 
3. To view all files and directories, use `$ ls -a`, which shows hidden items
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%205.14.12%20PM.png)
> Terminal output from the `$ ls -a` command that shows all the contents of working directory
4. To see the contents of the "perl5" file, use the command `$ cd perl5` followed by `$ ls`
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%205.14.12%20PM.png)
> Contents of the "perl5" folder (nothing appeared, so it is empty)
5. Navigate to the public class folder "/home/linux/ieng6/cs15lwi23/public" using the command `$ cd /home/linux/ieng6/cs15lwi23/public`
6. After using `ls` here, we see a couple of items, including a "hello.txt" file. To see its contents, type `$ cat hello.txt`
![Image](https://github.com/hpai1/cse15l-lab-reports/blob/main/Screen%20Shot%202023-01-13%20at%205.14.12%20PM.png)
> Terminal output showing the contents of the public class folder and the content of the "hello.txt" file
