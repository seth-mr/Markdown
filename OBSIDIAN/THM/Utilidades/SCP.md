
(SECURE COPY PROTOCOL)

-  Copy files & directories from your current system to a remote system
- Copy files & directories from a remote system to your current system

SCP is just that means *secure copyng files*
Unlike the cp command, this comman allows us to *transfer files between two computers using SSH* 
to provide both *autentication and encryptation*


## copyng files

### from our machine to  a remote
Provided that we know usernames and passwords for a user on your current system and a user on the remote system. For example, let's *copy an example file from our machine to a remote machine*, which I have neatly laid out in the table below:

| **Variable**                                                | **Value**       |
| ----------------------------------------------------------- | --------------- |
| The IP address of the remote system                         | 192.168.1.30    |
| User on the remote system                                   | ubuntu          |
| Name of the file on the local system                        | important.txt   |
| Name that we wish to store the file as on the remote system | transferred.txt |
`scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt`

### copy a file from a remote computer 
 now let's reverse this and layout the syntax for using scp to *copy a file from a remote computer that we're not logged into*

|   |   |
|---|---|
|**Variable**|**Value**|
|IP address of the remote system|192.168.1.30|
|User on the remote system|ubuntu|
|Name of the file on the remote system|documents.txt|
|Name that we wish to store the file as on our system|notes.txt|

The command will now look like the following: `scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt`

### Serving Files From Your Host

usually linux machines come pre-packaged with *python 3* this situation allow us to use a module called *HTTPServer* this module turns your computer into a quick web server that you can use to serve your files.

this files can be downloaded by another computing using *curl* abd *wget*

[[wget y scp]]
