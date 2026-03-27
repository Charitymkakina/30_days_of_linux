# Creating Files and Directories
1. Create an empty file
The touch command is used to create an empty file. If the file already exists, it updates the file's timestamp without changing its content.
Command: `touch file1.txt.`

2. Create a file with content
command: `echo "Learning Linux is fun!" > file2.txt.`
The command does 2 things: `echo- prints text`, and `>` redirects the output of echo into a file named file2.txt.

3. Create a hidden file
`echo "Hidden file" > .hiddenfile`
Creates a hidden file in Linux; any file or directory name that starts with a dot (.) is considered hidden

4. Create a directory
`mkdir testdir` Creates a new directory named testdir

# Listing Files and Directories
1. Basic Listing
`ls.`
Displays files and directories in your current location

2. Long listing format
`ls -l` provides a "long" format listing.

 You see additional details like file permissions (drwr-xr-x), owner, size, and modification date

3. Show hidden files
`ls -a`
Shows all files, including the hidden file.

`ls -la`
Shows all files in long format

`ls -l testdir`
Displays the contents of a directory. If nothing appears, the directory is empty

# COPYING FILES AND DIRECTORIES
1. Copy a file
`cp file1.txt file_copy.txt`

Creates a duplicate of file1.txt.

2. Copy of a file to a directory
`cpfile2.txt testdir/.`

Copies file2.txt into testdir.

# Copy a directory 
`cp -r testdir testdir_copy.`

(The -r stands for recursive; it's necessary when copying directories to ensure all contents are copied).




