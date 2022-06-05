# Lab Report 5
## by Victor Wu

## **Overview** 
>Lab Partner with Sean Wang

In this lab report, we will be finding comparing differences between two different implementations 

## **Finding different results**

After running all the tests on both implementations, we needed a way to compare the differences between the results. We ran the tests on each implementation and stored the outputs into seperate files. After this, we ran `vimdiff` with the two files to highlight the differences.

Since there were so many differences, I selected two random tests to compare. 

[Link to test 482](https://github.com/vjwuUCSD/markdown-parser/blob/main/test-files/482.md)

[Link to test 483](https://github.com/vjwuUCSD/markdown-parser/blob/main/test-files/483.md)

## **Test 482**

The provided implementation for the lab produced a correct output. Our implementation of `MarkdownParser.java` did not.

### Outputs

Output for our implementation: ![image](https://raw.githubusercontent.com/vjwuUCSD/cse15l-lab-reports/main/LabReport5/Screen%20Shot%202022-06-04%20at%2010.59.15%20PM.png)

Output for provided implementation: ![image](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport5/Screen%20Shot%202022-06-04%20at%2010.59.24%20PM.png?raw=true)
### Expected

Expected output: [/uri]

![image](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport5/Screen%20Shot%202022-06-04%20at%2011.01.08%20PM.png?raw=true)

Reasoning:
Even though the link is not an actual link to a webpage, the `/uri` part of the `.md` file is still recognized as a link as seen above. This means `/uri` should be returned.

### How to fix our implementation

![tbchanged](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport5/Screen%20Shot%202022-06-04%20at%2011.02.19%20PM.png?raw=true)

The code snippet above shows the likely cause of the failure to return anything. Since our implementation used this to filter out some things that should not be returned, it caused more problems than it fixed. Since the link does not contain a `.com` or `.net`, `/uri` was not returned. By just removing this line, the implementation would likely be fixed for this situation.

## **Test 483**

The provided implementation for the lab produced a correct output. Our implementation of `MarkdownParser.java` did not.

### Outputs

Output for our implementation: ![image](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport5/Screen%20Shot%202022-06-04%20at%2010.59.35%20PM.png?raw=true)

Output for provided implementation: ![image](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport5/Screen%20Shot%202022-06-04%20at%2010.59.43%20PM.png?raw=true)
### Expected

Expected output: [./target.md]

![image](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport5/Screen%20Shot%202022-06-04%20at%2011.01.28%20PM.png?raw=true)

Reasoning:

Even though the link portion of the link is not a link and the text portion of the link is empty, it is still recognized as a link. Since the first part is empty and the second part contains a valid link, the result is empty as seen above. This means the `./target.md` should be considered a link in our parser.

### How to fix our implementation

![tbchanged](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport5/Screen%20Shot%202022-06-04%20at%2011.02.19%20PM.png?raw=true)

The same code snippet as before causes this issue for the same reason. Since our implementation used this to filter out some things that should not be returned, it caused more problems than it fixed. Since the link does not contain a `.com` or `.net`, `./target.md` was not returned. By just removing this line, the implementation would likely be fixed for this situation.
