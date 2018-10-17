# Linux Cheatsheet

**Table of Contents**
1. [Linux File Structure](#linux-file-structure)

## Linux File Structure
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
