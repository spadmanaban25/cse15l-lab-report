## Week 8 Lab Report: Testing Snippets between Two Implementations of MarkdownParse.java

For this Lab Report, I had been given three snippets of code that contain links and text. This is 
to be tested using JUunit Test methods with my implementation of MarkdownParse.java and the other
group's implementation. 

Repositories for MarkdownParse.java:
<br><br>
[My Repository](https://github.com/spadmanaban25/markdown-parse)
<br>
[Other Repository](https://github.com/clingunis/markdown-parse)

## Snippet 1: Inline Backticks
For this snippet, the expected links to be returned were: **`google.com, google.com, ucsd.edu**. The reason
that these links should be returned is that Markdown reads these as valid links, so **url.com** is not one.
<br><br>
However, my MarkdownParse had read **url.com** link as valid and returned it in the list. <br>
![Snippet 1 Test Failed](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%208%20Lab%20Report%20Images/testSnippet1FailedResult.JPG)
<br><br>
The other person's MarkdownParse had also read **url.com** as valid too. <br>
![Snippet 1 Other Failed](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%208%20Lab%20Report%20Images/testSnippet1OtherFailedResult.JPG)
<br><br>

## Snippet 2: Nested Parantheses, Brackets, Escaped Brackets
Here, I expected that the return list will contain the following links: **a.com, a.com(()), example.com** since 
Markdown read these links as valid using VS Code's Markdown Preview. 
<br><br>
My MarkdownParse read all these links, except for the fact that the second link was cut short of two closing parentheses. <br>
![Snippet 2 Test Failed](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%208%20Lab%20Report%20Images/testSnippet2FailedResult.JPG)
<br><br>
The other person's MarkdownParse had the same issue. <br>
![Snippet 2 Other Failed](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%208%20Lab%20Report%20Images/testSnippet2OtherFailedResult.JPG)
<br><br>

## Snippet 3: New lines within Brackets and Parantheses
This snippet was unique in which there were break lines in brackets and parantheses causing small links 
to be huge within the text file. With this, I expected that these links: **https://www.twitter.com, https://ucsd-cse15l-w22.github.io/, https://cse.ucsd.edu/**
to be returned in the list since Markdown regarded this as valid links. <br><br>
<br>
In addition to another invalid link being added to the list, a JUnit Assertion error was thrown possibly due to extraneous
characters included in the links or anywhere else in the text file. <br>
![Snippet 3 Test Failed](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%208%20Lab%20Report%20Images/testSnippet3FailedResult.JPG)
<br><br>
The other person's code face the same issue including the JUnit Assertion error. <br>
![Snippet 3 Other Failed](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%208%20Lab%20Report%20Images/testSnippet3OtherFailedResult.JPG)
<br><br>
## Reflection
* For Snippet 1, I presume that I must ensure that the characters bounded by the backticks should not include the Markdown formatted brackets.
If it does, then Markdown will assume that the bracket will be part of some code segment which is what the backtick is used for. A small code change
would work.

* In order for Snippet 2 and other similar cases to work, we must ensure that there is a balance of nested parantheses and brackets.
This is important so that Markdown will recognize which brackets/parantheses are the essential ones and which ones are extraneous
or minor ones. This can be done with short code change. 

* Regarding Snippet 3, this will require more than a short code change. We are dealing with more manipulation with Markdown links, 
so it will take some more changes to make sure that all links in the file are recognized by Markdown. Having new lines in brackets
and parantheses shouldn't result in errors provided that they occur at places that won't affect the overall link.

