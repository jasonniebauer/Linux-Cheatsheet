# Linux Cheatsheet
A reference guide from the [Linux Journey](https://linuxjourney.com/).

**Table of Contents**
1. [Command Line Fundamentals](#command-line-fundamentals)
2. [Text Manipulation](#text-manipulation)
3. [User Management](#user-management)
4. [Permissions](#permissions)
5. [Processes](#processes)
6. [Packages](#packages)
7. [Devices](#devices)
8. [The Filesystem](#the-filesystem)
9. [Boot the System](#)
10. [Kernal](#)
11. [Init](#)
12. [Process Utilization](#)
13. [Logging](#)
14. [Network Sharing](#)
15. [Network Basics](#)
16. [Subnetting](#)
17. [Routing](#)
18. [Network Config](#)
19. [Troubleshooting](#)
20. [DNS](#)

## Command Line Fundamentals

### The Shell
The shell is a program that takes your commands from the keyboard and sends them to the operating system to perform.

The shell prompt format looks like this:
```shell
username@hostname:current_directory
```
Shell commands are entered after the `$` shown at the end of the shell prompt.
```shell
pete@icebox:/home/pete $ _command_goes_here_
```

### Echo
Print text arguments to the display with `echo`:
```shell
echo Hello World
```

|Command|Description|
|:------|:----------|
|**echo**|Print text arguments to the display.|
|**date**|Prints the date in UTC format (Wed Sep 26 15:55:37 UTC 2018)|
|**whoami**|Prints the username of the current user signed in.|

### Print Working Directory
|Command|Description|
|:------|:----------|
|**pwd**|Shows you which directory you are in.|

### Change Directory
|Command|Description|
|:------|:----------|
|**cd .**|This is the directory you are currently in.|
|**cd ..**|Takes you to the directory above your current.|
|**cd \~**|This directory defaults to your “home directory”.|
|**cd -**|This will take you to the previous directory you were just at.|

### List Directories and Files
Lists the files and directory in the current or specified folder.

|Command|Description|
|:------|:----------|
|**ls**|Show directory contents.|
|**ls -a**|Show all directory contents. (even hidden files).|
|**ls -l**|Show a detailed list of directory contents in a long format.|
|**ls -la**|Show a detailed list of all directory contents (even hiden files).|
|**ls -R**|Recursively list directory contents.|
|**ls -r**|Show directory contents in reverse order while sorting.|
|**ls -t**|Show directory contents sorted by modification time (newest first).|

### Touch
Touch allows you to create new, empty files. Touch can also be used to change timestamps on existing files and directories.
```shell
touch filename.txt
```

### Cat
THe `cat` command, short for concatenate, displays the contents of a file(s).
```shell
cat filename 
````

## Basic Commands
|Command|Description|
|:--|:--|
|**adduser**|Adds a user to the system.|
|**ifconfig**|Much like ipconfig in Windows, displays network configuration information about your NIC (Network Interface Card).|
|**kill**|Kills a running process. (You must specify the process ID number.)|
|**passwd**|Used to change your password.|
|**ps**|Process status command. Using the -ef option will show all processes running on the system.|
|**su**|Allows you to perform functionas as another user. The sudo command version allows you to run programs with "super user" (root) privileges.|
|**mkdir `<folder>`**|Creates a new subfolder in the current or specified folder.|
|**cp `<file>` `<destination>`**|Copies a file or a directory to another location (to copy a complete directory you need to add the -r parameter for “recursive”).|
|**mv `<source>` `<destination>`**|Moves a file or a directory to another location.|
|**cat \<file\>**|Displays all the content of the specified file.|
|**more \<file\>**|Displays the content of the specified file, page per page (enter or spec to continue, q to quit).|
|**tail \<file\>**|Tail allows you to display the end of a file, it’s useful to check new entries in a log file.|
|**tail \<file\>**|Tail allows you to display the end of a file, it’s useful to check new entries in a log file.|
|**tail -n20 \<file\>**|Specify the number of lines to display with `-n`.|
|**tail -f \<file\>**|Displays new lines in real-time.|
|**head \<file\>**|Display the beginning of a file.|
|**grep \<file\>**||
|**man**|Displays the "manual" page for a comman (much like a help file).|
|**rm**|Removes files. The command rm -r also recursively removes all directories and subdirectories on the path and provides no warning when deleting a write-protected file.|
|**tar -c**|Store files into an archive. It’s often used with gzip to compress files.|
|**tar -x**|Same command but to extract files.|

## The Filesystem
Linux File Structure
```
/
├── bin
├── dev
├── etc
│   ├── passwd (password file)
│   └── shadow (encrypted passwords)
├── home
│   ├── user 1
│   └── user 2
├── mnt
│   ├── CDROM
│   ├── Hard drive
│   └── USB
├── sbin
└── usr
```

### /
A forward slash represents the root directory.

### /bin
The bin directory holds all sorts of basic Linux commands (a lot like the C:\Windows\System32 folder in Windows).

### /dev
This folder contains the pointer locations to the various storage and input/output systems you will need to mount if you want to use them, such as optical drivers and additional hard drives or partitions. Note that *everything* in Linux is a file.

### /etc
The etc folder contains all the administration files and passwords. Both the password and shadow files are found here.

### /home
This folder holds the user home directories.

### /mnt
This folder holds the access locations you've actually mounted.

### /sbin
Another folder of great importance, the system binaries folder holds more administrative commands and is the repository for most of the routines Linux runs (known as *daemons*).

### /usr
This folder holds almost all of the information, commands, and files unique to the users.
