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

| Command |Description |
|:--------|:-----------|
| **ls**     | Show directory contents.|
| **ls -a**  | Show all directory contents. (even hidden files).|
| **ls -l**  | Show a detailed list of directory contents in a long format.|
| **ls -la** | Show a detailed list of all directory contents (even hiden files).|
| **ls -R**  | Recursively list directory contents.|
| **ls -r**  | Show directory contents in reverse order while sorting.|
| **ls -t**  | Show directory contents sorted by modification time (newest first).|

### Touch
Touch allows you to create new, empty files. Touch can also be used to change timestamps on existing files and directories.
```shell
touch filename.txt
```

### Cat
The `cat` command, short for concatenate, displays the contents of a file(s).
```shell
cat filename 
````

### Less
The `less` command displays text in a paged manner, so you can navigate through a text file page by page.

```shell
less /path/file
```

Once you are in the `less` command you can use other commands to navigate in the file.

| Command                                                    | Description                                         |
|:-----------------------------------------------------------|:----------------------------------------------------|
| **q**                                                      | Quit out of less.                                   |
| **up**, **down**, <kbd>Page Up</kbd>, <kbd>Page Down</kbd> | Navigate using arrow keys or page keys.             |
| **g**                                                      | Move to the beginning of the text file.             |
| **G**                                                      | Move to the end of the text file.                   |
| **/\<search term\>**                                       | Search for specific words within the text document. |
| **h**                                                      | Help menu for `less`.                               |

### History
View a history of commands that you previously entered.

```shell
history
```

Instead of typing a command again you can use the up arrow to find a previously entered command and press <kbd>Enter</kbd>. Use `!!` if you want to use the previous command without typing it in again.

Another history shortcut is <kbd>CTRL</kbd> + <kbd>R</kbd>, the reverse search command. Hit the <kbd>CTRL</kbd> + <kbd>R</kbd> keys and start typing parts of the command you want and it will show you matches. You can navigate through them by hitting the <kbd>CTRL</kbd> + <kbd>R</kbd> keys again. Once you find the command you want to use again hit the <kbd>Enter</kbd>.

To clean up the terminal window use the `clear` command to remove the clutter in the display.

If you start typing the beginning of a command, directory, file, etc you can hit the <kbd>Tab</kbd> key to autocomplete based on what is found in the directory you are searching.

---

## Basic Commands
|Command|Description|
|:--|:--|
|**adduser**|Adds a user to the system.|
|**ifconfig**|Much like ipconfig in Windows, displays network configuration information about your NIC (Network Interface Card).|
|**passwd**|Used to change your password.|
|**ps**|Process status command. Using the -ef option will show all processes running on the system.|
|**su**|Allows you to perform functionas as another user. The sudo command version allows you to run programs with "super user" (root) privileges.|

## File Management
|Command|Description|
|:--|:--|
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

## Network Commands
|Command|Description|
|:--|:--|
|**ifconfig**|Displays your current network configuration, mainly your IP address if connected.|
|**ping \<ip\>**|Sends a ping packet to another IP on the network to check if the host is alive.|
|**ifup \<interface\>**|Enables the specified interface.|
|**ifdown \<interface\>**|Disables the specified interface. Could be useful to disable WiFi if you are already connected by cable for example.|

## File Transfer and Remote Connection
|Command|Description|
|:--|:--|
|**wget \<url\>**|This command allows you to download a file from the Internet.|
|**ssh \<user\>@\<ip\>**|SSH is a network protocol that provides you a way to connect securely to a remote computer.|
|**scp \<file\> \<user\>@\<ip\>:\<path\>**|scp can transfer a file to a remote computer over SSH.|
|**rsync \<file\> \<user\>@\<ip\>:\<path\>**|rsync does almost the same thing but with a delta comparison algorithm and some optimizations to transfer files faster.|

## System Updates
|Command|Description|
|:--|:--|
|**apt-get update**|Downloads the last repository version for each one you have in your configuration (/etc/apt/sources.list).|
|**apt-get upgrade**|Updates all installed packages if needed.|

## Packages Management
|Command|Description|
|:--|:--|
|**apt-get install \<package\>**|Installs the specified package(s).|
|**apt-get remove \<package\>**|Removes a previously selected package.|
|**apt-cache search \<search\>**|Searches for a package name in the packages list (repository).|
|**dpkg -l**|Lists all installed packages on your system. You can use grep to find a specific package.|

## System Management
|Command|Description|
|:--|:--|
|**reboot**|This command will restart the machine immediately.|
|**shutdown -h now**|This is to stop the machine immediately.|
|**service \<servicename\> \<action\>**|This command allows you to start or stop services.|
|**ps**|This command displays all running process on your machine.|
|**kill \<pid\>**|Kills a running process. (You must specify the process ID number.)|

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
