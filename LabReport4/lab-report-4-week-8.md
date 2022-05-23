# Lab Report 3
## by Victor Wu


## **Repositories used**

[Link to my repository](https://github.com/vjwuUCSD/markdown-parser)

[Link to the reviewed repository](https://github.com/ayushs2725/markdown-parser.git)

## **Snippet 1**
```
`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)
```

A properly implemented `MarkdownParse.java` should return the links [`google.com, google.com, ucsd.edu].

The test written was:

![test](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.09.34%20PM.png?raw=true)


### Reviewed code


> Test did not pass.

Output was:

![output](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.09.56%20PM.png?raw=true)

### My code

> Test did not pass

Output was:

![output2](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.10.32%20PM.png?raw=true)

**How can we fix this?**

There is likely a small change that could fix this error. An idea that could be tested would be to count the amount of backticks there are and keep a running total. If the current total of backticks is on an odd number prior to the first `"["` in a link, the link should be ignored if another backtick occurs anywhere before the last `")"` in the link. This should be able to track what elements are wrapped in code blocks.

This would could potentially be done in less than 10 lines as the code to track the current index is already existing. 
However, the issue could be more complicated and could take more lines after thorough testing.

## **Snippet 2**
```
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \] (example.com)
```

A properly implemented `MarkdownParse.java` should return the links [`a.com, a.com(()), example.com].

The test written was:

![test](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.09.34%20PM.png?raw=true)

### Reviewed code


> Test did not pass.

Output was:

![output](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.09.56%20PM.png?raw=true)

### My code

> Test did not pass

Output was:

![output2](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.10.32%20PM.png?raw=true)

**How can we fix this?**

This would likely not be a small code change as the issue gets very complicated when involving nested links. The current format of counting the indices of `"["`, `"]"`, `"("`, and `")"` gets extremely complicated when multiple of each are involved in a single link.

This would probably not be possible with just 10 line changes as a complete redesign would likely be necessary.