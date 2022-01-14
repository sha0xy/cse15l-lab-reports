# Lab Report 1

***This lab report is a tutorial to log into a course-specific account on `ieng6`.***


> ## Steps
***

* Install VSCode  

    Go to Visual Studio Code website [https://code.visualstudio.com/][1] to download and install the right version of VSCode. Open VSCode when installed, and it should look like this.![Image][2]

    [2]: images/VSCode.png
   
    [1]: https://code.visualstudio.com/

* Connect Remotely  

    If you are using Windows, first [install OpenSSH][3]. 
    
    Then, check your course specific account [here][4].   
    
    Next, we will connect to the remote computer. Open a new terminal in VSCode and enter the following command. Replace the `zz` with your own account.  
   
    `$ ssh cs15lwi22zz@ieng6.ucsd.edu`

    Enter your password, and you are logged in. If you succeed, it should look like this:

    ![Image][5]

    [5]: images/Connect.png
    [4]: https://sdacs.ucsd.edu/~icc/index.php

    [3]: https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse

* Try Some Commands

    Try running some commands both on your computer and on the remote computer after ssh-ing.

    Here are some recommended commands to try:  
    1. `cd ~`  
    2. `cd`  
    3. `ls -lat`  
    4. `ls -a`  
    5.  `cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/`
    6. `cat /home/linux/ieng6/cs15lwi22/public/hello.txt`

* Moving Files with `scp`

    The command `scp` can be used to copy a file from the client to the server.