**Secure File transfer Protocol**

SFTP is part of *SSH PROTOCOL* suite and shares the same *port 22* 

if enabled in the OpenSSH server configuration, you can connect ussing command such as  `sftp username@hostname ` once logged in, you can issue coomands such as ` get filename` and `put filename` to *download and upload files* 

SFTP should not be confused with FTPS. You are right to think that FTPS stands for File Transfer Protocol Secure. How is FTPS secured? Yes, you are correct to estimate that it is secured using TLS, just like HTTPS. While FTP uses port 21, FTPS usually uses port 990. It requires certificate setup, and it can be tricky to allow over strict firewalls as it uses separate connections for control and data transfer.

Setting up an SFTP server is as easy as enabling an option within the OpenSSH server. Like HTTPS, SMTPS, POP3S, IMAPS, and other protocols that rely on TLS for security, FTPS requires a proper TLS certificate to run securely.