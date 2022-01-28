#  CSE15L Week 4 Lab Report: Testing and Searching For Bugs and Symptoms

For this week, I had forked the MarkdownParse.java file from the CSE15L Github Repository and created test files to test MarkdownParse's getLinks method via command line args. 
Testing the method with unique test files caused errors such as wrong output, the file freezing/hanging, and exceptions. With this, my lab group and I made changes to fix 
or improve the code provided in Labs 3 and 4. 

# Fix 1: Add If-Statement
![Code Change](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%204%20Lab%20Report%20Images/markdownparsecodechange.JPG)
<br><br>
[Test file link producing error](https://spadmanaban25.github.io/markdown-parse/test-file4.md)
<br><br>
![MarkdownParse Output with error](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%204%20Lab%20Report%20Images/markdownparsecodeerrorifstatement.JPG)
<br><br>
Here, the bug was that no condition was implemented in the getLinks method to check if the the index of the open bracket was -1,
meaning there is no first occurence of an open bracket. Because of this, the current index  will always be less than the 
markdown length. and the array list will keep adding elements infinitely, causing an out of memory exception on commandline when
inputting the test file with no brackets. Thus, an if statement is needed, telling to do the necessary operations when open bracket index is greater than 0.
<br><br>

# Fix 2: Add Break Statement
![Code Change](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%204%20Lab%20Report%20Images/markdownparsecodechange2.JPG)
<br><br>
[Test file link producing error](https://spadmanaban25.github.io/markdown-parse/test-file4.md)
<br><br>
![MarkdownParse Output with error](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%204%20Lab%20Report%20Images/markdownprasecodeerrorbreakstatement.JPG)
<br><br>
Adding the if statement to maintain the condition that the open bracket index is greater than 0 is not enough.
Here, I just made sure that the method won't do the operations if it is not greater than 0, but I need to find
a way to break out the while loop, since it isn't guaranteed in this select test file that there won't be 
an open bracket. Because I didn't add a break statement, the java command lead to a freezing or hanging output
on commandline. To resolve this, I needed to add a break statement to let the method know to break out of the
loop if the index if less than 0.
<br><br>

# Fix 3: Stack Implementation
![Code Change](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%204%20Lab%20Report%20Images/markdownparsecodechange3.JPG)
<br><br>
[Test file link producing error](https://spadmanaban25.github.io/markdown-parse/test-file1.md)
<br><br>
![MarkdownParse Output with error](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%204%20Lab%20Report%20Images/markdownparsecodeerrorstackdatastructure.JPG)
<br><br>
We must consider all cases and outputs when testing. Bugs don't necessarily have to lead to an error or to 
a system crashing. Wrong outputs are also symptoms of bugs. Here, I use a test case file where an extra
parentheses is inserted within the link. When testing on commandline, the output was the link with that 
parentheses. In the method, there is no condition or command to check for any extraneous characters
that are not needed for the link. What my lab group came up with was using a different data structure: stack.
The stack is useful in which all characters of the link could be passed into a stack, and we could pop or remove
characters that weren't necessary for the link. 


