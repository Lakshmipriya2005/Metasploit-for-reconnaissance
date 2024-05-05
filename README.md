# EXP.NO:05
# DATE:

# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

## Step 2:
Investigate on the various categories of tools as follows:

## Step 3:
Open terminal and try execute some kali linux commands

## Step4: 
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## PROGRAM:
Find out the ip address of the attackers system

## OUTPUT:
![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/f1e503de-3180-4bcf-b7ee-465d18284833)


## Invoke msfconsole:
## OUTPUT:
![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/a5910b23-34ee-4de3-9024-7c449304f4b7)


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/4c8c5284-f372-4efb-bc7e-f3ced81b159c)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/cadb47ce-e16a-4414-aa12-806bfb675db6)


## OUTPUT:
![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/24c11b6c-3806-47ce-9451-e18365478d75)


Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/adf159ba-90c8-465f-a4a5-17bbeed7a20d)

![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/81893844-cac8-4197-9ad7-66324c0a0285)


Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/b2c2e737-483a-42ae-9189-d2f5984cb960)

The info command provides information regarding a module or platform

## OUTPUT:
![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/50fef82f-24cc-488a-800d-eadea2e57128)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address> 

![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/7ae76a37-ab78-46d4-8585-ac2a65b1f372)


Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/7c6625e9-5855-49a5-bcce-2a941b8000cf)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/1df789c6-1c31-4d52-8962-fca3b3d25907)


Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/be445d81-bae0-40a4-b770-1adf09ee1f8b)


After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/9a190717-5e24-45d6-ab92-e091e93fef1e)



set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/Lakshmipriya2005/Metasploit-for-reconnaissance/assets/115525361/3ebbdc76-ec11-4793-98e8-d59b0e826e77)




## RESULT:
The Metasploit framework for reconnaissance is examined successfully

