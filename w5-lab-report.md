# Week 5 Lab Report - Revisiting Week 3 Lab

*Hrithik Pai - A17311788*

In this report, I will revisit one of my favorite labs, the one from Week 3. 
I will go through the lab and explain what I did and how I would have done it differently with tools I learned later in the course.


## Original Lab 3

In this lab, we had to fork a repository that had several java files. Some of the java files were implementations and methods of data structures, like lists and arrays, while others contained tester methods for those implementations and methods. The files included
- `ArrayExamples.java`
- `ArrayTests.java`
- `ListExamples.java`
- `LinkedListExample.java`
- `FileExample.java`



## Step 2 - Cloning the fork of the repository

In this step, we will be cloning the forked repository. In the set-up phase, we forked [this](https://github.com/ucsd-cse15l-w23/lab7) repository. Forking a repository means to create a copy of it on your account. The typical naming convention of the repository would be *github.com/hpai1/lab7*, except the *hpai1* path would be replaced with your github username. 

In that github repo, find the ssh key url for cloning. As seen in the below picture, you should be able to find it under the *code* tab. 

<img width="392" alt="Screen Shot 2023-02-25 at 11 45 21 AM" src="https://user-images.githubusercontent.com/69052552/221376618-88e96719-2720-472f-ac67-51e6a1d46b31.png">

> Screenshot showing where to find the ssh url to clone.

Copy that ssh url and in the terminal, type `$ git clone <Command + v> <enter>`

To ensure that the lab7 repo was cloned, type `$ ls <enter>` and you should see a lab7 directory in your remote account.

<img width="523" alt="Screen Shot 2023-02-25 at 11 48 12 AM" src="https://user-images.githubusercontent.com/69052552/221376721-3d5d4bc6-af90-4b37-8961-c0031114c71f.png">

 > Screenshot showing the commands to clone the repository using the ssh url and making sure that it got cloned.

## Step 3 - Running the Java tests, showing that they failed

In this step, we need to run java junit tests on a certain file to show that they failed. 

To do this, we need to use a series of commands. 
Firstly, we need to navigate into the lab7 directory using the command `$ cd l<tab> <enter>` 
The *tab* key autofills the rest of the command, which is why you may have noticed the *l* became *lab7/* after hitting the key. 

To find what files are in this repo, use the *ls* command: `$ ls <enter>`. We could also type `<up><up>` to retrieve the *ls* command stored in history then type `<enter>` to execute the *ls* command.

We see that there are two files of interest, *ListExamples.java* and *ListExamplesTests.java*. 
We need to run the tests on the *ListExamplesTests.java* file because as the name suggests, that is the file that contains the junit tests. 

Since this is our first time running the java tests, we would need to type out the entire command to compile and run the java tests. 
The command to compile is `$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java <enter>`. 
The command to run the test is `$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore L <tab> T <tab> <delete> <enter>` 

In the above command, the first `<tab>` button autofills to *ListExamples*. To get the *Test* part, you would need to type *T* then autofill the rest. The tab button completes it to *ListExamplesTab.* The period isn't needed at the end, so you would need to delete that before executing the command.

It should match the output below. 

<img width="967" alt="Screen Shot 2023-02-25 at 12 05 36 PM" src="https://user-images.githubusercontent.com/69052552/221377375-e7a4effa-888a-4105-8faf-7dc5a05833bb.png">

> Output showing that the tests ran successfully and one of them failed.

## Step 4 - Editing the code to fix the failing test

From the above output, we see that the test timed out, meaning that there is an infinite loop in the code somewhere. 

To edit the file, we can use the *nano* command. We would type in the following command: `$ nano L<tab>.n<tab> <enter>` to open the editor file within the command.

After reading through the file, the error is at the very end of the file, so use the `<down>` button to scroll to the last while loop. 
The error arises because *index1* is being changed instead of *index2*, so use the `<right>` arrow keys to position your cursor to the below position.

<img width="286" alt="Screen Shot 2023-02-25 at 12 48 00 PM" src="https://user-images.githubusercontent.com/69052552/221378980-42fe0db5-4f52-4185-85e0-8bb72c120374.png">

Then, type `<delete> 2`, which should change the code to *index2 += 1*. To save your changes, type `<Control + O> <Enter>`. To exit, type `<Control + X>`. 
You should be back to the regular terminal window. 

## Step 5 - Run the tests again to prove they pass

To run the tests again, you can use your terminal's history instead of rewriting the entire command. 

To do this, we first need to recompile the files, so type `<up><up><up><enter>`. The three up arrows should bring up the command used to compile the files, then hit enter to run the command. 

To run the tests, we will follow a similar procedure, so type `<up><up><up><enter>` to bring up the right command and execute it. 

If all the steps were done properly and the file was properly saved, we should see the below screen. 

<img width="972" alt="Screen Shot 2023-02-25 at 12 53 11 PM" src="https://user-images.githubusercontent.com/69052552/221379153-865d6536-5326-4f92-b756-648c5a8fc053.png">

> Terminal output showing all the tests passed.

## Step 6 - Commit and Push the changes to github

To commit and push the changes to github, we first need to add all our changes to be pushed. 

To do this, we can use the command `$ git add .`, which adds all the files that were changed. 
Then, we need to commit our changes with a message, so type `$ git commit -m "Fixed the code"`. Feel free to replace the message with anything you like. 
In the above command, the -m flag means that we are adding a message. 

Then finally, push the changes by using the command `$ git push`. 

If all the steps above and the inital ssh setup were done right, the below output should appear on the terminal.

<img width="573" alt="Screen Shot 2023-02-25 at 12 56 37 PM" src="https://user-images.githubusercontent.com/69052552/221379247-3ff85335-f2a2-43e0-95f0-2fac7bddf101.png">

> Terminal output showing successful adding, committing, and pushing of changes to the remote repository.

