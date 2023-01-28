# Week 2 Lab Report

*Hrithik Pai - A17311788*

## Making a Web Server
To make a Web Server, we need to install Java packages, such as the URI package, which allows us to read URLs. 
My algorithm works by first validating the url then calling the add() method. 
The parameter that is passed is the word in the url, found by using the .split() method. 
The add method appends the word to a running String with the escape sequence "\n" after it, making it print on a newline.

<img width="479" alt="Screen Shot 2023-01-28 at 1 49 14 PM" src="https://user-images.githubusercontent.com/69052552/215292631-93cdf066-0944-4f91-a01d-fa17df66ad0f.png">

> My Web Server output when asked to add a "Hello World" message.

In this query, the add(String w) method is called. In this case, the String "Hello World" is passed to the method.
The method adds the String to a running String, called *words*, and appends a newline character at the end.
To get the string, I used the .split("=") method to split the actual word from the *add-message* part of the query. 

