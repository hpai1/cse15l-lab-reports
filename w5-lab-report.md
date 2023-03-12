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

The lab says that any class that ends in *Examples* has errors and it is our job to find them using the tester class provided any by writing additional tester methods. 

When we originally run the tester file, we see that all the tests pass. 

<img width="783" alt="Screen Shot 2023-03-12 at 10 44 00 AM" src="https://user-images.githubusercontent.com/69052552/224562578-6f7a9697-7c46-4730-88ae-1b35f77d80d9.png">

> Screenshot showing that all the tests in ArrayTests.java passed

The lab writeup says that we have to write additional tests to show the bugs in the other classes. In week 3, I used GitHub desktop to clone, edit, and run the java files. 

## What I would've Done Differently
In the lab, we had to clone a repository, edit files, run java tests, and commit the changes we made.

During week 3, I relied heavily on GitHub desktop to clone repositories and open them in VS Code. 

Now, I have the tools to do this all from the command line. I would use the command `$ git clone https://github.com/ucsd-cse15l-w23/lab3` to clone the repository. 

To edit the files, I would use the `nano` command. 
For example, we had to edit the tester class to add more tests. Instead of doing this in VS Code, I can use the command `$ nano ArrayTests.java`, which would open the below screen. 

<img width="636" alt="Screen Shot 2023-03-12 at 11 11 49 AM" src="https://user-images.githubusercontent.com/69052552/224563998-d18e4e90-a368-4c87-867a-5333ecefe648.png">

> Screenshot showing output of above command

I can then use the arrow keys and type a new test, like below. 
<img width="436" alt="Screen Shot 2023-03-12 at 11 14 10 AM" src="https://user-images.githubusercontent.com/69052552/224564105-14aae8a4-c12f-4a2a-bf08-ccfb5afe0f22.png">

After typing the above test, I can hit `Ctrl + O` to save the file then `Ctlr + X` to exit the editor.
Now, if we run the tester class again, we can see that the test failed, as expected. 

<img width="769" alt="Screen Shot 2023-03-12 at 11 17 03 AM" src="https://user-images.githubusercontent.com/69052552/224564254-0bd62169-5bf6-4014-a90d-1688b2085751.png">

 
In a similar fashion, I can edit the tester file to write more tests and edit the java files to fix the errors. 

To expand on my knowledge, I can also use the `jbd` command to walk through the code to see the errors. 
The `$ jbd` command is used to open a Java debugger tool to see the code execute in real time. You can view values of variables and see what is happening to the variables after each step. 
I can use this to debug my code and find errors as an alternative to writing Junit tests.

To commit my changes, I used GitHub Desktop in Week 3, which commits all your changes in the click of a button. Now, I have a lot more github commands in my toolbox. Instead of using GitHub Desktop, I can run the commands `$ git add .` and `$ git push` to push my changes. The `$ git add .` command adds all the changes I made to a local repository. The `git push` command pushes all the changes to the remote repository. 
