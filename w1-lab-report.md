# Week 1 Lab Report 
*Hrithik Pai*


## Installing VS Code
VScode is a type of text editor that allows you to write and modify code which has a built-in terminal to execute commands.
1. To Install VScode, go to [this link](https://code.visualstudio.com/download) and download the version for your system
2. Launch the VScode application and ensure it has downloaded properly (should look similar to picture below)

<img width="1470" alt="Screen Shot 2023-01-13 at 4 40 58 PM" src="https://user-images.githubusercontent.com/69052552/212456966-4c90fab3-ec3c-48e2-8c72-be0db8b93604.png">
> VS code home screen 


## Finding your account details
Each student in this class has their own account to manage and edit files. 
To connect via SSH, you need to first connect to the server that is respective to your account. 
Follow the steps below to find and set-up your account. 
1. Click on [this link](https://sdacs.ucsd.edu/~icc/index.php) which takes you to the below website. 

<img width="1470" alt="Screen Shot 2023-01-13 at 4 45 33 PM" src="https://user-images.githubusercontent.com/69052552/212456983-59965fbe-67ea-44aa-934b-7ebb16f04721.png">
> UCSD Technology Account Lookup Homepage

2. Enter your UCSD username and student ID in the respective fields.
3. Locate your CSE 15l account username which starts with the letters "cs15l" as shown in the red circle

<img width="1470" alt="Screen Shot 2023-01-13 at 4 47 56 PM" src="https://user-images.githubusercontent.com/69052552/212456992-00c9fbc7-2d2f-46a5-907f-ec90150474e0.png">
> UCSD Technology Site to find lab account details (Account name circled in red)

4. If this is your first time accessing this account, follow the below steps to set-up your password
5. Follow [this link](https://sdacs.ucsd.edu/~icc/password.php) and enter the required information. Note: your username is your CSE 15l account
6. After doing so, you should end up on the below site

<img width="1470" alt="Screen Shot 2023-01-13 at 4 54 38 PM" src="https://user-images.githubusercontent.com/69052552/212457001-58864014-ad95-4f88-bd71-b0be6ff173ab.png">
> Page to set-up password CSE15l account 

7. Enter your current password (UCSD password) and a new password for this account
8. Note that after doing this, it will take about 15 minutes for your new password to go into effect


## Connecting to remote ssh
SSH is a protocol that allows you to connect to a computer or server remotely. 
In this case, we are trying to connect to our ieng6 CSE15L account. 

1. Click on the two icons in the bottom bar on the bottom left of the screen. 
2. Open a terminal on VS Code by navigating to the terminal tab

<img width="1470" alt="Screen Shot 2023-01-13 at 5 35 28 PM" src="https://user-images.githubusercontent.com/69052552/212457014-663c3294-45b4-4a8f-ab0a-a9235335ddcf.png">
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
6. Enter `yes` to confirm your connection
7. Next, enter your password. Note: it will not appear as you're typing for security reasons
8. If done right, the below should appear on the command line.

<img width="499" alt="Screen Shot 2023-01-13 at 5 14 12 PM" src="https://user-images.githubusercontent.com/69052552/212457005-bff099eb-25ce-440c-a302-6c7f2077ebe5.png">
> VS Code terminal prompt after log-in is successful

## Entering Commands
Now, you are remotely connected to a back-end system from your local machine. 
To work on this system, you have to use the terminal and the various commands it supports
1. To show all the files on this system, use the command `$ ls`

<img width="311" alt="Screen Shot 2023-01-13 at 5 14 56 PM" src="https://user-images.githubusercontent.com/69052552/212457033-7a2c4f64-292e-4467-b8de-29dbfacb7fc3.png">
> Terminal output from the `$ ls` command that shows contents of working directory

2. We can see that there is one file and one directory. 
3. To view all files and directories, use `$ ls -a`, which shows hidden items

<img width="828" alt="Screen Shot 2023-01-13 at 5 15 51 PM" src="https://user-images.githubusercontent.com/69052552/212457037-874a23f4-d85b-4b5f-b8a7-1d98e3f0cc8a.png">
> Terminal output from the `$ ls -a` command that shows all the contents of working directory

4. To see the contents of the "perl5" file, use the command `$ cd perl5` followed by `$ ls`

<img width="341" alt="Screen Shot 2023-01-13 at 5 17 58 PM" src="https://user-images.githubusercontent.com/69052552/212457038-c04881c2-41cc-497d-a275-36d7c8b200fd.png">
> Contents of the "perl5" folder (nothing appeared, so it is empty)

5. Navigate to the public class folder "/home/linux/ieng6/cs15lwi23/public" using the command `$ cd /home/linux/ieng6/cs15lwi23/public`
6. After using `ls` here, we see a couple of items, including a "hello.txt" file. To see its contents, type `$ cat hello.txt`

<img width="616" alt="Screen Shot 2023-01-13 at 6 04 45 PM" src="https://user-images.githubusercontent.com/69052552/212457054-f79d57e2-0d46-4c55-816f-be5a45315312.png">
> Terminal output showing the contents of the public class folder and the content of the "hello.txt" file
