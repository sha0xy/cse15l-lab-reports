# Lab Report 1

***This lab report is a tutorial to log into a course-specific account on `ieng6`.***


> ## Steps

* **Install VSCode**

    Go to [Visual Studio Code website](https://code.visualstudio.com/) to download and install the right version of VSCode. Open VSCode when installed and it should look like this.![Image][1]

    [1]: images/VSCode.png
   
* **Connect Remotely**  

    If you are using Windows, first [install OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse). 
    
    Then, check your course specific account [here](https://sdacs.ucsd.edu/~icc/index.php).   
    
    Next, we will connect to the remote computer. Open a new terminal in VSCode and enter the following command. Replace the `zz` with your own account.  
   
    `$ ssh cs15lwi22zz@ieng6.ucsd.edu`

    Enter your password, and you are logged in. If you succeed, it should look like this:

    ![Image][2]

    [2]: images/Connect.png

* **Try Some Commands**

    Try running some commands both on your computer and on the remote computer after ssh-ing.

    Here are some recommended commands to try:  
    1. `cd ~`  
    2. `cd`  
    3. `ls -lat`  
    4. `ls -a`  
    5.  `cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/`
    6. `cat /home/linux/ieng6/cs15lwi22/public/hello.txt`

    Some examples:
    ![Image][3]
    ![Image][4]

    [3]: images/Commands1.png
    [4]: images/Commands2.png

* **Moving Files with `scp`**

    The command `scp` can be used to copy a file from the client to the server.

    Create a file named `WhereAmI.java` on your computer and enter the following contents.

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

    Run it on your computer with `javac` and `java`.

    Then, run this command (with your own account)

    `scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/`

    Enter the password and you are logged in. Use `javac` and `java` to run it again on the server.

    It should look like this:
    ![Image][5]
    ![Image][6]
    ![Image][7]

    [5]: images/scp1.png
    [6]: images/scp2.png
    [7]: images/scp3.png


* **Setting an SSH Key**

    We can set an SSH key to avoid entering the password all the time. We use a program called `ssh-keygen`.

    Run the commands like this:
    ```
    # on client (your computer)
    $ ssh-keygen
    Generating public/private rsa key pair.
    Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
    Enter passphrase (empty for no passphrase): 
    Enter same passphrase again: 
    Your identification has been saved in /Users/joe/.ssh/id_rsa.
    Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
    The key fingerprint is:
    SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
    The key's randomart image is:
    +---[RSA 3072]----+
    |                 |
    |       . . + .   |
    |      . . B o .  |
    |     . . B * +.. |
    |      o S = *.B. |
    |       = = O.*.*+|
    |        + * *.BE+|
    |           +.+.o |
    |             ..  |
    +----[SHA256]-----+
    ```

    If you use Windows, follow `ssh-add` [here](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation).

    If you succeed, it should look like this:
    
    ![Image][8]
    ![Image][9]

    [8]: images/SSH1.png
    [9]: images/SSH2.png
    
* **Optimizing Remote Running**

    There are some more ways to optimize remote running experience.

    Here are some examples: 
    
    1. Write a command in quotes at the end of `ssh` command.
    
        `ssh cs15lwi22@ieng6.ucsd.edu "ls"`

    2. Use semicolons to run multiple commands on the same line.

        `cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`

    3. Use up-arrow on the keyboard to recall the latest command that was run.  
    
    **An Example: `ssh` using cse15l account and exit.**
    
    - Type the command in hand
    
    `ssh cs15lwi22aor@ucsd.ieng6.edu (return)`. 
    `exit (return)`. 
    
    Keystroke count: 36
    
    - Using up-arrow the next time sshing
    
    `(up-arrow)(return)`. 
    `(up-arrow)(return)`. 
    
    Keystroke count : 4
    
    As the example shows, it can save a lot of time by using up-arrow.  

    The examples above should look like this:
    ![Image][11]

    [11]: images/Optimize.png
      
  
***-End of Lab Report 1-***
