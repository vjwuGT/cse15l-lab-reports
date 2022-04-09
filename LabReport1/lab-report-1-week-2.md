# Lab Report 1
---
## **Installing VScode**

To install VSCode, visit the [VScode Website](https://code.visualstudio.com) and click the download button. After running the installer and downloading necessary packages from the installer, VScode is ready to use.

Example of VScode installed:
 ![Image of VSCODE SETUP](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport1/Screen%20Shot%202022-04-01%20at%206.12.35%20PM.png?raw=true)  

## **Remote Connection**

 > Prior to the lab, make sure you [reset your password](https://sdacs.ucsd.edu/~icc/index.php) for your cs15lsp22 account.


Open the terminal and type:  
`ssh cs15lsp22(username)@ieng6.ucsd.edu`

Replace (username) with the three letters from your [account name](https://sdacs.ucsd.edu/~icc/index.php).

Type in your password (it should not be visible to protect your privacy) and hit return/enter. For any first time prompts, type `yes` and hit `return`. You should now be connected to the remote machine.

Example of the Command and Successful Connection: 
![Image for Remote Connection](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport1/Screen%20Shot%202022-04-01%20at%206.16.03%20PM.png?raw=true)

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
Does the last command work? You should get a result like the example.

Example of `cp /home/linux/ieng6/cs15lsp22/public/hello.txt` 

![Image of cp command](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport1/Screen%20Shot%202022-04-01%20at%206.36.29%20PM.png?raw=true)