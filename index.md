# CSE 15L Week 2 Lab Report: Remote Accesss

<span style="font-size:20px;">In this lab report, I will show how to remotely connect your personal computer (client) to the UCSD's ieng6 server.</span>
<br><br><br>
<span style="font-size:18px;">For this tutorial, I will be using Visual Studio Code as the IDE for the remote connection. Go to the Microsoft VS Code website [https://code.visualstudio.com/](https://code.visualstudio.com/) , to download VS Code for any platform.</span>
## Installing VS Code
<br><br>
<img src="https://github.com/spadmanaban25/cse15l-lab-report-week-2/blob/main/vscodedownloadscreenshot.JPG?raw=true" width="625" height="350"/>

<br><br><br>
<span style="font-size:18px;">After downloading and installing VS Code, you should have this opening page on VS Code: </span>
<br><br>
<img src="https://github.com/spadmanaban25/cse15l-lab-report-week-2/blob/main/vscode%20opening%20page.jpg?raw=true" width="625" height="350"/>
<br><br><br>
## Remotely Connecting
<span style="font-size:18px;">For Windows users, you will need a program called OpenSSH installed. To check if it is installed, go to **Settings**, **Apps**, **Apps and Features**,
and select **Optional Features**. Search for OpenSSH Server and OpenSSH Client. If one of them or both of them don't show up, then click **Add A Feature**, and install 
them.
<br><br>
<img src="https://github.com/spadmanaban25/cse15l-lab-report-week-2/blob/main/ssh%20feature%20screenshot.JPG?raw=true" width="625" height="350"/>
</span>
<br><br>
<span style="font-size:18px;">You will need your CSE15L course-specific account username. Go to this [link](https://sdacs.ucsd.edu/~icc/index.php), enter your 
UCSD username, and Student ID (starts with A). Then click on CSE15L course, and you should see your username.</span>
<br><br>
<img src="https://github.com/spadmanaban25/cse15l-lab-report-week-2/blob/main/course-specific-account%20screenshot.JPG?raw=true" width="625" height="350"/>
<br><br>
<span style="font-size:18px;">Now we will go to VS Code and start the remote connection. Click on the Terminal Tab to open a new Terminal (or Ctrl/Command + \` ). Type the following command: </span>
<br><br>
`ssh cs15lwi22yy@ieng6.ucsd.edu`
<br>
<span style="font-size:18px;">Where yy is your last few characters of your username</span><br>
<span style= "font-size:18px;">Once you press Enter, it will ask you if you are sure to continue connecting (This happens when you try to login to new device). Type ***yes*** and continue.
Next, it will ask for password, so type in your password (it will appear blank, but you are still typing). There might few times where it will ask you to type the password
couple times, but again it might be due to new device login, or you are typing incorrect password. Afer this, you should get a similar result:	
<br>
```
ssh cs15lwi22yy@ieng6.ucsd.edu
Last login: Wed Jan 5 10:57:29 2022 from 107-143-89-38.lightspeed.miamifl.sbcglobal.net
quota: No filesystem specified.
Hello cs15lwi22yy, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   18:25:01   34  2.60,  2.50, 2.41
ieng6-202   18:25:01   23  3.29,  3.30, 3.26
ieng6-203   18:25:01   27  1.25,  1.32, 1.18

Thu Jan 06, 2022 6:28pm - Prepping cs15lwi22
```
<br><br>
Now you are logged in! Here, I didn't need to type my password in because I had set ssh keys in which I don't have to type in my password every time I login. We will
discuss more about this later on.</span>
<br><br>
## Try Running Some Commands
<span style="font-size:18px;">Now that you are logged in, type some commands and see the results. Remember, we will be using linux commands since we have now logged into the server which
is running a linux operating system. Some commands include, **cd**, **ls**, and **pwd**. Go to this [link](https://ucsd-cse15l-w22.github.io/week/week1/#part-4--run-some-commands) to 
see list of commands the CSE15L staff provided. <br><br> Also, go to this [link](https://www.javatpoint.com/linux-commands) to find more linux commands.</span>
<br><br>
```
Wed Jan 26, 2022  2:23pm - Prepping cs15lwi22
[cs15lwi22yy@ieng6-201]:~:127$ ls -a
.              .bashrc  .kshrc       .modulesbegenv  .ssh       .zshrc           Test.class      WhereAmI.java
..             .cache   .local       .motd           .viminfo   HelloTest.class  Test.java       hello
.bash_history  .config  .locallogin  .procmailrc     .zprofile  HelloTest.java   Tester.java     perl5
.bash_profile  .cshrc   .login       .profile        .zshenv    OtherMain.java   WhereAmI.class
[cs15lwi22yy@ieng6-201]:~:128$ ls -lat
total 164
-rw-r--r--   1 cs15lwi22yy ieng6_cs15lwi22  1286 Jan 26 14:23 .modulesbegenv
-rw-r-----   1 cs15lwi22yy ieng6_cs15lwi22     0 Jan 26 14:22 .motd
drwxr-sr-x 637 cs15lwi22    ieng6_cs15lwi22 49152 Jan 15 08:06 ..
-rw-------   1 cs15lwi22yy ieng6_cs15lwi22  1346 Jan 14 11:20 .bash_history
-rw-r--r--   1 cs15lwi22yy ieng6_cs15lwi22   184 Jan 14 10:18 Tester.java
drwxr-s---   7 cs15lwi22yy ieng6_cs15lwi22  4096 Jan 14 10:18 .
-rw-r-----   1 cs15lwi22yy ieng6_cs15lwi22   575 Jan  6 19:55 WhereAmI.class
-rw-r-----   1 cs15lwi22yy ieng6_cs15lwi22   311 Jan  6 19:55 OtherMain.java
-rw-r--r--   1 cs15lwi22yy ieng6_cs15lwi22   311 Jan  6 19:47 Test.java
-rw-r--r--   1 cs15lwi22yy ieng6_cs15lwi22   311 Jan  6 19:40 WhereAmI.java
drwxr-sr-x   2 cs15lwi22yy ieng6_cs15lwi22  4096 Jan  6 19:20 perl5
-rw-------   1 cs15lwi22yy ieng6_cs15lwi22   840 Jan  6 19:03 .viminfo
-rw-r-----   1 cs15lwi22yy ieng6_cs15lwi22    31 Jan  6 19:03 hello
drwxr-s---   2 cs15lwi22yy ieng6_cs15lwi22  4096 Jan  6 16:40 .ssh
-rw-r-----   1 cs15lwi22yy ieng6_cs15lwi22   427 Jan  5 16:23 HelloTest.class
-rw-r--r--   1 cs15lwi22yy ieng6_cs15lwi22   126 Jan  5 16:22 HelloTest.java
-rw-r-----   1 cs15lwi22yy ieng6_cs15lwi22   418 Jan  5 16:21 Test.class
drwxr-sr-x   3 cs15lwi22yy ieng6_cs15lwi22  4096 Jan  5 10:46 .cache
drwxr-sr-x   3 cs15lwi22yy ieng6_cs15lwi22  4096 Jan  5 10:46 .local
drwxr-sr-x   3 cs15lwi22yy ieng6_cs15lwi22  4096 Jan  5 10:46 .config
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22   290 Dec 20 13:39 .zshrc
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22   481 Dec 20 13:39 .zshenv
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22  1931 Dec 20 13:39 .zprofile
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22  1961 Dec 20 13:39 .profile
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22   837 Dec 20 13:39 .procmailrc
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22   431 Dec 20 13:39 .login
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22   155 Dec 20 13:39 .locallogin
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22  1692 Dec 20 13:39 .kshrc
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22  1931 Dec 20 13:39 .cshrc
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22  1721 Dec 20 13:39 .bashrc
-rwxr-x---   1 cs15lwi22yy ieng6_cs15lwi22   975 Dec 20 13:39 .bash_profile
[cs15lwi22yy@ieng6-201]:~:129$ ls
HelloTest.class  OtherMain.java  Test.java    WhereAmI.class  hello
HelloTest.java   Test.class      Tester.java  WhereAmI.java   perl5
[cs15lwi22yy@ieng6-201]:~:130$ ls -l
total 36
-rw-r----- 1 cs15lwi22yy ieng6_cs15lwi22  427 Jan  5 16:23 HelloTest.class
-rw-r--r-- 1 cs15lwi22yy ieng6_cs15lwi22  126 Jan  5 16:22 HelloTest.java
-rw-r----- 1 cs15lwi22yy ieng6_cs15lwi22  311 Jan  6 19:55 OtherMain.java
-rw-r----- 1 cs15lwi22yy ieng6_cs15lwi22  418 Jan  5 16:21 Test.class
-rw-r--r-- 1 cs15lwi22yy ieng6_cs15lwi22  311 Jan  6 19:47 Test.java
-rw-r--r-- 1 cs15lwi22yy ieng6_cs15lwi22  184 Jan 14 10:18 Tester.java
-rw-r----- 1 cs15lwi22yy ieng6_cs15lwi22  575 Jan  6 19:55 WhereAmI.class
-rw-r--r-- 1 cs15lwi22yy ieng6_cs15lwi22  311 Jan  6 19:40 WhereAmI.java
-rw-r----- 1 cs15lwi22yy ieng6_cs15lwi22   31 Jan  6 19:03 hello
drwxr-sr-x 2 cs15lwi22yy ieng6_cs15lwi22 4096 Jan  6 19:20 perl5
```
<br><br>
## Moving Files over SSH with scp
<span style="font-size:18px;">We will now see how to copy files from your personal computer to the remote server. The command, **scp** helps us do this. <br> <br>
First, create a Java file (or any file type, but we will create a Java file for this tutorial) and put some content in there. After this, run this command on the directory
your Java file is located: <br><br>
`scp WhereAmI.java cs15lwi22yy@ieng6.ucsd.edu:~/`
<br><br>
Where you replace WhereAmI.java with the Java file you created. <br><br>
As usual, you will be prompted to enter your password. Enter, and the action will be executed. Then, log in to ssh, and type **ls** which lists all files located in the directory. <br><br>
Here is an example of using **scp** to move a Java file to a remote computer, and the results of it. You will see the file you copied: <br><br></span>
```
class WhereAmI {     
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

```
[cs15lwi22yy@ieng6-201]:~:135$ ls
HelloTest.class  OtherMain.java  Test.java    WhereAmI.class  hello
HelloTest.java   Test.class      Tester.java  WhereAmI.java   perl5
```
<br><br>
## Setting an SSH Key
<span style="font-size:18px;">As mentioned earlier, we will now discuss about SSH Keys. Basically, this feature allows us to create two SSH keys, one public and one private.
The public key is saved in a location on the server, and the private key is saved in a location on your computer. So then when you log on to ssh, you don't need your password. <br><br>
You will implementing a component of ssh called **keygen** to set up your public/private keys. Type the following command: <br>
```
C:\Users\padsp>ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/joe/.ssh/id_rsa): C:\Users\padsp/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in C:\Users\padsp/.ssh/id_rsa.
Your public key has been saved in C:\Users\padsp/.ssh/id_rsa.
The key fingerprint is:
SHA256: dgaKKOYDU088t1061Jjhdw3nG7LOSATgix/COZUVH4 padsp@DESKTOP-LH9UA50 
The key's randomart image is:
+--- [RSA 3072]----+
|	 ....            |
|     ..           |
|.. O O..E.        |
|o.o + 0.=         |
|.o o o oS.o       |
|  + X ..o+        |
|o  B + +.o        |
|*+.o.+ .=         |
|=O*=*.o  .        |
+---- [SHA256]-----+
```
For Windows users, additional setup is required in which you will need to implement **ssh-add**: 
```
# By default the ssh-agent service is disabled. Allow it to be manually started for the next step to work.
# Make sure you're running as an Administrator.
Get-Service ssh-agent | Set-Service -StartupType Manual

# Start the service
Start-Service ssh-agent

# This should return a status of Running
Get-Service ssh-agent

# Now load your key files into ssh-agent
ssh-add ~\.ssh\id_ed25519
```

This will add the private key to your client directory. Then log in through ssh, and use **mkdir** to create a new directory, ".ssh". After this, log out. <br><br>Now we have to add the public key to the remote computer server using **scp**: <br>
```
C:\Users\padsp>scp C:/Users/padsp/.ssh/id_rsa.pub_cs151wi22avv@ieng.ucsd.edu:-/.ssh/authorized_keys 
Password: 
id_rsa.pub
```
We are done. Now, you can **ssh** without entering the password.<br><br></span>
<img src="https://github.com/spadmanaban25/cse15l-lab-report-week-2/blob/main/ssh%20keys%20results.jpg?raw=true" width="750" height="375"/><br><br><br>
## Optimizing Remote Running
<span style="font-size:18px;">So far, you have learned how to log into the remote server and use different commands when logged in. We can take one step further
and run files and commands remotely through efficient methods. One way we can do this is append commands in quotes on the ssh login statement: <br><br>
<img src="https://github.com/spadmanaban25/cse15l-lab-report-week-2/blob/main/optimize%20ssh%20command1.JPG?raw=true"/><br><br>
Another way is to run multiple files at the same time, separating each file with semicolon:</span>
<img src="https://github.com/spadmanaban25/cse15l-lab-report-week-2/blob/main/optimize%20ssh%20command2.jpg?raw=true" width="700" height="450"/><br><br>
## Conclusion
<span style="font-size:18px;">You have now learned how to remotely connect your personal computer to UCSD's remote computer. 
Also, you have learned linux commands that are used to run on the server, commands that cannot be used on a Windows or Mac
platform. Moreover, you now know how to optimize your ssh environment by adding ssh keys, and learning syntax that can do multiple
actions in one statement. 

