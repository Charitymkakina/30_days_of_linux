# Creating and navigating directories
1. To create a directory 

Command: `mkdir ~/project.`

2. To change directory: cd ~/project

Command: `cd~/project

3. To create a new file

Command: `touch example.txt.`

4. Verify file creation

command: `ls.`

# Changing Ownership of a File
1. Checking the current ownership of the file

Command: `ls -l.`

Output:` -rw-rw-r--1 charity charity 0 feb 16 16:01 example.txt.`

Meaning: `(-rw-rw-r--1)` represents the file permissions.

         `(1st charity)` represents the current owner of the file
         
         `(2nd charity)` represents the current group of the file.
         
         `(0)` represents the file size in bytes.
         
         `(feb 16 16:01)` represents the last modified date and time.
         
2. To change the user and group, we create a user and group first, since they don't exist on my machine

3. To create a group: `sudo groupadd developer.`

4. To create user: `sudo useradd -g developer labby.`
   
5. To change the ownership of a file: `sudo chown labby: developer example.txt.`
   
6. Verifying the changes: `ls -l.`

Output: `-rw-rw-r--1 labby developer 0 feb 16 16:01 example.txt.`

# Changing Ownership of a Directory
1. Create a new directory with some files

command: `mkdir -p new-dir/subdir.`

         `echo "Hello, world" > new-dir/file1.txt.`
         
         `echo "Another file" > new-dir/subdir/file2.txt.`
         
Verify: `ls -R new-dir.`

2. Changing ownership:

Create the user first: `sudo useradd -g group1 user1.`

Create the group: `sudo groupadd group1.`

changing ownership: `sudo chown -R user1:group1 new-dir.`

Verifying: `ls -l new-dir.`

# Changing the permissions of a file

- In Linux, file permissions are represented by a series of letters or numbers.

- Understanding the permissions is vital for securing your files and preventing unauthorized access
  
Command: `ls - l example.txt.`

Output: `-rw-rw-r--1 labby developer 0 feb 16 16:01 example.txt.`

Command:`sudo chmod 700 example.txt.`

Output: `-rwx------ 1 charity charity 0 Feb 16 16:06 example.txt.`

2. Changing the Permission of a Directory

Command: `mkdir ~/test-dir.`

Command: `chmod 700 ~/test-dir.`

Verification: `ls -ld ~/test-di.r.`

Output: `drwx-------2 charity charity 4096 feb 16 21:17.`

Command: `chmod -R 755 ~/test-dir.`

Verification: `ls -ld ~/test-dir.`

`Output: drwxr-xr-x 2 charity `charity 4096 feb 16 21.17`

Using Symbolic Notation for Permissions

-Symbolic notation can be more intuitive, especially when you only want to change a single permission. 

Symbolic notation uses letters to represent the user group and others, and operators to add or remove permissions.

- We will first create a new script file with some content

Command: `cd ~/project.`

Command: `echo '#!/bin/bash\necho "Hello, world"' > script.sh.`

Verification: `ls -l script.sh.`

Output: `-rw-rw-r--1 charity charity 33 feb 16 21:25 script.sh.`

Test: ./script.sh

Output: permission denied

Command: chmod u+x script.sh

Verification: ls -l script.sh

Output: -rwxrw-r--1 charity charity 33 feb 16 21:25 script.sh

Test: ./script.sh

Output: Hello, world



