# Week 2 Lab Report

*Hrithik Pai - A17311788*

## Making a Web Server
To make a Web Server, we need to install Java packages, such as the URI package, which allows us to read URLs. 
My algorithm works by first validating the url then calling the add() method. 
The parameter that is passed is the word in the url, found by using the .split() method. 
The add method appends the word to a running String with the escape sequence "\n" after it, making it print on a newline.

**Web Server Code** 

<img width="719" alt="Screen Shot 2023-01-28 at 2 01 46 PM" src="https://user-images.githubusercontent.com/69052552/215293031-e4a61ec3-22ff-4cd4-b20e-285b55f9a1ef.png">

> VS Code tab containing the code to my web server

**Output 1**

<img width="479" alt="Screen Shot 2023-01-28 at 1 49 14 PM" src="https://user-images.githubusercontent.com/69052552/215292631-93cdf066-0944-4f91-a01d-fa17df66ad0f.png">

> My Web Server output when asked to add a "Hello World" message.

In this query, the add(String w) method is called. In this case, the String "Hello World" is passed to the method.
The method adds the String to a running String, called *words*, and appends a newline character at the end.
To get the string, I used the .split("=") method to split the actual word from the query. 

**Output 2**

<img width="333" alt="Screen Shot 2023-01-28 at 2 06 22 PM" src="https://user-images.githubusercontent.com/69052552/215293160-8b4aa83e-d841-49a7-b101-78dbb7122fd5.png">

> Web Server output when asked to incorrectly add the word "Java".

In this query, we can see that "404 not found" is returned. This is because I have an if statement to validate the path and query. 
If the path does not include the string "add-message", the program returns a "404 not found". In this case, the path is "add", 
which does not contain "add-message", so it prints out a "404 not found", as an error.

## Debugging Programs with Bugs

The method below is trying to reverse the elements of an array by making a new array and returning that new array. 
Let's see how it performs when it is tested.

<img width="574" alt="Screen Shot 2023-01-28 at 2 43 19 PM" src="https://user-images.githubusercontent.com/69052552/215294446-287ccd88-c788-4abe-a7b2-e166c9262b0a.png">

**Failure-Inducing Input**
```
@Test
public void reverseInPlaceNums() { 
  int [] input = {1,2,3,4}; 
  assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input));
}
```
> JUnit test of reversed() that showcases a bug in the program.

**Corresponding Symptom**

<img width="617" alt="Screen Shot 2023-01-28 at 2 50 38 PM" src="https://user-images.githubusercontent.com/69052552/215294673-dc975342-74d7-4a01-9917-1c63b2037a3c.png">

> Symptom on VSCode when the above test was run. Clearly shows that symptom was not same as expected value.

**Non-Failure Input** 
```
@Test
public void reverseInPlaceZeros() { 
  int [] input = {0,0,0,0}; 
  assertArrayEquals(new int[]{0,0,0,0}, ArrayExamples.reversed(input));
}
```
> JUnit test of reversed() method that doesn't induce a failure

**Corresponding Symptom**

<img width="611" alt="Screen Shot 2023-01-28 at 2 51 51 PM" src="https://user-images.githubusercontent.com/69052552/215294709-b62c9211-5c5c-47f8-a41e-7b14050d3bd7.png">

> Symptom on VSCode when the above test was run. The green check mark on the left shows that the test passed.

**The Bug Before Changes** 
``` 
  arr[i] = newArray[arr.length - i - 1];
}
return arr;
``` 

**Corresponding Code After Changes** 
```
  newArray[i] = arr[arr.length - i - 1];
}
return newArray;
``` 

In this method, the bug was a result of the programmer mixing up the two arrays that are being used. Originally, the programmer did `arr[i] = newArray[arr.length - i - 1];`. This line of code will always produce an array of all zeros because it is taking the values of *newArray*, backwards, and assigning it to *arr*. *newArray* is an array of all 0s because it is the default value of an integer, so this line of code is essentially populating *arr* with 0s. The second error is that the programmer initially returned the original array, *arr*, even though the comments mentioned to return a new array. 

To fix this, I replaced the line inside the for-loop with `newArray[i] = arr[arr.length - i - 1];`. This line now takes each value in *arr* backwards, and puts it in the new array, *newArray*. I also modified the return statement to `return newArray`, so that it returns the new array, instead of the old one.


## Reflection
In Lab 2, I learned how to set-up a local host and read urls. Although I knew about local hosts and the general concept behind them, I never knew that it was possible to read URLs and update the site live without recompiling the .java file. Adding onto this, I learned some new URL class methods, such as .getPath() and .getQuery(). I also learned about ports numbers and how they relates to local hosts. I also found out how to specify the port number when running my program through the command line.
