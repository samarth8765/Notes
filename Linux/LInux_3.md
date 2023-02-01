# Lec-3 

## Users and Groups
- In the Linux operating system, a user is a person who uses the system, and a group is a collection of users. Every user is a member of at least one group, and each group is associated with a specific set of permissions that determine what actions the group's members are allowed to perform on the system.

- Users and groups are used to control access to resources on the system, such as files, directories, and system resources. For example, a user might be granted permission to read and write to a particular file, while another user might only be granted permission to read the file. Groups allow you to manage permissions for multiple users at once, rather than setting permissions for each user individually.

- You can use the useradd command to create a new user, and the groupadd command to create a new group.

- It's important to carefully manage users and groups on a Linux system, as improper permission settings can compromise the security of the system.

## sudo
-sudo is a command in Linux and other Unix-like operating systems that allows a user to execute commands with the privileges of another user, typically the superuser (root).

- The sudo command is typically used to perform tasks that require root privileges, such as installing software or modifying system configuration files. This allows users to perform these tasks without logging in as the root user, which is generally considered to be a security best practice.

- To use the sudo command, a user must be granted permission to use it by being listed in the /etc/sudoers file. This file specifies which users are allowed to use sudo, and which commands they are allowed to execute using sudo.

- When you execute a command using sudo, you will be prompted to enter your own user password. This is to verify that you are authorized to use sudo and to prevent unauthorized users from gaining elevated privileges on the system.

- It's important to use sudo with caution, as executing commands with root privileges can have unintended consequences if not done carefully.

### Informartion about users in our linux system
- We can access each user's info using sudo cat /etc/passwd.
- User's info is represented as - 
    - root:x:0:0:root:/root:/bin/bash
    -  1   2 3 4  5    6      7  
    which is divided into 7 different parts.

- Let us explore each part in detail -
    - root - Name of the user. Here in this example it is  root.
    - x - Second part of this info gives us the password of the user. If it is represented by x, then the password is stored in a file called shadow.   
    - 0 - Third part is userID, which is 0 for root user.
    - 0 - Fourth part is groupID, which is 0 for root user.
    - root - Fifth part is some basic user's info like contact details, email etc.
    - /root - Sixth part User's home directory.
    - /bin/bash - Seventh part is the shell user is using

- Shadow file contains info about each user password which is stored in /etc folder.(sudo cat /etc/shadows).

### PAM
- Pluggable authentication module (recent authentication system).

### Information about groups in our linux system
- It is stored in /etc/group
- The info is stored in the form root:x:0: which is divided into 4 parts.
    - First part contains name of the group.
    - Second part contains password of the group.
    - Third part is the groupID.
    - Fourth part contains all users which are their in the group.


- To change the password of a user (sudo passwd $USERNAME)
- To change hostname (sudo hostname NEW-HOSTNAME)

### Permission of files and directories in linux-
- drwxr-xr-x (10 characters or bits)
- First part - d (Type whether it is a file(-) or a directory(d) or a link(l))
- second part - rwx (User permission)
- third part - r-x (Group permission)
- fourth part - r-x (others)

- r(read)(4), w(write)(2), x(execute)(1).
- users(u), groups(g), others(o).
- + symbol is use to add permission and - for vice-versa.

- setuid (s symbol permission)


### Sticky-bit
- In Unix-like operating systems, the sticky bit is a special type of file permission that can be set on a file or a directory. It is represented by the letter t in the execute permission field of the ls -l command output.

- The sticky bit is used to prevent the deletion of a file in a directory that is not owned by the user. When the sticky bit is set on a directory, only the owner of the file, the owner of the directory, or the root user can delete or rename a file in that directory. This can be useful in cases where the directory is used by multiple users and you want to prevent users from deleting or renaming each other's files.

- To set the sticky bit on a file or directory, use the chmod command with the +t option. For example:

### Process Permission
- Effective UID
- Real UID
- Saved UID




