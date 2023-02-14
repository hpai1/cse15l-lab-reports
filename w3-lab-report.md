# Week 3 Lab Report - Grep command

*Hrithik Pai - A17311788*

In this report, I will be exploring the grep command. The grep command is used to search for a string within files. As with any other command, grep has flags that can be used to alter the output. Here, I will be discussing 4 of these flags. 
Sources used: [Grep Documentation](https://man7.org/linux/man-pages/man1/grep.1.html) and `$ man grep` command


## -r Flag 

The -r flag is used to search recursively within a directory. This is useful if the file system has a complex heirarchy because grep can just search all the files within the given directory. The command follows `$ grep -r "word" directory` 

**Example 1**
```
[hpai@ieng6-203]:skill-demo1-data:384$ grep -r "world" written_2/non-fiction/OUP/Berk/

written_2/non-fiction/OUP/Berk/CH4.txt:Psychoanalyst Erik Erikson built on Freud’s 
vision, expanding his picture of make-believe. According to Erikson, children draw 
on fantasy play to ﬁnd out about themselves and their social world. 1 In all 
cultures, children act out family roles and highly visibleoccupations—police officer, 
doctor, and nurse in our society; rabbit hunter and potter among the Hopi Indians; 
and hut builder and spear maker among the Baka of West Africa. 2 As they do so, they 
enter a small social organization whose members must cooperate to achieve common 
goals. And through observing and emulating admired adult ﬁgures, preschoolers 
internalize social norms and gain a sense of their future, of what they can become 
and how they can contribute to society. 

written_2/non-fiction/OUP/Berk/CH4.txt:Piaget acknowledged the emotional function 
of play, and he agreed that through pretending, children become familiar with 
social-role possibilities. But he is best known for stressing the symbolic nature 
of make-believe. Pretending, Piaget pointed out, is a vital means of mentally 
representing the world that, along with gestures, language, and drawings, develops 
rapidly in early childhood. Through it, children practice and strengthen their 
capacity to represent their experiences.3 For example, when Sophie pretended to 
put the animals to bed and used a TinkerToy to stand for a lollipop, she represented 
in her mind what formerly she could experience only directly—by going to bed or 
sucking a lollipop. Practicing and solidifying modes of representation, Piaget 
emphasized, make it possible for the child to free thought from the here and now; 
create larger images of reality that take into account past, present, and future; 
and transform those images mentally in the service of logical thinking. 

written_2/non-fiction/OUP/Berk/CH4.txt:Around age 2, children begin to pretend with 
less realistic toys, such as a block for a telephone. And sometime during the third 
year, they can imagine objects and events with little or no support from the real 
world, as when they say to a play
...
```
> Truncated output when using -r flag on the Berk directory when searching for the word "world"

In the above command, grep searched recursively for the word "world" in the Berk directory. When it searched recursively, it went through all the files in the Berk directory and found all instances of "world" and printed the lines surrounding that word within each file.

**Example 2**
```
[hpai@ieng6-203]:skill-demo1-data:387$ grep -r "world" written_2/non-fiction
/OUP/Berk/ch7.txt
                                       
In this chapter, I take up dilemmas that today’s parents face in rearing young 
children. Throughout this book, we have touched on myriad forces that make 
contemporary parenting highly challenging. These include one-sided, contradictory 
messages in the parenting-advice literature; career pressures that impinge on parent 
involvement in children’s lives; abysmally weak American child-care services to 
assist employed parents in their child-rearing roles; cultural violence and 
excessive materialism permeating children’s worlds; schools with less than optimal 
conditions for children’s learning; and impediments to granting children with 
deﬁcits and disabilities social experiences that maximize their development. 

Parents are wise to limit children’s access to TV to about one to one-and-a-half 
hours a day—no more than 10 hours a week. Following that guideline would cut the 
exorbitant number of hours children spend watching TV by 50 to 75 percent. Parents 
also need to prohibit violent TV and orient children toward educational programs 
that inform them about their world and toward entertainment shows that teach 
positive values and social skills. In Chapter 2, I explained how readily children 
can pick up negative attitudes and behaviors from television. Fortunately, children 
can just as easily absorb worthwhile messages and information from TV, so parental 
guidance in this area can have great beneﬁts for development.

Chinese and Japanese parents spend a great deal of time helping their children 
with homework—far more than American parents do. Asian parents also communicate 
often with teachers about how to help their child learn at his or her best. Rather 
than being dependent, Chinese and Japanese students develop into well adjusted, 
excellent students51—at the top in academic achievement in the world. 
```
> Output when using -r flag on the ch7.txt file in the Berk directory

As we can see from above, the -r flag 
can also be used on a .txt file, meaning it will not throw an error if a directory is not provided. If we give a .txt file to the -r flag, the -r flag's
function gets omitted because there is nothing to search recursively for. 

## -l Flag 

The -l flag is used to list only the files names of the files which are found using grep. In the above output, it can be tedious trying to sort through the
files if you are trying to search for a particular file name, which is where -l is helpful. It omits all the text that is printed, and only prints the file
names.

**Example 1**
```
[hpai@ieng6-203]:skill-demo1-data:390$ grep -r -l "world" written_2/non-fiction/
OUP/Berk/

written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch7.txt
```
> Output when adding -l flag to the Berk directory

As seen in the above output, when I used the -l command, the terminal only printed out the names of the files that contained the given word, as opposed to printing out the file names and the contents of the file. 

**Example 2**
``` 
[hpai@ieng6-203]:OUP:407$ grep -l "econosphere" Kauffman/ch9.txt Kauffman/ch6.txt

Kauffman/ch9.txt
``` 
> Terminal output when only using -l flag and passing in two text files

In the above example, I searching for the word "econosphere" in the ch9.txt and the ch6.txt files. I tell grep to print out only the name of the file that contains that word using the -l flag. The output printed ch9.txt, meaning that the word exists in that text file, not in the ch6.txt file. 

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


