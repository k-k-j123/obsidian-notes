## DNS (Domain name system):

- It is a Program that does the work of mapping Domain Names to Ip addresses.
- The Process of DNS mapping is Done as follows
	1. The user passes the host name to a file transfer client
	2. the file transfer client sends the domain name to DNS Client which stores the IP of the DNS server.
	3. The DNS client queries the DNS server with the domain name 
	4. The DNS server returns the Ip address of the required Domain Name to DNS client
	5. the DNS client forwards to the IP to the File transfer client and file transfer client uses this IP to communicate with the website (file transfer server).
		![[DNS CLIENT SERVER.png]]

## Name Space:
A name space is a system that maps addresses to unique names. There are two ways to organize a name space:
1. Flat Name Space
    Assigns a single, unstructured name to each address
    Names may or may not have a common structure
    Not suitable for large-scale use (e.g., internet) due to potential duplication

2. Hierarchical Name Space
    Organizes names into a structured hierarchy
    Each part of the name defines a specific level:
        First part: Nature or organization
        Second part: Organization name
        Third part: Department or sub-organization
	`eg- pune.com, nashik.com etc`

## Domain Name Space:
The domain name space is a hierarchical system used to identify and organize domain names on the internet. It's like a phone-book for websites!
1. Fully Qualified Domain Name:
	- If a label is terminated by a null string it is called as Fully qualified domain name 
	- A FQDN is a complete domain name for a specific computer or host on the internet FQDN contains full name and label of a host 
	- eg - unipune.ac.in pcccs.org
2. Partially Qualified domain name:
	- IF a label is not terminated by a null string it is called a partially qualified domain name 
	- A PQDN starts from a node but does not reach the root
	- for eg- Unipune
3. Domain Name:
	- A Domain name is a subtree of Domain name space
	- the name of a domain is the domain name of the node at the top of the subtree
	- A domain may be divided int sub domain
	- Two Types of Domain Names:
	    Generic  Domains (gTLDs)
	        These are domain names that are not specific to any country or region.
	        Examples:
	            .com (commercial)
	            .org (organization)
	            .net (network)
	            .edu (education)
	    Country Domains (ccTLDs)
	        These are domain names specific to a country or region.
	        Examples:
	            .in (India)
	            .us (United States)
	            .uk (United Kingdom)
	            .au (Australia)

## Email:
Email or electronic mail is a communication system that allows us to transfer messages through internet.
the email architecture consists of four scenarios.
1. Both sender and receiver connected to the same system:-
		In this the sender and receiver are connected to the same system. The sender composes the mail using its user agent and sends it to receivers mail box .
2. Both sender and receiver are connected to different systems.
		In this the sender and receiver are connected to different systems which in turn are connected through internet.
		here the sender uses its UA to create a message and an MTA(Message transfer agent) is used to send the message to the receivers system through internet. the receiver then uses its MTA client to receive the message and it is stored in receivers mail box
3. Sender is remote user.
		In this case the sender is not directly connected to the mail server system instead it uses LAN or WAN to access the system.Sender uses its UA to create a message. then an MTA client establishes a connection with the MTA server at Receivers side. The receivers server receives it and stores it in receivers mail box. 
4. Both are remote users.
		here both sender and receiver are remotely connected to mail system through LAN or WAN. the message is again created by UA and sent to the receivers mail system through MTA client however once message is stored on receivers mail box it cannot be accessed directly it is accessed using MAA (Mail access agent) the receiver uses this MAA to retrieve the message from the mail server 


> [!NOTE] Functions of User Agent
> - Composing Messages
> - Reading Messages
> - Replying to messages
> - Forwarding messages
> - Handling Messages
>

## MIME (Multipurpose Internet mail extensions):
It is a protocol that allows non-ASCII data to be sent through email by default email can only send NVT 7-bit ASCII hence it cannot be used for languages like Hebrew,Chinese,Japanese also it cannot be used for video , audio or binary files.
MIME transforms the non-ascii data at the senders site to NVT ASCII and delivers it to the client MTA to be sent through internet. 
Similarly MIME can convert the NVT ASCII back to its non ascii format at the receivers site 
MIME header :- mime header is inserted at the beginning of any email transfer MIME defines 5 header namely
- MIME version-- this defines version of mime protocol
- Content-type-- header defines type of data used in the body of message 
- content-type-encoding-- defines the method used for encoding body of the message
- content-id--header is used to uniquely identify the whole message in a multiple message environment 
- content-description-- defines weather the body is actually image video or audio

## SMTP (simple mail transfer protocol):
the protocol that defines the communication between MTA client and MTA server is called simple mail transfer agent.
it is a tcp protocol that specified how computers exchange electronic mail. smtp is used twice between senders and receivers mail server and between the two mail servers
smtp uses commands and responses to transfer messages between MTA client and MTA server commands are sent by client to server command consist of a keyword followed by zero or more arguments responses are sent from server to client

## POP3 & IMAP:
smtp is used in first and second stage of mail delivery it is a push protocol it pushes message from the client to the server the third stage needs a pull protocol from receiver to mail server the third stage uses a mail access agent now two message access protocol are available POP3 and IMAP.
**POP3 :**- is an application protocol used by local email clients to retrieve mail from a remote sever over a tcp connection 
pop supports simple download and delete requirement for access to remote mailboxes it uses 110 port. Mail access starts with client when the user wants to access email from the mail server to mailbox client opens a tcp connection on port 110 it then sends its username and password to access the mail box user can then retrieve the mail messages
it has two modes delete mode and keep mode in delete mode the mail is deleted after each retrieval in keep mode the mail remains in the mailbox after retrieval 
**IMAP** :- imap stands for Internet mail access protocol it is similar to POP3  but is more powerful and more complex. POP3 not allows the user to organize mail on the sever the user cannot have different folders on the server POP3 also does not allows to partially check the content of mail before downloading. All these drawbacks are overcome in IMAP
in IMAP user can check email header before downloading
*user can search the content of the email for a specific string of character before downloading*
*user can partially download an email* 
*a user can create delete or rename mailboxes on the mail server* 
*user can create a hierarchy of mailboxes in a folder storage*

## FTP:
FTP stands for File Transfer Protocol. It is a standard network protocol used to transfer files between a local computer and a remote server over the internet.
1. **Establishing a Connection**
- A user initiates an FTP session by opening an FTP client (e.g., FileZilla) and entering the host name or IP address of the remote server.   
- The client establishes a connection to the server on port 21 (the default FTP port).

2. **Authentication**
- The server prompts the user to log in with a username and password.
- The client sends the login credentials to the server
- The server verifies the credentials and grants access if they are correct.

3. **Command Channel**
- Once authenticated, a command channel is established between the client and server.
- The client sends FTP commands (e.g., `LIST`, `GET`, `PUT`) to the server through this channel.
-
4. **Data Transfer**
- When a file transfer is requested, a separate data channel is opened between the client and server.
- The server sends the requested file to the client through this data channel.
- The client receives the file and saves it locally.
    
5. **Closing the Connection**
- When the file transfer is complete, the data channel is closed.
- The client can issue more commands or terminate the session.
- The server closes the connection when the session is terminated.
