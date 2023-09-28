
- The `MSF` is distributed by `Rapid7` and can be downloaded and installed as a standalone package on both Windows & Linux.

- In this course we will be utilizing the Metasploit Framework on Linux and our preferred distribution of choice is Kali Linux.

- `MSF` and its required dependencies come pre-packaged with Kali Linux which saves us from the tedious process of installing `MSF` manually.

### The `MSF` Database

+ The Metasploit Framework Database (`msfdb`) is an integral part of the Metasploit Framework and is used to keep track of all your assessments, host data scans etc.

+ The Metasploit Framework uses PostgreSQL as the primary database server, as a result, we will also need to ensure that the PostgreSQL database service is running and configured correctly.

+ The Metasploit Framework Database also facilitates the importation and storage of scan results from various third party tools like `Nmap` and `Nessus`.

### Installation Steps

+ Update our repositories and upgrade our Metasploit Framework to the latest version. 
+ Start and enable the PostgreSQL database service. 
+ Initialize the Metasploit Framework Database (`msfdb`). 
+ Launch `MSFconsole`! 

- Command to run the `msfd` utility `sudo msfdb`
- Setup and initialize the Metasploit Framework database with `sudo msfdb init`
- Check the status with `sudo msfdb status` 
- Start `msfconsole`
- Check the connection to the databse `db_status`

