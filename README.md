# RHCSA

- [File System](#File-System)

- [Directory Listing Attribute](#Directory-Listing-Attribute)

- [Create file and Dir](#Create-file-and-Dir)

- [File maintainence command](#File-maintainence-command)

- [Soft link and hard link](#Soft-link-and-hard-link)

- [Input and Output Redirect](#Input-and-Output-Redirect)

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

 **Link** is just like a shortcut in a regular term as if I creating a shortcut on my Desktop .

 - I have a file located somewhere I have to go to that file all the time by navigating to that file system . So I will create a shortcut double click and run 

`ls -li`: `i` stand for **inode** . This help me to find out the **inode** of this file . 

- When I `ls -li tim` I will see a **inode** associate with my file `tim` in my current folder

- But then I create a **Soft Link** for in `/tmp` folder associate with `/home/trinhnguyen/tim` file It will have a different **inode** number bcs It is remember as a **Link** it does not know that it is actually a file

## Input and Output Redirect 

There are 3 diffent types of Redirect in Linux :

**Stdin** Standard input and it has file descriptor number as 0 

**Stdout** Standard output and it has file descriptor number as 1 

**Stderr** Standard error and it has file descriptor number as 2 

Everything in Linux is consider as **File** . All those devices attached to my Linux System, monitor, keyboard, mouse or any of those are considered or seen by OS as a **File** 

When we write something on screen from the Keyboard that coming in as **Standard Input** and it knocking for **File Descriptor 0**

When we are showing that output on the screen that output actually going through the **File Output Descriptor 1** 

If there is any error it will show up as the **File Descriptor 2**

**Stdout** :

- By default when running a command its output goes to the Terminal

- The output of a command can be routed to a file using **>** symbol sign

- For example : `ls -l > listings` Route the `ls -l` to a `listings` file

- If using the same file for addition output or to **append** to the same file then use **>>**

**Stdin**: 

- Input is use when feeding file content to a file or script

- For example : `cat < listings`

- Using **mail** program : `mail -s "Office memo" allusers@abc.com < memoletter` . Give me an option indirect bring the content of memo or file into that program 













 
