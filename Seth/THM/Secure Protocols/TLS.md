
opera en *OSI TRANSPORT LAYER*

1. for a client o server who wants to identify itself is to get a signed TLS certificate.

generally the server administrator creates a certificate signing request *(csr)* and submits it to a certifica authority *(CA)* ; the Ca verifies CSR and issues a digital certificate

2. Once the *signed* certificate is recived, it can be used to identify the server (or client) to others who can confirm he validity of the signature. For a host to confirm the validity of a signed certificate, the certificates of the signing authorities needs to be installed on the host in the no digital world.

![[Pasted image 20250823183300.png]]