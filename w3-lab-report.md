# Week 3 Lab Report - Grep command

*Hrithik Pai - A17311788*

In this report, I will be exploring the grep command. The grep command is used to search for a string within files. As with any other command, grep has flags that can be used to alter the output. Here, I will be discussing 4 of these flags. 

Sources used: [Grep Documentation](https://man7.org/linux/man-pages/man1/grep.1.html) and `$ man grep` command


## -r Flag 

The -r flag is used to search recursively within a directory. By searching recursively, grep will search for all files within the given directory, even if they are within sub-directories in the working directory. On the contrary, the 'normal' grep command will only search for files one level lower than the working directory, instead of looking into other folders. This is useful if the file system has a complex hierarchy because grep can just search all the files within the given directory. The command follows `$ grep -r "word" directory` 

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
[hpai@ieng6-203]:~:450$ grep -r "world" skill-demo1-data/ 

skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt:Product proliferation 
and shorter product cycles, reflected in ever-changing styles and product 
differentiation, contribute to general demand uncertainty for both retailers and 
manufacturers, thereby making demand forecasting and production planning harder every 
day. In a world where manufacturers must supply an increasing number of products 
with fashion elements, speed and flexibility are crucial capabilities for firms 
wrestling with product proliferation, whether they are retailers trying to offer a 
wide range of choices to consumers or manufacturers responding to retail demands 
for shipments. skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt:In 
conventional terms, these three sectors are considered distinct industries, 
separated by traditional market relationships. For example, arm’s-length transactions 
between retail buyers and apparel sellers determine prices and quantities of goods to 
be delivered. Apparel companies periodically made deliveries based on these contracts 
and the transaction was then completed. In such a world, coordination problems between 
the parties were of little concern. 

skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt:But, as we have already 
emphasized, this is not the real world of apparel today. At its most fundamental level, 
the channel perspective reflects a revolution in retail practices. These practices have 
resulted in the integration of enterprises at all stages of the distribution and 
production chain, because of the infusion of real-time information on consumer sales. 
Instead of gearing planning and production decisions to forecasts and guesses made months 
in advance of a selling season, firms now receive periodic ongoing orders based on actual 
consumer expenditures. And companies in transformed retail-apparel-textile channels have 
established a complex web of computer hardware and software, other technologies, and 
managerial practices that have blurred the traditional boundaries between retailers and 
suppliers.

skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt:A Stitch in Time concludes 
with a look at the many factors shaping today’s retail-apparel textile channel—from the 
complex management challenges facing suppliers to labor standards and macroeconomic policy. 
Chapter 13 (“The Global Marketplace”) reviews trends in U.S. imports and exports of apparel 
and textiles, including information on trade by countries and specific products. It then 
connects these trends to changing trade policies, emphasizing the growing regionalization 
of trade flows in different parts of the world. Chapter 14 (“Suppliers in a Lean World”) 
examines our survey results from another angle, evaluating firm performance in an integrated 
channel. Here we highlight the importance of combining information technologies, manufacturing 
innovations, and new methods of management to respond to lean retailing demands.

...

```
> Output when using -r flag on the overall skill-demo1-data directory

As we can see from above, the -r flag was used to search a very large directory for the word *world*. From this example, we see how powerful the -r flag really is because we can search a very large and complex directory for a specific word and get its relative location in the file along with the file name. In the previous example, we used -r on a smaller sub-directory, but the real value of the flag is shown in the above example, where it is meant to be used in larger and more complex file systems, such as the skill-demo1-data directory.

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

As we can see in the output, the -n flag only adds a slight, but important change in the terminal's output. The -n flag includes the line number in which the word is found. As we can see above, the word "Neighboring" is found on line 185 in the ch8.txt file. The grep -n flag is useful when you want to find the location of a certain word in a file. Similar to using Command + F on a word document, grep -n functions the same way, but through terminal. Then, when you want to edit the file, you can navigate to the specific line number with the word.

**Example 2**
```
[hpai@ieng6-203]:OUP:434$ grep -r -n -l "Neighboring" Kauffman

Kauffman/ch8.txt
```
> Terminal output when using the -n and -l flags

In the above example, I ran the same -n command, but also included the -l flag, which only lists the names of the files in which the word is found. Since the -l flag only lists filenames, we can see that the -n flag had no effect on the output, despite coming first in the command. From trying this combination of flags, we can see that it doesn't make sense to use a -l flag if we want the line numbers because the file names are already given with the -n flag. This leads me to believe that certain flags have priority over others because if the order of the -n and -l flags were switched, the same output is shown.

## -i Flag 

The -i flag when using grep is used when you want to ignore the case of the word you are searching for. 
When grep searches for the string in the file, it searches for the exact match. In other words, it also matches the case that you provide. When the -i
flag is used, the case of the word is ignored, so it searches for all instances of the sequence of characters. 

The -i flag comes in useful for certain log-in features. Some accounts will ingore case on their usernames because they only search for the sequence of characters. In this case, they can use -i to find if the given username is in their file of total usernames without worrying about letter casing.

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


