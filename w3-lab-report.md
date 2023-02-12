# Week 3 Lab Report

*Hrithik Pai - A17311788*

## All About the Grep Command
In this report, I will be exploring the grep command. The grep command is used to search for a string within files. As with any other command, grep has flags that can be used to alter the output. Here, I will be discussing 4 of these flags. 


**-r Flag** 

The -r flag is used to search recursively within a directory. This is useful if the file system has a complex heirarchy because grep can just search all the files within the given directory. The command follows `$ grep -r "*word*" *directory*` 

```
[hpai@ieng6-203]:skill-demo1-data:384$ grep -r "world" written_2/non-fiction/OUP/Berk/
written_2/non-fiction/OUP/Berk/CH4.txt:Psychoanalyst Erik Erikson built on Freud’s vision, expanding his picture of make-believe. According to Erikson, children draw on fantasy play to ﬁnd out about themselves and their social world.1 In all cultures, children act out family roles and highly visible occupations—police officer, doctor, and nurse in our society; rabbit hunter and potter among the Hopi Indians; and hut builder and spear maker among the Baka of West Africa.2 As they do so, they enter a small social organization whose members must cooperate to achieve common goals. And through observing and emulating admired adult ﬁgures, preschoolers internalize social norms and gain a sense of their future, of what they can become and how they can contribute to society. 

written_2/non-fiction/OUP/Berk/CH4.txt:Piaget acknowledged the emotional function of play, and he agreed that through pretending, children become familiar with social-role possibilities. But he is best known for stressing the symbolic nature of make-believe. Pretending, Piaget pointed out, is a vital means of mentally representing the world that, along with gestures, language, and drawings, develops rapidly in early childhood. Through it, children practice and strengthen their capacity to represent their experiences.3 For example, when Sophie pretended to put the animals to bed and used a TinkerToy to stand for a lollipop, she represented in her mind what formerly she could experience only directly—by going to bed or sucking a lollipop. Practicing and solidifying modes of representation, Piaget emphasized, make it possible for the child to free thought from the here and now; create larger images of reality that take into account past, present, and future; and transform those images mentally in the service of logical thinking. 

written_2/non-fiction/OUP/Berk/CH4.txt:Around age 2, children begin to pretend with less realistic toys, such as a block for a telephone. And sometime during the third year, they can imagine objects and events with little or no support from the real world, as when they say to a play
...
```
> Truncated output when using -r flag on the Berk directory when searching for the word "world"

In the above command, grep searched recursively for the word "world" in the Berk directory. When it searched recursively, it went through all the files in the Berk directory and found all instances of "world" and printed the lines surrounding that word within each file.

```
[hpai@ieng6-203]:skill-demo1-data:387$ grep -r "world" written_2/non-fiction/OUP/Berk/ch7.txt
In this chapter, I take up dilemmas that today’s parents face in rearing young children. Throughout this book, we have touched on myriad forces that make contemporary parenting highly challenging. These include one-sided, contradictory messages in the parenting-advice literature; career pressures that impinge on parent involvement in children’s lives; abysmally weak American child-care services to assist employed parents in their child-rearing roles; cultural violence and excessive materialism permeating children’s worlds; schools with less than optimal conditions for children’s learning; and impediments to granting children with deﬁcits and disabilities social experiences that maximize their development. 

Parents are wise to limit children’s access to TV to about one to one-and-a-half hours a day—no more than 10 hours a week. Following that guideline would cut the exorbitant number of hours children spend watching TV by 50 to 75 percent. Parents also need to prohibit violent TV and orient children toward educational programs that inform them about their world and toward entertainment shows that teach positive values and social skills. In Chapter 2, I explained how readily children can pick up negative attitudes and behaviors from television. Fortunately, children can just as easily absorb worthwhile messages and information from TV, so parental guidance in this area can have great beneﬁts for development.

Chinese and Japanese parents spend a great deal of time helping their children with homework—far more than American parents do. Asian parents also communicate often with teachers about how to help their child learn at his or her best. Rather than being dependent, Chinese and Japanese students develop into well adjusted, excellent students51—at the top in academic achievement in the world. 
```
> Output when using -r flag on the ch7.txt file in the Berk directory

As we can see from above, the -r flag can also be used on a .txt file, meaning it will not throw an error if a directory is not provided. If we give a .txt file to the -r flag, the -r flag's function gets omitted because there is nothing to search recursively for. 

**-i Flag** 
The -i flag when using grep is used when you want to ignore the case of the word you are searching for. 
When grep searches for the string in the file, it searches for the exact match. In other words, it also matches the case that you provide. When the -i flag is used, the case of the word is ignored, so it searches for all instances of the sequence of characters. 


