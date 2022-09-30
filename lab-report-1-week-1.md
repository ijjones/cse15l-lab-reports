**Part 1: Installing VScode**
* Visit [VScode Website](https://code.visualstudio.com/)
* Click blue download button on the top right corner
* Download for Windows or Mac depending on your system.

**Part 2: Remotely Connecting**
* Note: If you are on Windows install [OpenSSH](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui)
* To find your account go to [link](https://sdacs.ucsd.edu/~icc/index.php) and enter your username and PID.
* Once installed, open VScode and open the Terminal (Ctrl or Command + `)
* In the terminal, type

<pre><code>ssh cs15lfa22zz@ieng6.ucsd.edu
Note: replace zz with your specific account letters </code></pre>

* Enter your password. If you would like to reset your passowrd then visit [this link](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit)
* You will then be prompted by a message. In the terminal type **yes**.
* You are now connected remotely!

**Part 4: Trying Some Commands**
* Once you are in the server, try running some commands. Some useful commads are <code>ls pwd mkdir ls cp</code>

**Part 5: Moving Files With scp**
* You can copy files using <code>scp</code> also known as secure copy.
* In your terminal, type 
<pre><code>scp File Name cs15lfa22zz@ieng6.ucsd.edu:~/
Note: Replace zz with you specific letters 
</code></pre>
* Enter your password once prompted. 
* Check if your file is in the server by using <code>ls</code>
* If it is try running it by using <code>cat</code> followed by the file name in the terminal. 
* The file should now be copied.

**Part 6: Setting an SSH key**

**Part 7: Optimizing Remote Running**
