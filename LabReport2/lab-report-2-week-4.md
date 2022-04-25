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

### **Explanation of bug, symptom, and input**

The bug is that there the `MarkdownParser.java` file will read image links as regular links because of the similar implementation in markdown. 

This creates a symptom of image links being added to the ArrayList of links in the output. 

The failure inducing input contained in the [test file](https://github.com/vjwuUCSD/markdown-parser/blob/6fd140a80f2225a18bf3fc9f5d86638bf9bb4fe2/test2-file.md?plain=1) has an image link and will cause the program to print out the image link as a regular link. 

The change shown above reads the substring before the next instance of `"["` and checks if it is equal to `"!"` which is the difference between the declaration of an image link and regular link. If it is equal to `"!"`, the program will skip the entire link and move the index to the end parenthesis.

## **Text after the last link**

Example of the fix:
![change](https://raw.githubusercontent.com/vjwuUCSD/cse15l-lab-reports/main/LabReport2/Screen%20Shot%202022-04-24%20at%208.55.50%20PM.png)

[Test file](https://github.com/vjwuUCSD/markdown-parser/blob/7806b22acdf41e0f9153f9389279ffd4ce432c41/test3-file.md?plain=1) that caused the error. The file has a header after the last link.

Example of the output given the test file:
![broken](https://raw.githubusercontent.com/vjwuUCSD/cse15l-lab-reports/main/LabReport2/Screen%20Shot%202022-04-24%20at%209.01.34%20PM.png)
### **Explanation of bug, symptom, and input**
The bug is that the program is stuck in a while loop based off of the length of the entire markdown file. However, the loop only ends when the variable `currentIndex` is equal or greater than the length of the markdown file. Since `currentIndex` can only reach the index of the last `")"`, this implementation is bugged.

When the last line is not a properly implemented link, the symptom will be throwing a `java.lang.OutOfMemoryError`.

The failure inducing input contained in the [test file](https://github.com/vjwuUCSD/markdown-parser/blob/7806b22acdf41e0f9153f9389279ffd4ce432c41/test3-file.md?plain=1) has a line at the end of the program that is not a link which lets the program run into the bug and show the symptom.

The change that was implemented is to instead run the while loop to the `markdown.lastIndexOf(")")` so the program will stop at the parenthesis instead. This change is not perfect but will work for most cases.

## **File with no link bug fix:**

Example of the fix:
![change](https://raw.githubusercontent.com/vjwuUCSD/cse15l-lab-reports/main/LabReport2/Screen%20Shot%202022-04-24%20at%209.16.46%20PM.png)

[Test file](https://github.com/vjwuUCSD/markdown-parser/blob/main/my%20test%20files/test4-file.md?plain=1) that caused the error. There are no links so the file will break.

Example of the output of given test file:
![output](https://raw.githubusercontent.com/vjwuUCSD/cse15l-lab-reports/main/LabReport2/Screen%20Shot%202022-04-24%20at%209.32.14%20PM.png)
The error is that the program is stuck on this output and is in an infinite loop.

### **Explanation of bug, symptom, and input**

This is an example of different bugs causing the same symptoms. In this case, the bug is that there are no links in the file and the program is constantly trying to read up to the next link. Since `currentIndex` will never change, it will always be less than `markdown.length`.

The symptom is that the program will never conclude running and will be stuck on an infinite loop which was the same symptom as the bug above. 

However, the failure inducing input [test file](https://github.com/vjwuUCSD/markdown-parser/blob/main/my%20test%20files/test4-file.md?plain=1) was instead a file that contained no links at all. 

The solution to this fix can be solved in many ways. My lab partner Sean's solution was to create an `if` statement that would return the empty ArrayList if `"["` and `"]"` were not in the file. While not a perfect implementation, it would solve the issue in this case. My implementation from the bug above would also coincidentally solve this bug.


