# Installation process
This repository documents the step-by-step process I use to install Kali Linux and Ubuntu on Oracle VirtualBox.
It also includes system requirements, configurations, and troubleshooting steps I encountered.

# Prerequisites
Before installation, ensure you have:
1. Oracle VirtualBox installed
2. VirtualBox Extension Pack
3. At least 8 GB RAM (recommended)
4. 50 GB free disk space
5. ISO / Pre-built VM files downloaded

# Kali Linux installation steps
Visit the official Kali Linux page and download the VirtualBox image. After unzipping the file, there are .vbox, .vdi, and .vbox files. I will be using the .vdi file.

# VirtualBox
- Click New in VirtualBox
  
- Name: Kali Linux
  
- Type: Linux/ Version: Debian (64-bit)
  
- Memory: Set to at least 2048mb
  
- Hard disk: This is the crucial step: Select "use an existing virtual hard disk file."
  
- Link the. Vdi file:
  
  1. Click the small folder icon next to the drop-down menu
  2. Click " Add " at the top
  3. Navigate into your kali-linux.2025.4-virtualbox-amd64 folder
  4. Select the file ending with .vdi
  5. Click Open, choose, and finally create.

Tip: Before starting your machine, always go back and review your system settings and make any adjustments where you feel they're needed.

# Ubuntu Installation
1. Download Ubuntu ISO
2. Download Ubuntu Desktop LTS ISO from the official website

# Create New Virtual Machine
1. Open VirtualBox
2. Click New
   
Name: Ubuntu

Type: Linux

Version: Ubuntu (64-bit)

3. Allocate Resources
Recommended:

RAM: 4096 MB

CPU: 2 processors

Disk: 25–50 GB (VDI, Dynamically allocated)

4. Attach ISO File
   
Go to Settings → Storage

Under Controller IDE → Add ISO

Select the Ubuntu ISO file

6. Start Installation
  
7. Click Start
   
8. Select Install Ubuntu
   
Choose:

Keyboard layout

Normal installation

Erase disk & install Ubuntu (Virtual disk only)

# Create User Account
Set: Username and Password
Computer name

Complete Installation

Wait for the installation to finish

Restart VM

Remove ISO when prompted
