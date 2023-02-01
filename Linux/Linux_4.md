# Processes in linux system

- ps -aux
    - a -> all processes
    - u -> user or owner of that process
    - x -> processes that donot require any terminal to run (daemon).

- pts - psuedo terminal
- tty - regula terminal (Teletypewriter)

- init is the mother of all processes (pstree)
- Initally when processes create, init forks to create new processes.

- Termination of a process
- When a process terminates it will send wait system call to its parent.


- Orphan process
    - If parent process dies before the child process.
    - So kernel assigns 'init' as their parent process. 


- Zombie process
    - Child terminates but parent doesnot acknownlege the wait system call. So, this child process is known as zombie process.

- Signal
    - Simply signal's the process.Some of the examples are-
    - Sigkill (9)
    - Sigsegv (11)
    - Sigterm (15)

    - So when we wirte 'kill PID' it will send sigterm signal to the process and process will first clean necessary tasks before exiting whereas 'kill -9 PID' will send sigkill which will immediately kills the process without cleaning up the necessary tasks.

- Nice(NI) column in top command
    - If NI value of a process is high then (Low priority).
    - Else process is of high priority.

- We can also change the priority of a process using the following commands-
    - nice -n VALUE PROCESS_NAME

- If a process is running, still we can change it priority using renice command-
    - renice VALUE -p PID_OF_PROCESS

- Everything in linux is a file, so all the processes with their details are in the proc folder in the root directory.


- If we want to run a process in the background we can '&' symbol at the end of our commnad.For example:
- python3 time.py &

- In Linux and other Unix-like operating systems, a process is an instance of a program that is being executed. Each process has its own process ID (PID) and runs as an independent entity, with its own memory space and other resources.

- A job is a process that is associated with a terminal. When you run a command in a terminal, the command becomes a job that is managed by the terminal. You can use the jobs command to view a list of all jobs that are running or stopped in the current terminal.

- The main difference between a process and a job is that a process is a program that is being executed, while a job is a process that is associated with a terminal and can be managed by the terminal. A single process can be associated with multiple jobs, and a single job can be made up of multiple processes.

- For example, when you run a command in a terminal, the terminal creates a new process to run the command. The command becomes a job that is associated with the terminal, and the process is the instance of the program that is being executed.

- You can use the ps command to view a list of all processes currently running on the system, and you can use the jobs command to view a list of all jobs running or stopped in the current terminal.

- We can also bring a process from background to foreground using the following command (fg %JOB_ID).

- To bring a running process from foreground to background, just press CTRL + Z.

- To directly kill a process in background use kill %JOB_ID.

