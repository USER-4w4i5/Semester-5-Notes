- What error can cause the OS to crash?
	- Improper Synchronization
	- Failed Mutual Exclusion
	- Nondeterminate Program Operation
	- Deadlocks
- Process consists of:
	- Executable
	- Associated data
	- Execution Context(Process State)
		- Register values
		- OS Process control data (pid is stored here, if halted)
		- Priority
		- I/O Status
- Process implementation (Not complete)
	- Some defs
		- Process registers
			- PC
				- Program counter
			- Base
				- Holds the address for the start of the program
			- Limit
				- Number of words occupied by the process
		- Process
			- Page
				- Context
					- Base points to the start of context
				- Data
				- Program
- Virtual Memory
	- Allows programs to work with virtual addresses that refer to the real addresses
		- Allows OS to just manage addresses logically and delegate the real placement of the pages up to the ram
	- All pages are maintained on disk
<!--
	- Memory Management
	- Process Isolation
	- Automatic Allocation and Management
	- Support of modular programming
	- Protection and access control
	- Long-term storage
-->