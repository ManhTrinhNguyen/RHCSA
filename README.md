# RHCSA

- [File System](#File-System)

- [Directory Listing Attribute](#Directory-Listing-Attribute)

- [Create file and Dir](#Create-file-and-Dir)

- [File maintainence command](#File-maintainence-command)

- [Soft link and hard link](#Soft-link-and-hard-link)

## Access the CLI 

To get an IP Address : `ifconfig` -> Look for enp0s3

- If do not have `ifconfig` I can use : `ip addr`

If I want to ssh to my Linux Virtual from my Mac which is host : `ssh <ip-address>` then I can put username and password to connect 

## File System

It is a System used by OS to manage files or directory . The system control how data saved and retrieved from Computer Hard Disk 

OS stored files and directory in a structure way and organized way  

There are many different types of file system . In general, improvement have been made to filesystem with new release of OS and each new file system has been given different name 

There are **ext3**, **ext4**, **xfs** are Linux file system . **NTFS**, **FAT** are Window file system 

In Linux Everything start from `root` dir 

- **etc**: Where the configuration file go

- **Home**: Where all the User directories located

- **Opt**: where program are running

- **sbin**: where command and script are located

- **var**: where Logs file located

## Directory Listing Attribute 

When I do `ls -l` I will see this 

<img width="611" height="387" alt="Screenshot 2025-07-30 at 17 30 09" src="https://github.com/user-attachments/assets/c40d1705-1106-4eb8-802e-db3fe79b2934" />

First field is a `Type`: 

- Begin with : `d` stand for `Directory`

- Begin with :`l` stand for `Link`

- Begin with : `-` nothing on it, it's just a regular file 

Second field tell me a number of Links it has, or heart links attach to the directory 

Third field tell me the `Owner` of the Dir or File . Who's own it ? 

Fourth field tell me the `Group` 

Fifth is the size . 

Then `Month`, `Day`, `Time` and `Name`

## Create file and Dir 

Create file using : 

- `touch`

- `cp <existing file> <new destination location>`

- `vim <file name>` . vi is editor

Create Dir :

- `mkdir`

`ls -ltr` : Give me the ordered files . Oldest one at the top and Newest one at the bottom  

## File maintainence command 

`cp`: copy one to another 

`mv`: move file to another location . Or to rename a file 

`rm`: remove file 

`mkdir`: create dir 

`rmdir` or `rm -r`: to remove directory

`chgrp`: Ownership of the file at the Group level

`chown`: Change Ownership at the User Level 

- If I want to do both command at once : `chown trinhnguyen:trinhnguyen <file-name>` . It will change User ownership as well as Group ownership 

`man <command>` : Will show me the intruction how to use that specific command

## Soft link and hard link 

**inode**: is a **Pointer** or **Number** of a file on the **Hard Disk**

- For example if I create a file called `tim`, this is a name for me as a human for me to understand the name of the file . But computer does not understand **names**.

- Computers understand **numbers** . Every we create a file Computer assign a number to that file on a **Hard Disk** and associate **Numbers** to it, that **Numbers** is called **Inode**.

- Everytime we retrieve that file it go and retrieve that number

**Soft Link** is a Link when created and it will be **removed** if the file is **removed** or **renamed**  

- If I create a file and I create **soft link** to that file. Once I create it, it acutally look for that **Inode** through that file . So that create a **soft link**. If I removed Source file it will remove **Destination Link**

  **Hard Link** when deleting or renaming the source file the Hard Link will not change . It will remain the same as I copied

  To create **Hard Link**: `ln`

  To create **Soft Link**: `ln -s`

  **Soft Link** it is connecting **through my file**  to the **Inode**

  **Hard Link** connecting straing to the **Inode**


















 
