# Lab Report 1
---
## **Installing VScode**

To install VSCode, visit the [VScode Website](https://code.visualstudio.com) and click the download button. After running the installer and downloading necessary packages from the installer, VScode is ready to use.

Example of VScode installed:
 ![Image of VSCODE SETUP](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport1/Screen%20Shot%202022-04-01%20at%206.12.35%20PM.png?raw=true)  

---
## **Remote Connection**

 > Prior to the lab, make sure you [reset your password](https://sdacs.ucsd.edu/~icc/index.php) for your cs15lsp22 account.  

Open the terminal and type:  
`ssh cs15lsp22(username)@ieng6.ucsd.edu`  
Replace (username) with the three letters from your [account name](https://sdacs.ucsd.edu/~icc/index.php).

Type in your password (it should not be visible to protect your privacy) and hit return/enter. For any first time prompts, type `yes` and hit `return`. You should now be connected to the remote machine.

Example of the Command and Successful Connection: 
![Image for Remote Connection](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport1/Screen%20Shot%202022-04-01%20at%206.16.03%20PM.png?raw=true)

---
## **Try Some Commands**
Try some commands out while connected to the remote machine. Here are a few you can try:
```
cd ~
cd
ls
ls -l
ls -lat
cp /home/linux/ieng6/cs15lsp22/public/hello.txt ~/
```
Does the last command work? You should get a result like this:
![Image of cp command](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport1/Screen%20Shot%202022-04-01%20at%206.36.29%20PM.png?raw=true)

---
## **Moving Files with `scp`**

Create a file on VScode called `WhereAmI.java` with the following contents:
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
We will be using a command called `scp` which stands for Secure Copy Protocol. This way, we will be able to copy a file from the client (your local machine) to the remote machine.   
Follow the following steps:  
1. Run `javac` and `java` commands for the `WhereAmI.java` file. Make an observation about the output.
2. From the directory containing the `WhereAmI.java` file, run   
`scp WhereAmI.java cs15lsp22(username)@ieng6.ucsd.edu:~/`
3. Enter your password
4. Log into the ien6 with `ssh cs15lsp22(username)@ieng6.ucsd.edu`
5. Use `ls`. You should be able to see the `WhereAmI.java` file
6. Try running `javac` and `java` for the `WhereAmI.java` file. What is different?

Your result should look like:
![scp and ssh](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport1/Screen%20Shot%202022-04-01%20at%206.44.30%20PM.png?raw=true)

---
## **Setting an SSH key**

Typing a password each time we log onto the remote machine can time consuming. By using SSH keys we can circumvent this to automatically bypass the password requirement.

To accomplish this, follow the following steps:
1. Run `ssh-keygen` on the client terminal (*Windows users should type `ssh-keygen -t ed25519*)
2. When prompted with ` Enter file in which to save the key`, enter   
`(/Users/<user-name>/.ssh/id_rsa): /Users/<user-name>/.ssh/id_rsa`, replacing `<user-name>` with your machine's appropriate path
3. When prompted with `Enter passphrase` hit `return`. Repeat when asked to enter the passphrase again
4. Log onto the remote server with `ssh cs15lsp22(username)@ucsd.edu` and enter your password
5. Run `mkdir .ssh` and logout with `Ctrl/Cmd + Q` 
6. Run  
` scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22(username)@ieng6.ucsd.edu:~/.ssh/authorized_keys` replacing `<user-name>` with your machine's appropriate path and (username) with your ieng6 account username. Enter your password if prompted  

Try logging in with `ssh`. You shouldn't need a password anymore! The same should apply for `scp`.

Logging in should look like this now:
![logging in with ssh keys](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport1/Screen%20Shot%202022-04-01%20at%206.57.04%20PM.png?raw=true)

---