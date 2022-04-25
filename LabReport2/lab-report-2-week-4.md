# Lab Report 2 
## by Victor Wu
---
>Partner was Sean Wang

## **Overview**
`MarkdownParser.java` is a program that reads through a `.md` file and returns an ArrayList of all the links in the file. 

In the `MarkdownParser.java` file, we found three bugs and had to implement three changes to fix these bugs.

The three bugs were the following:

## **Image Links**
Example of the fix:
![fix1](https://raw.githubusercontent.com/vjwuUCSD/cse15l-lab-reports/main/LabReport2/Screen%20Shot%202022-04-24%20at%207.12.48%20PM.png)

[Test file](https://github.com/vjwuUCSD/markdown-parser/blob/6fd140a80f2225a18bf3fc9f5d86638bf9bb4fe2/test2-file.md?plain=1) that caused the error. The file contains one image link and one regular link.

Example of the output given the test file:
![output](https://raw.githubusercontent.com/vjwuUCSD/cse15l-lab-reports/main/LabReport2/Screen%20Shot%202022-04-24%20at%208.24.01%20PM.png)

The bug is that there the `MarkdownParser.java` file will read image links as regular links because of the similar implementation in markdown. 

This creates a symptom of image links being added to the ArrayList of links in the output. 

The failure inducing input contained in the [test file](https://github.com/vjwuUCSD/markdown-parser/blob/6fd140a80f2225a18bf3fc9f5d86638bf9bb4fe2/test2-file.md?plain=1) has an image link and will cause the program to print out the image link as a regular link. 

The change shown above reads the substring before the next instance of `"["` and checks if it is equal to `"!"` which is the difference between the declaration of an image link and regular link. If it is equal to `"!"`, the program will skip the entire link and move the index to the end parenthesis.



Infinite loop bug fix:
https://github.com/vjwuUCSD/markdown-parser/commit/9ea5e88df1167fccdc7e9264cb0cbf9ed2b91c72 
File with no link bug fix:
https://github.com/swang0222/markdown-parser/commit/a8a070cd126e900b856085930cc930f718615890
