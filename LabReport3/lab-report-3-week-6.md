# Lab Report 3
## by Victor Wu

## **Streamlining ssh Configuration**
While we already have ssh keys to log into the remote server without a password, typing out the full username can be quite time consuming. In this section, we will setup a config file so we only have to type `ssh ieng6` to login rather than the full username.

Follow the following steps:
1. Type `cd ~/.ssh` in the terminal to navigate to your .ssh folder.
2. Then create the config file by typing `touch config.txt`.
3. Open Finder (*Mac*) or File Explorer (*Windows*) and navigate to the `.ssh` folder.
    > Note: The folder will likely be hidden and you can do `CMD + Shift + .` to view hidden folders on Mac.
4. Open the `config.txt` file and add the following lines 
```
    Host ieng6
        HostName ieng6.ucsd.edu
        User cs15lsp22zzz (use your username)
```
Since the file is just a text file, your default text editor should be able to edit this. Here is an image for reference on Mac: 

![image1](https://raw.githubusercontent.com/vjwuUCSD/cse15l-lab-reports/main/LabReport3/Screen%20Shot%202022-05-08%20at%208.20.53%20PM.png)

5. Remove the `.txt` file ending and save.
6. Try logging in with just `ssh ieng6`. It should look like this 
![image2](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport3/Screen%20Shot%202022-04-29%20at%207.41.37%20PM.png?raw=true)
7. Success! You are done.

Try using `scp` to copy over files into the remote with your new log in command. A successful result should look like:

![image3](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport3/Screen%20Shot%202022-05-08%20at%208.33.52%20PM.png?raw=true)

## **Setup Github Access from ieng6** 

this is dumb

asdasd