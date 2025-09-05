*Secure shell*

its similar to [[Telnet]] but secure 

its convinient to use telnet to communicate on a remote sistem but its risky when all the traffic is sent in clear text.

*OpenSSH*  offres serveral benefits

- *Secure authentication* ssh **supports public key and two factor authentication** 

- *confidentiality* OpenSSH provides end-to-end encryption, protecting against eavesdropping. Furthermore, it notifies you of new server keys to protect against man-in-the-middle attacks.

- *Integrity*: In addition to protecting the confidentiality of the exchanged data, cryptography also protects the integrity of the traffic.

- *Tunneling* : SSH can create a secure “tunnel” to route other protocols through SSH. This setup leads to a VPN-like connection.

- *X11 Forwarding* : If you connect to a Unix-like system with a graphical user interface, SSH allows you to use the graphi

You would issue the command ssh username@hostname` to connect to an SSH server. If the username is the same as your logged-in username, you only need `ssh hostname`. Then, you will be asked for a password; however, if public-key authentication is used, you will be logged in immediately.

The screenshot below shows an example of running Wireshark on a remote Kali Linux system. The argument `-X` is required to support running graphical interfaces, for example, `ssh 192.168.124.148 -X`. (The local system needs to have a suitable graphical system installed.)

![After establishing an SSH connection to a remote server, we successfully started Wireshark, an application with a graphical user interface.](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/5f04259cf9bf5b57aed2c476-1721903514417.png)

While the *TELNET server listens on port 23, the SSH server listens on port 22.*