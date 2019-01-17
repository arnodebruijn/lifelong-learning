Linux
=====

Kernel
------
Responsible for enforcing rules, sharing resources, and providing the core services that user processes rely on.

The kernel hides the detail of the system's hardware underneath an abstract high level interface. This interface provides five basic features:
* Management and abstraction of hardware devices
* Processes and threads (and ways to communicate among them)
* Management of memory (virtual memory and memory-space protection)
* I/O facilities (filesystems, network interfaces, serial interfaces, etc.)
* Housekeeping functions (startup, shutdown, timers, multitasking, etc.)


System management processes
---------------------------
PID 1 process started by the kernel with some special priviliges. It's goal is to make sure the system runs the right complement of services and daemons.

* init
* systemd - Replaces init and adds more functionality. Responsible for how services should be accesses, configured, and managed.


SELinux
-------
Security Enhanced Linux that implements MAC and RBAC.

MAC	Mandatory Access Control
RBAC	Role Based Access Control


Process
-------
A process represents a running program and is an abstraction through which memory, processor time, and I/O resources can be managed and monitored.

A process consists of an address space and a set of data structures within the kernel.
The address space is a set of memory pages that the kernel has marked for the process's use.

A thread is an execution context within a process. Each thread has it's own stack and CPU context but operates within the address space of its enclosing process. Threads are more light weight than processes.

Processes are initiated in two steps:
1. An existing program clones itself with the fork system call to create a new process (the original process is referred to as the parent, and the copy is called the child).
2. The clone can then exchange the program it's running for a different one.

When a process completes it calls a routine called `_exit` to notify the kernel that it is ready to die. An integer exit code is supplied to tell why the process is exiting (a 0 indicates a succesfull termination). The kernel requires that the death of a process is acknowledged by it's parrent. If a parent dies before it's children the kernel adjusts the orphan processes to make them children of init or systemd.

Signals are process-level interrupt requests.


Logging
-------

Syslog integrated (linux) but rudementary logging system. Provides a standardized interface to applications for submitting log messages.
Systemd journal. Collects, stores, indexes and compresses messages. Provides a command line interface for filtering and viewing logs.
  `journalctl`

logrotate to manage and rotate logs.


Monitoring
----------
Nagios
- server and network monitoring
