Python3's *"HTTPServer" will serve the files in the directory where you run the command*, but *this can be changed* by providing options that can be found within the manual pages. Simply, all we need to do is run `python3 -m  http.server` in the terminal to start the module! In the snippet below, we are serving from a directory called "webserver", which has a single named "file".

**Using Python to start a web server**

![[Pasted image 20250822213426.png]]
        

Now, let's *use `wget` to download the file* using the *MACHINE_IP* address and the *name of the file*. Remember, because the *python3 server is running port 8000*, you will need to specify this within your wget command. For example:

![[Pasted image 20250822213526.png]]

**An example wget command of a web server running on port 8000**



Note, you will need to open a new terminal to use `wget` and leave the one that you have started the Python3 web server in. This is because, once you start the Python3 web server, it will run in that terminal until you cancel it.

Let's take a look in the snippet below as an example:

Downloading a file from our webserver using wget

![[Pasted image 20250822213554.png]]
Using Python to start a web server



**Remember**, you will need to run the wget command in another terminal (while keeping the terminal that is running the Python3 server active). An example of this on the TryHackMe AttackBox is below:

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5c549500924ec576f953d9fc/room-content/14de6e0470d50317f3b24f4f9aa9297a.png)  
