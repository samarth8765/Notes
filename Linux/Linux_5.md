- File types in linux filesystem
    - c - character
    - b - block(SSD's, HDD's)
    - p - pipe
    - l - link
    - d - directory
    - (-) - file
    - s - socket 

- Filesystem hierarcy
    - / - Root directory
    - bin - binaries files
    - boot - bootable files
    - dev - device files
    - etc - contains config files 
    - home - home directory
    - lib - library files for binaries
    - media - external storage devices
    - mnt - temporary mounted file system
    - opt - optional software packages
    - proc - process info
    - root - home directory for root
    - run - info after running up the system is stored in this directory
    - sbin - system binaries (only root can run these binaries)
    - sys - manage devices and filesystems
    - tmp - storage for temp files
    - usr - user installed softwares and utilities
    - var - variable directory

- Journaling
    - Journaling offers improved filesystem reliability and fast crash recovery through the use of a transaction log, or journal. The journal is an on-disk log of metadata, or data about the filesystem, that is kept up-to-date as the filesystem changes. 

- Desktop filesystem types-
    1. ext4
        - It supports disk space upto - 1 exabyte
        - It supports file size upto - 16 terabytes
    2. Btrfs (Butter/Better FS)
        - Relatively new fs.
    3. XFS
        - Good for large media servers.
    4. NTFS and FAT fs (windows filesystem)
    5. HFS+ (mac filesystem)

    - We can check which filesystems are we currently using , using (df -T) command.


- Two main partition schemes-
    - MBR (master boot record)(BIOS based booting)
    - GPT (Globally Unique ID partition table)(UEFI based booting)

    GUID Partition Table (GPT) and Master Boot Record (MBR) are two different partitioning schemes used to store information about how hard drives are partitioned on a computer.

    - GPT is a newer partitioning scheme that is used on modern computers and is slowly replacing MBR. It offers several advantages over MBR, such as support for larger drives (greater than 2 TB), the ability to have more than four partitions on a single drive, and improved reliability due to its use of a redundant copy of the partition table.

    - MBR is the traditional partitioning scheme that was used on computers for many years. It stores information about the partitions on a drive in a single 512-byte block at the beginning of the drive. One of the limitations of MBR is that it can only support up to four primary partitions, or three primary partitions and one extended partition. It is also limited to drives that are less than 2 TB in size.

    - If you are planning to install an operating system on a new computer, you will typically have the option to choose between using GPT or MBR for the partitioning scheme. In most cases, it is recommended to use GPT, as it offers several advantages over MBR and is becoming the standard on modern computers. However, if you need to boot an older operating system that does not support GPT (e.g., Windows XP), you may need to use MBR instead.


- File structure components-
    - Boot block
    - Super block
    - Inode table 
    - Data blocks

    - The boot block, super block, inode table, and data blocks are all part of a Unix-style file system, which is a way of organizing and storing files on a computer's hard drive or other storage device. A file system is responsible for organizing and managing the storage of files on the device, and these four elements are important components of many file systems. The boot block is used to boot the operating system, the super block contains information about the file system as a whole, the inode table contains information about individual files and directories, and data blocks are used to store the actual contents of the files and directories.

    - To know more about files system we can use
     ```
        sudo parted -l
    ```

- Swapfile
    - A swap file (also known as a paging file or a swap space) is a special file on a computer's hard drive that is used to support virtual memory. Virtual memory allows a computer to compensate for shortages of physical memory (RAM) by temporarily transferring pages of data from RAM to a swap file on the hard drive. This allows the system to continue running even if all of the available physical memory has been used up.

    - When a computer runs low on physical memory, the operating system will move some of the data that is stored in RAM to the swap file. This frees up space in RAM for other programs to use. If the data in the swap file is needed again, it is transferred back to RAM. This process is transparent to the user and happens automatically in the background.

    - The size of the swap file is usually set automatically by the operating system based on the amount of physical memory in the system and the workload of the system. However, it is also possible to adjust the size of the swap file manually if necessary.

    - In summary, a swap file is a special file on a hard drive that is used to support virtual memory and allow a computer to compensate for shortages of physical memory.

- Disk-usage command
    ```
        du -h
    ```
- Number of Inodes in our system
    ```
        df -i
    ```

- Inode table(Index node table)
    - In a Unix-style file system, an inode (short for "index node") is a data structure that stores information about a file or directory. Each file and directory in the file system has its own inode, which is identified by a unique inode number. The inode table is a data structure that contains a list of all the inodes in the file system.

    - The inode for a file or directory typically contains the following information:
    - The file type (e.g., regular file, directory, symbolic link, etc.)
    - The file's size
    - The file's owner and group
    - The file's permissions (e.g., read, write, execute)
    - The timestamps for the file's creation, last access, and last modification
    - Pointers to the blocks on the disk where the file's data is stored
    - The inode table is usually stored in a fixed location on the disk, and the operating system maintains a cache of inodes in memory for faster access. When a file or directory is accessed, the operating system looks up its inode in the inode table to find the information it needs to access the file's data. 

    - If Inodes in our system is full, then we cannot create files and directories in our system if
     still we have storage left in our system.

     - We can check inode number of our files using `ls -li` command.

     - How Inodes work?
        -  


- Links

    - In the Linux operating system, a link is a reference to a file or directory that allows multiple names to be associated with the same file or directory. There are two types of links: hard links and soft (symbolic) links.

    - A hard link is a direct link to the actual file or directory on the file system. When a hard link is created, the file or directory is not duplicated, but an additional name is created that points to the same inode as the original file. Hard links are indistinguishable from the original file and can be used in the same way.

    - A soft (symbolic) link, on the other hand, is a special file that contains a reference to another file or directory. When a soft link is followed, the operating system looks up the path contained in the link and accesses the file or directory that the link refers to. Soft links are often used to create aliases for files or to create links to files in different locations on the file system

    - Command for short link
        ```
            ln -s originalFileName softFileName
        ```
    - Command for hard link
        ```
            ln originalFileName hardFileName
        ```
    - If we make changes in the soft link file then "yes" they would be shown in the original file.
    - If we make changes in the hard link file then "yes" they would be shown both the original and soft link file.
    - if we delete the original file then the soft link doesn't work, but the hard link works properly.
