# Week 4 Lab Report - Git Commands + Nano

*Hrithik Pai - A17311788*

In this report, I will be using git commands through the command line to add, commit, and push changes to certain files. 
I will also be editing files through the terminal using the nano command. 
For this lab report, I will be performing these commands on a new terminal window, meaning that history from before is not saved.


## Step 1 - Log in to ieng6

To log in to ieng6, use the ssh command, which is used to connect to a remote machine through the command line. 
One can use the `<up>` button to retrieve the previous command, but since my terminal window is new, there is no history saved.

To log in, use the command `$ ssh cs15lwi23afr@ieng6.ucsd.edu <enter>`. 
Be sure to replace the *afr* with your own letters. 
If all the set-up was done properly, the terminal shouldn't require a password and should display the screen below. 

<img width="485" alt="Screen Shot 2023-02-25 at 11 36 07 AM" src="https://user-images.githubusercontent.com/69052552/221376250-692a37e7-b521-45fd-aa34-7e6898d1696f.png">

> Terminal window showing successful log-in to ieng6. Note that there was no password required at log in, which was done in the setup phase.


## Step 2 - Cloning the fork of the repository

In this step, we will be cloning the forked repository. In the set-up phase, we forked [this](https://github.com/ucsd-cse15l-w23/lab7) repository. Forking a repository means to create a copy of it on your account. The typical naming convention of the repository would be *github.com/hpai1/lab7*, except the *hpai1* path would be replaced with your github username. 

In that github repo, find the ssh key url for cloning. As seen in the below picture, you should be able to find it under the *code* tab. 

<img width="392" alt="Screen Shot 2023-02-25 at 11 45 21 AM" src="https://user-images.githubusercontent.com/69052552/221376618-88e96719-2720-472f-ac67-51e6a1d46b31.png">

> Screenshot showing where to find the ssh url to clone.

Copy that ssh url and in the terminal, type `$ git clone <Command + v> <enter>`

To ensure that the lab7 repo was cloned, type `$ ls <enter>` and you should see a lab7 directory in your remote account.

<img width="523" alt="Screen Shot 2023-02-25 at 11 48 12 AM" src="https://user-images.githubusercontent.com/69052552/221376721-3d5d4bc6-af90-4b37-8961-c0031114c71f.png">

 > Screenshot showing the commands to clone the repository using the ssh url and making sure that it got cloned.

## -n Flag 

The -n flag prints out the line number where the specified string is found in the file. This can be combined with other flags to alter the terminal's output, as shown below. 

**Example 1**
```
[hpai@ieng6-203]:OUP:433$ grep -r -n "Neighboring" Kauffman

Kauffman/ch8.txt:185:If one thinks of the measure of how close the output of a 
binary string program is to the correct program as the “fitness” of that trial 
binary string, then the fitness can be thought of as a height. The distribution of 
heights over the dimensional Boolean hypercube therefore creates a fitness 
landscape. In fact, my conjecture amounts to stating that the resulting fitness 
landscape is completely random. Neighboring points have fitnesses that have no 
correlation.
```
> Terminal output when using -n flag

As we can see in the output, the -n flag only adds a slight, but important change in the terminal's output. The -n flag includes the line number in which the word is found. As we can see above, the word "Neighboring" is found on line 185 in the ch8.txt file.

**Example 2**
```
[hpai@ieng6-203]:OUP:434$ grep -r -n -l "Neighboring" Kauffman

Kauffman/ch8.txt
```
> Terminal output when using the -n and -l flags

In the above example, I ran the same -n command, but also included the -l flag, which only lists the names of the files in which the word is found. Since the -l flag only lists filenames, we can see that the -n flag had no effect on the output, despite coming first in the command. This leads me to believe that certain flags have priority over others because if the order of the -n and -l flags were switched, the same output is shown.

## -i Flag 

The -i flag when using grep is used when you want to ignore the case of the word you are searching for. 
When grep searches for the string in the file, it searches for the exact match. In other words, it also matches the case that you provide. When the -i
flag is used, the case of the word is ignored, so it searches for all instances of the sequence of characters. 

**Example 1**
``` 
[hpai@ieng6-203]:OUP:421$ grep -r -i "Robust" Kauffman

Kauffman/ch8.txt:•The number of state cycle attractors robustly scales as a square 
root function of the number of genes in the ordered regime. The number of cell 
types in real cells scales as roughly a square root to a linear function of the 
estimated number of genes in that organism, from yeast to sponge to worm to man. 
Indeed, the square root of , is about , and Bruce Alberts and colleagues quote the 
number of cell types in humans as .

Kauffman/ch9.txt:Robust Constructibility

Kauffman/ch9.txt:My first purpose in investing in an entire box of Legos was to 
explore and define concepts of “robust constructibility.” We have succeeded, but run 
into fascinating problems of a general phase transition in problem solvability. In turn, 
this very phase transition suggests that in a coconstructing biosphere or econosphere 
rather specific restrictions arise and are respected by critters and firms, creatures 
and cognoscenti.
...
```
> grep output when using -i on the Kauffman directory

In the above example, I was searching for the string "Robust" since I used the -i flag, grep searched for all instances of the sequence of characters and omitted any instances of lowercase and uppercase characters. We see this within the first two text files, where it shows "robust" and "Robust", 
proving that casing was disregarded. 

**Example 2**
``` 
[hpai@ieng6-203]:OUP:440$ grep -n -i -l "Neighboring" Kauffman/ch9.txt Kauffman/ch8.txt

Kauffman/ch9.txt
Kauffman/ch8.txt
```
> Output when combining the -i, -n, and -l flags

In the above example, I combined the -i, -n, and -l flags and specified two files two search for within the Kauffman directory. The -i flag tells grep to search for the word Neighboring, but exclude cases, meaning that it would identify "neighboring" as a valid word. The -n flag tells grep to print out the line numbers where each word is found, but the -l flag over-writes the -n flag and prints out only the file names. Since we see both the ch8.txt and ch9.txt files, we know that the specified sequence of characters exists in both files, but we do not know the cases of each letter.

