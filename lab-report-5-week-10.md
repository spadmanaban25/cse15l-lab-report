## Week 10 Lab Report: Comparing Both Implementations of Markdown Parse

In this final Lab Report, I will select two test cases
from the CommonMark-spec test file where my implementation
of Markdown Parse and Professor Politz's Markdown Parse
yield different results. 
<br>
## Process of Finding the Results
Here, I used a command called bash script.sh
to point to results.txt. This means that I pushed
all the results of the test cases in mine and Professor's Markdown Parse to this new file called results.txt.

![](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%2010%20Lab%20Report%20Images/mymdparsebashscript.JPG)



Moreover, I used the **diff** command which
will show the test cases that yield different results.

![](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%2010%20Lab%20Report%20Images/difftestresults.JPG)
<br><br>
I will be selecting test cases files: **481.md** and **51.md**

![](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%2010%20Lab%20Report%20Images/different%20test%20case1.JPG)
<br><br><br>
![](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%2010%20Lab%20Report%20Images/different%20test%20case%202.JPG)

## Test File: 481.md
In this test file, a valid link is 
created in this file. This is valid since 
CommonMark acknowledges this due to correct
syntax. My implementation recognized it and added
it to the list. However, Professor's didn't and returned
an empty list.
<br><br>
The correct output should be: **[/uri "title"]**
<br><br>
A potential bug in Professor's implementation is that
the index of either openParen or closeParen is possible yielding to -1. 
<br><br>

## Test File: 51.md
In this test file, three dashed lines were the only 
content in the file. CommonMark did not recognize this 
as a link. Because of this, my implementation produced 
nothing, while Professor's produced three empty ArrayLists. Logically, the result should be just any empty list. I feel like mine definitly did not cover for when there are no link-related characters appearing the test file. This could have led to a symptom of infinite loop or a strange symptom since it should have just returned the empty list if anything. 
