# Lab Report 5

***This lab report is a discussion of two different test results from my markdown parse repository and given markdown parse repository***

***

**Find tests with different results**

- To find tests with different result, I first save the test results in result.txt using the command `bash script.sh > results.txt`. Then, use `diff` to find the differences in the results. This is part of the outcome of `diff` command:

    ![Image](images/diff.png)

***

**Test 1 that has different results**
- This is a screenshot of the test file: 

    ![Image](images/test1.png)

- This is a screenshot of result from my implementation:  

    ![Image](images/test1myimpl.png)

- This is a screeshot of the result from given implementation: 

    ![Image](images/test1givenimpl.png)

- The expected result is `[/bar\* "ti\*tle"]`

- My implement is correct.

- The given implement is incorrect. It excludes all the links with spaces while sometimes links may be valid even with spaces. To fix the problem, it should check whether the spaces will invalidate the link and then decide to exclude the link or not. This is the screenshot of the part of the code needed to be fixed:

    ![Image](images/test1fix.png)

***

**Test 2 that has different results**
- This is a screenshot of the test file: 

    ![Image](images/test2.png)

- This is a screenshot of result from my implementation:  

    ![Image](images/test2myimpl.png)

- This is a screeshot of the result from given implementation: 

    ![Image](images/test1givenimpl.png)

- The expected result is `[]`

- My implement is incorrect. It fails to detect the space in link (stuff in the parenthesis) and include an invalid link in the output. There should be some code checking for spaces after the index of open parenthesis and before the index of close parenthesis. This is the screenshot of the part of the code needed to be fixed:

    ![Image](images/test2fix.png)

***

***-End of Lab Report 5-***