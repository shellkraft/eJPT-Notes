
- The Metasploit Framework (MSF) is an open-source, robust penetration testing and exploitation framework that is used by penetration testers and security researchers worldwide.

- It provides penetration testers with a robust infrastructure required to automate every stage of the penetration testing life cycle.

- It is also used to develop and test exploits and has one of the world's largest database of public, tested exploits.

- The Metasploit Framework is designed to be modular, allowing for new functionality to be implemented with ease.

- The Metasploit Framework (MSF) source code is available on GitHub. Developers are constantly adding new exploits to the framework.

### History of `MSF`

+ Developed by HD Moore in 2003 
+ Originally developed in Perl 
+ Rewritten in Ruby in 2007 
+ Acquired by Rapid7 in 2009
+ Metasploit 5.0 released in 2019 
+ Metasploit 6.0 released in 2020 

### Metasploit Editions

+ Metasploit Pro (Commercial)

+ Metasploit Express (Commercial)

+ Metasploit Framework (Community)

### Essential Terminologies 

+ Interface — Methods of interacting with the Metasploit Framework.

+ Module - Pieces of code that perform a particular task, an example of a module is an exploit.

+ Vulnerability - Weakness or flaw in a computer system or network that can be exploited.

+ Exploit - Piece of code/module that is used to take advantage a vulnerability within a system, service or application.

+ Payload - Piece of code delivered to the target system by an exploit with the objective of executing arbitrary commands or providing remote access to an attacker.

+ Listener — A utility that listens for an incoming connection from a target. 

### Metasploit Framework Interfaces

+ The **Metasploit Framework Console (MSFconsole)** is an easy-to-use all in one interface that provides you with access to all the functionality of the Metasploit Framework.

- The **Metasploit Framework Command Line Interface** (MSFcli) is a command line utility that is used to facilitate the creation of automation scripts that utilize Metasploit modules.
	+ It can be used to redirect output from other tools in to `msfcli` and vice versa.
	+ `MSFcli` was discontinued in 2015, however, the same functionality can be leveraged through the `MSFconsole`.

- **Metasploit Community Edition** is a web based GUI front-end for the  Metasploit Framework that simplifies network discovery and vulnerability identification. 

- **Armitage** is a free Java based GUI front-end for the Metasploit Framework that simplifies network discovery, exploitation and post exploitation. 