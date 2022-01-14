# CSE 15L Week 2 Lab Report: Remote Accesss

<span style="font-size:20px;">In this lab report, I will show how to remotely connect your personal computer (client) to the UCSD's ieng6 server.</span>
<br><br><br>
## Installing VS Code
<span style="font-size:18px;">For this tutorial I will be using Visual Studio Code for the remote connection. Go to the Microsoft VS Code website to download VS Code for any platform.</span>
<br><br>
<img src = "file:///C:/Users/padsp/Documents/Steve/vs%20code%20download%20screenshot.JPG" width="625" height="350"/>
<br><br><br>
<span style="font-size:18px;">After downloading and installing VS Code, you should have this opening page on VS Code: </span>
<br><br>
<img src = "file:///C:/Users/padsp/Documents/Steve/vscode%20opening%20page.JPG" width="625" height="350"/>
<br><br><br>
## Remotely Connecting
<span style="font-size:18px;">For Windows users, you will need a program called OpenSSH installed. To check if it is installed, go to **Settings**, **Apps**, **Apps and Features**,
and select **Optional Features**. Search for OpenSSH Server and OpenSSH Client. If one of them or both of them don't show up, then click **Add A Feature**, and install 
them.
<br><br>
<img src = "file:///C:/Users/padsp/Documents/Steve/ssh%20feature%20screenshot.JPG" width="625" height="350"/>
</span>
<br><br>
<span style="font-size:18px;">You will need your CSE15L course-specific account username. Go to this [link](https://sdacs.ucsd.edu/~icc/index.php), enter your 
UCSD username, and Student ID (starts with A). Then click on CSE15L course, and you should see your username.</span>
<br><br>
<img src = "file:///C:/Users/padsp/Downloads/course-specific-account%20screenshot.JPG" width="625" height="350"/>
<br><br>
<span style="font-size:18px;">Now we will go to VS Code and start the remote connection. Click on the Terminal Tab to open a new Terminal (or Ctrl/Command + ` ). Type the following command: </span>
<br><br>
<img src = "file:///C:/Users/padsp/Downloads/ssh%20command%20vscode.JPG"/>
<br><br>
<span style="font-size:18px;">Where yy is your last few characters of your username</span><br>
<span style= "font-size:18px;">Once you press Enter, it will ask you if you are sure to continue connecting (This happens when you try to login to new device). Type ***yes*** and continue.
Next, it will ask for password, so type in your password (it will appear blank, but you are still typing). There might few times where it will ask you to type the password
couple times, but again it might be due to new device login, or you are typing incorrect password. Afer this, you should get a similar result:	
<br><br>
<img src="file:///C:/Users/padsp/Documents/Steve/remote%20connection%20result.JPG" width="625" height="350"/>
<br><br>
Now you are logged in! Here, I didn't need to type my password in because I had set ssh keys in which I don't have to type in my password every time I login. We will
discuss more later on.</span>
<br><br><br>
## Try Running Some Commands
<span style="font-size:18px;">Now that you are logged in, type some commands and see the results. Remember, we will be using linux commands since we have now logged into the server which
is running a linux operating system. Some commands include, **cd**, **ls**, and **pwd**. Go to this [link](https://ucsd-cse15l-w22.github.io/week/week1/#part-4--run-some-commands) to 
see list of commands the CSE15L staff provided. <br><br> Also, go to this [link](https://www.javatpoint.com/linux-commands) to find more linux commands.</span>
<br><br>
<img src = "file:///C:/Users/padsp/Documents/Steve/ssh%20commands.jpg" width="625" height="350"/>
<br><br><br>
## Moving Files over SSH with scp
<span style="font-size:18px;">We will now see how to copy files from your personal computer to the remote server. The command, **scp** helps us do this. <br> <br>
First, create a Java file (or any file type, but we will create a Java file for this tutorial) and put some content in there. After this, run this command on the directory
your Java file is located: <br><br>
<img src = "file:///C:/Users/padsp/Downloads/scp%20command.jpg"/>
<br><br>
As usual, you will be prompted to enter your password. Enter, and the action will be executed. Then, log in to ssh, and type **ls** which lists all files located in the directory: <br><br>
<img src= "file:///C:/Users/padsp/Documents/Steve/scp%20command%20result.jpg" width="625" height="350"/>
<br><br>
Here is an example of using **scp** to move a Java file to a remote computer, and the results of it.</span>