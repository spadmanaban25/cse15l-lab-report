# CSE15L Week 6 Lab Report: Streamlining ssh Configuration

In this lab report, I will be creating a configuration file called config that is located in the .ssh file of
my local drive. Below are screenshots of how I created the file and using this to log in via ssh and copy and 
move files to the server with this file.
<br><br><br>

**SSH Configuration File**
<br><br>
![SSH Config Picture](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%206%20Lab%20Report%20Images/ssh%20config%20location.JPG)
<br><br>
Here, I simply went to the .ssh file on the local drive and created a file called config. I made sure that it was of
type "file," generic extension, so ssh can recognize this. In order to edit this file, I will open this file with 
Nodepad, so I can input the information such as host name and the user account that should recognize this name. 
<br><br>

**SSH Config Login**
<br><br>
![SSH Config Login](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%206%20Lab%20Report%20Images/ssh%20config%20login.JPG)
<br><br>
When logging in to my course-specific account, instead of using ssh then typing out my account username, I can go ahead and use the name of host variable
that I set on the config file. With this, I can simply login faster using this method.
<br><br>

**SSH Config With SCP**
<br><br>
![SSH Config scp file](https://raw.githubusercontent.com/spadmanaban25/cse15l-lab-report/main/Week%206%20Lab%20Report%20Images/ssh%20config%20copy%20file.JPG)
<br><br>
Using this advantage, I can treat this config host name as a variable and replace all occurrences of the ssh login username with this
new host name. One of these occurrences is when using scp to move a file to the remote server. Here, I just did the normal scp
command, but instead of typing out the whole account username, I just used the host name along with the required syntax afterwards. 

<br><br>
**Conclusion**
<br>
Utilizing this config feature is a powerful advantage, especially when you have so much commands to type out. It reduces redundancy
by alot, so there is space for required commands to be typed out fully. In a way, this is a form of abstraction in command-line interface.
