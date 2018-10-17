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

## Basic Commands
|Command|Description|
|:--|:--|
|**cd**|Change directory.|
|**pwd**|View where you are.|
|**adduser**|Adds a user to the system.|
|**cat**|Displays the contents of a file.|
|**cp**|Copies.|
|**ifconfig**|Much like ipconfig in Windows, displays network configuration information about your NIC (Network Interface Card).|
|**kill**|Kills a running process. (You must specify the process ID number.)|
|**ls**|Displays the contents of a folder. The -l option provides the most information about the folder contents.|
|**man**|Displays the "manual" page for a comman (much like a help file).|
|**passwd**|Used to change your password.|
|**ps**|Process status command. Using the -ef option will show all processes running on the system.|
|**rm**|Removes files. The command rm -r also recursively removes all directories and subdirectories on the path and provides no warning when deleting a write-protected file.|
|**su**|Allows you to perform functionas as another user. The sudo command version allows you to run programs with "super user" (root) privileges.|

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
