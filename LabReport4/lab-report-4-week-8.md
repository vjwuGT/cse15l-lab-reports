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

![test](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.17.55%20PM.png?raw=true)

### Reviewed code


> Test did not pass.

Output was:

![output](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.21.01%20PM.png?raw=true)

### My code

> Test did not pass

Output was:

![output2](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.21.22%20PM.png?raw=true)

**How can we fix this?**

This would likely not be a small code change as the issue gets very complicated when involving nested links. The current format of counting the indices of `"["`, `"]"`, `"("`, and `")"` gets extremely complicated when multiple of each are involved in a single link.

This would probably not be possible with just 10 line changes as a complete redesign would likely be necessary.

## **Snippet 3**
```
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)
```

A properly implemented `MarkdownParse.java` should return the link [https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule].

The test written was:

![test](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.17.55%20PM.png?raw=true)

### Reviewed code


> Test did not pass.

Output was:

![output](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.21.01%20PM.png?raw=true)

### My code

> Test did not pass

Output was:

![output2](https://github.com/vjwuUCSD/cse15l-lab-reports/blob/main/LabReport4/Screen%20Shot%202022-05-22%20at%209.21.22%20PM.png?raw=true)

**How can we fix this?**

This would likely not be a small code change as the issue gets very complicated when involving nested links. The current format of counting the indices of `"["`, `"]"`, `"("`, and `")"` gets extremely complicated when multiple of each are involved in a single link.

This would probably not be possible with just 10 line changes as a complete redesign would likely be necessary.