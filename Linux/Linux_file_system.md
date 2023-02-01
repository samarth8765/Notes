- Everything in linux is a file.

# Linux file system
- Bin - Short form for binary which contains executable files
- Sbin - System binaries used by admin.
- usr - 
- boot - boot has bootable files that a system needs while booting the system.
- dev - devices in our system are also files
- etc - In a Linux operating system, the /etc directory (short for "etcetera") contains configuration files for the system and various programs installed on the system. These files contain settings that control the behavior of the system and the programs that run on it.

# Daemon 
- A daemon is a type of process that runs in the background on a Unix-like operating system, such as Linux. Daemons are typically started at system boot time and run continuously, performing tasks or services in the background.

- Examples of daemons include the inetd daemon, which listens for network connections and starts other processes to handle incoming requests, and the cron daemon, which executes scheduled tasks.

- Daemons are usually not associated with a terminal and do not have a controlling terminal. This means that they run independently of a terminal and are not interrupted by signals sent from a terminal. Daemons are usually started automatically by the system and run in the background, performing their tasks or services without requiring user interaction.

- You can use the ps command with the -aux options to see a list of all processes, including daemons, running on a system. You can also use the systemctl command to manage daemons and other system services on systems that use the systemd init system.

- Systemd is regarded as the master daemon. It is one of the important daemon as it manages all daemons in the system. It is the first process that starts when system boots up.

- Commands (ps -aux, pstree, systemctl is-active < process_name >, systemctl is-enable < process_name >, systemctl disable/enable < process_name >)

- If we want to see all active daemon processes use systemctl list-units


# Curl
- curl is a command-line tool that is used to transfer data from or to a server. It supports various protocols, such as HTTP, HTTPS, FTP, and many more. curl is often used to download files, upload files to a server, submit data to a form, and more. It is a powerful tool that is frequently used in scripts and programs to automate tasks.

- Here is an example of using curl to download a file from a server:

- curl https://example.com/file.zip --output file.zip
- This command downloads the file located at https://example.com/file.zip and saves it to the current directory with the name file.zip.

- There are many options and flags that you can use with curl to customize its behavior. For example, you can use the -L flag to follow redirects, the -u flag to specify a username and password for authentication, and the -X flag to specify the request method (e.g., GET, POST, DELETE).

- To learn more about curl and all of its options, you can consult the manual pages by running man curl in your terminal.



