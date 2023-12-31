## Android
- Based on Linux
- Android Runtime
	- Every android application runs in its own process of the Dalvik Virtual Machine (DVM)
	- DVM executes in the .dvx format
### System Libraries 
- Collection of useful system functions written in C/C++ and used by various parts of the andriod system
- Called from the application framework and applications through 

### Power Management
- Alarms
- Wakelocks

# Chapter 3: Process Description and Control
- Process is an instance of a program or a program in execution
- Process elements
	- Program code
	- Process data
	- Process State Word (PSW)
- Process control block
	- Contains the process elements
		- **Process ID (PID)**: A unique identifier assigned to each process in the system, enabling the OS to distinguish between processes.
			- **Program Counter (PC)**: 
				- Keeps track of the address of the next instruction to be executed by the process.
			- **CPU Registers**: '
				- Stores the values of CPU registers when the process is preempted or interrupted. This allows the process to resume execution seamlessly.
			- **Scheduling Information**:
				- Contains details about the process's scheduling priority, state (e.g., running, waiting, or ready), and other scheduling-related data.
			- **Memory Management Information**: 
				- Includes information about the process's memory allocation, such as the base and limit registers, page tables, or segment descriptors.
			- **I/O Status Information**: 
				- Keeps track of I/O devices the process is using or waiting on, such as open files, pending I/O requests, and their status.
			- **Accounting Information**: 
				- Tracks resource usage statistics like CPU time, wall-clock time, and other resource-related data.
			- **Parent Process Pointer**: 
				- Points to the PCB of the parent process if the process is created by another process (e.g., in fork() operations).
			- **Child Process Pointers**: 
				- Contains pointers to PCBs of child processes if any exist.
			- **Inter-Process Communication (IPC) Information**: 
				- Includes data related to message queues, semaphores, and shared memory segments used for IPC.
			- **Signal Handling Information**: 
				- Records how the process handles signals or interrupts, such as signal handlers and signal masks.
			- **File Descriptors**: 
				- Stores references to open files and their associated file control blocks.
			- **Priority and Scheduling Information**: 
				- Contains information about the process's priority, scheduling algorithm, and any time-related data for scheduling.
			- **Security Information**: 
				- May include information related to process permissions, access control, and security attributes.
			- **Exit Status**: 
				- Records the exit status or exit code of the process when it terminates
	- Created and managed by the OS
	- Key tool that allowed for support for multiple process
	- When a process is removed from the running state to allow another process to run values important to correct execution of the process must be saved. The PCB is where such information is saved
	- PCB lifetime is only for the duration of the process
- Reasons for process creation
	- **New batch job**: 
		- Processes are created to execute a new batch job or task in batch processing systems, where multiple jobs are run sequentially.
	- **Interactive logon**: 
		- When a user logs into a computer system, an interactive process is created to facilitate user interaction and run user-specific tasks.
	- **Created by OS to provide a service**: 
		- The operating system creates processes to offer various services like printing, network services, or background tasks (daemons) that serve system-level functions.
	- **Spawned by the existing process**: 
		- Existing processes can create child processes or spawn new processes to perform parallel or related tasks, enabling multitasking and efficient resource utilization.
- Process Creation
- Process Termination
	- **Normal Termination**:
	    - The process has completed its execution and exits gracefully.
	    - The program reaches the end of its main function.
	- **Abnormal Termination**:
	    - **Error**: The process encounters an unrecoverable error or exception.
	    - **Illegal Instruction**: Attempting to execute an invalid or privileged instruction.
	    - **Segmentation Fault**: Accessing memory that the process doesn't have permission to access.
	    - **Stack Overflow**: The process's call stack exceeds its allocated memory.
	    - **Arithmetic Error**: Dividing by zero or other illegal arithmetic operations.
	- **External Termination**:
	    - **Killed by User**: A user or administrator terminates the process manually.
	    - **Resource Exhaustion**: The system runs out of resources (e.g., memory) and terminates processes to free up resources.
	    - **Parent Termination**: If a parent process terminates, its child processes might also terminate.
	- **Interrupts and Signals**:
	    - Processes can be terminated due to receiving specific signals or interrupts from the operating system or other processes. For example:
	        - SIGTERM: Termination signal.
	        - SIGKILL: Unconditionally kill a process.
	- **System Shutdown**:
	    - When the entire system shuts down or restarts, all processes are terminated.
	- **Time Limits**:
	    - Some systems or batch processing environments may impose time limits on processes. When exceeded, the process is terminated.
	- **Resource Constraints**:
	    - Running out of allocated resources, such as file handles or network connections, can lead to termination.
	- **Security Policies**:
	    - Security mechanisms or policies may force termination if a process violates security rules or access controls.
	- **Deadlock Resolution**:
	    - In multi-process systems, processes might be terminated to resolve deadlocks where processes are waiting for resources indefinitely.
- Process States
	- Trace
		- The code of the process
	- Dispatcher
		- A process itself responsible for 
- Process State Models
	- 2 State model
		- ![](Pasted%20image%2020230912151828.png)
		- 
	- 5 State model 
		- ![](Pasted%20image%2020230912151924.png)
		- 
	- 6 State model
		- ![](Pasted%20image%2020230912152003.png)
	- 