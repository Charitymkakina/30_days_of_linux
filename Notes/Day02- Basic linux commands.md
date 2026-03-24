# Basic Linux Commands

# Using Nano text editor
Nano is a simple, text-based terminal editor.
Nano uses shortcuts at the bottom of the screen.
To save a file, `Ctrl+O`, then press `enter.`
To exit, `Ctrl+x.`

# File Permissions

To make the file a read-only file for everyone: `chmod 444 filename.txt.`

This means:
1. Owner- Read only
2. Group- Read only
3. User- Read only

# Linux File System Structure

In Windows, you have C:\ and D:\. In Linux, everything starts from the root `(/)`:

`/home/user`: Contains personal user files

`/etc`: contains system configuration files

`/bin`: Where essential command binaries live, such as `ls`, `mv`, `cp.`

# The Power Of Sudo

Sudo (SuperUser Do). lets you borrow that power for one command

`sudo apt update`- Update your package list

`sudo apt install git -y '. The "install" lets you install the tool, "-y" is you saying yes


