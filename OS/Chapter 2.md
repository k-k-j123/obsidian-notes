## Process concept
- a process is a program in execution which competes for CPU time and other resources
- the execution of a program must be in a sequential fashion
- when a program is loaded into memory it becomes process
- the process contains a program counter which specify next instruction to be executed
- each process has following sections
	- a text section contain the program code
	- a data section contains global or static variables
	- the heap section is used for dynamically allocated memory to a process during its execution
	- the stack section is used for local variables a process stack which contains the temporary data such as subroutines and function calls
	
	process model:
	- a process is just an executing program including current values of the program counter, register and variables
	- conceptually each process has its own virtual CPU in reality of course the real CPU switches back and forth from process to process thus it is much a collection of processes running in parallel this rapid switching is called as multi-programming
	- when the CPU switches back and forth among the processes the rate at which a process performs its computation will not be uniform

## Process States:
- the current activity of process is known as its state 
- as a process executes it changes state. the process state represents the current status of the process 
- a process may be in one of the following states 
	- New: a process is said to be new if ti is being created
	- Ready: a process is said to be ready if it is ready for execution and waiting for CPU
	- Running: a process is said to be in running state if the CPU has been allocated to it
	- Waiting or Blocked: A process is said to be in waiting state if it has been blocked by some event unless that event occurs the process cannot continue 
	- Terminated: A process is said to be terminated if it has completed its execution or has been terminated abnormally 
- when the process is selected by scheduler it is loaded into memory means the process is in new state or admitted
- after the process is new state it is in ready state and the process control block is created bu the scheduler the process is waiting for CPU when the process is allocated the CPU and executed it is in running state. during execution if it requires some I/O operations then it is in wait for I/O device after I/O operation the process is again in ready state waiting for CPU 

## Process control block:
- each process is represented in the operating system as process control block (PCB) also called as Task control block(TCB) 
- the operating system groups all the information that needs about a particular process into a data structure called PCB 
- when a process is created OS creates a corresponding PCB which stores descriptive information regarding the process such as its state program counter, memory management information, information about its scheduling allocated resources etc that is requires to manage and control a process 
- A PCB stores information as follows
	- Pointer : the pointer has address of next PCB whose process state is ready
	- Process State: specifies the current state of the process
	- Process number: unique number to identify each process (PID)\
	- Priority: the process is assigned a priority at the time of its creation 
	- program counter: stores the address of next instruction to be executed
	- CPU registers : various CPU registers like accumulators,stack pointer, general purpose registers where process needs to be stored
	- CPU scheduling information: includes process priority and other scheduling information\
	- memory management information: this includes the information of page table, memory limits, segment table 
	- accounting information: includes amount of CPU time used, time limits, account number
	- I/O status information: this information includes the list of I/O devices allocated to the process
	- File management: it includes information about all open files,access rights etc
	- ![[PCB.png]]

## Process Scheduling
- process scheduling is an essential part of mulitprogramming operating system which allows more than one process to be loaded into executable memory at a time and then loaded process shares the CPU using time multiplexing 
- schedules are often implemented so they keep all computer resources busy allowing multiple users to share system efficiently 
- when two or more processes compete for CU at the same time then a choice has to be made which process to allocate the CPU next this process of determining the next process to be executed is called as process scheduling 

### Scheduling Queue:
- several process are in ready or waiting state these process form a queue the OS maintains all PCB in process scheduling queue 
- the OS maintains a separate queue for each of the process states and PCB of all process in the same execution state are placed in the same queue
- when the state of a process is changed its PCB is unlinked from its current execution queue and moved to its new state
- the OS maintains the following process scheduling queue
	- Job queue: keeps all the processes residing in the system. As the process enters the system it is put into a job queue
	- Ready queue: keeps a set of all processes residing in main memory, ready and waiting to execute a new process is always put in this queue
	- ![[Scheduling queue.png]]

### Types of Schedulers:
There are three main types of schedulers in operating systems:
1. Long-Term Scheduler (Job Scheduler)

    Responsible for selecting jobs from the job pool and loading them into memory
    Decides which jobs to execute and when to execute them
    Used in batch processing systems
    Example: Selecting a batch job from a queue and loading it into memory

2. Short-Term Scheduler (Process Scheduler)

    Responsible for selecting processes from the ready queue and allocating the CPU to them
    Decides which process to execute next and when to execute it
    Used in multi-programming systems
    Example: Selecting a process from the ready queue and allocating the CPU to it

3. Medium-Term Scheduler (Swapper)

    Responsible for swapping processes in and out of memory
    Decides which processes to swap out of memory and which to swap in
    Used in virtual memory systems
    Example: Swapping out a process from memory to disk and swapping in another process from disk to memory
    
	![[Schedulers.png]]

## Context Switching
Context switching is the process of switching the CPU's execution context from one process or thread to another. This involves saving the current state of the process/thread being switched out and restoring the state of the process/thread being switched in.
**Context Switching Steps**
1. **Save Registers**: Save the current values of the CPU registers (e.g., program counter, stack pointer) of the process being switched out.
2. **Save Program Counter**: Save the current program counter (PC) of the process being switched out.
3. **Save Stack Pointer**: Save the current stack pointer (SP) of the process being switched out.
4. **Restore Registers**: Restore the saved registers of the process being switched in.
5. **Restore Program Counter**: Restore the saved PC of the process being switched in.
6. **Restore Stack Pointer**: Restore the saved SP of the process being switched in.
7. **Update Memory Management Unit (MMU)**: Update the MMU to point to the new process's memory space.

	![[Pasted image 20240815200738.png]]

## Thread Scheduling:
**Definition**
Thread scheduling is the process of allocating CPU resources to threads, which are lightweight processes that can execute concurrently within a process.

**Multi-Threading**
Multi-threading is a programming technique where a single process creates multiple threads to execute concurrently, improving responsiveness, throughput, and system utilization.

**Thread Scheduling Scope**
Thread scheduling can occur within:
1. **Operating System (OS)**: The OS schedules threads for CPU execution.
2. **Application**: An application schedules threads for execution within its own context.
    
**Thread Scheduling Contention**
Thread scheduling contention occurs when multiple threads compete for:
1. **CPU Resources**: Threads compete for CPU execution time.
2. **Shared Resources**: Threads compete for shared data, locks, or other system resources.

**Thread Scheduling Techniques**
1. **Preemptive Scheduling**: The OS interrupts a thread to schedule another thread.
2. **Non-Preemptive Scheduling**: A thread yields control to another thread voluntarily.
3. **Round-Robin Scheduling**: Each thread gets a fixed time slice (time quantum) for execution.
4. **Priority Scheduling**: Threads are scheduled based on their priority.
5. **FIFO Scheduling**: Threads are scheduled in the order they arrive.

### Differences between process and threads
![[process vs threads.png]]


### User level thread and Kernel level thread
**User-Level Threads**
- Managed by the application or library
- The operating system is unaware of their existence
- Threads are created and scheduled by the application
- Context switching is done by the application
- Lightweight and fast creation and destruction
- Limited access to system resources

**Advantages of User-Level Threads**
- **Faster Creation and Destruction**: User-level threads are created and destroyed faster since they don't require kernel involvement.
- **Lightweight**: User-level threads are lightweight, requiring less memory and resources.
- **Portability**: User-level threads are more portable across different operating systems.

**Disadvantages of User-Level Threads**
- **Limited Resource Access**: User-level threads have limited access to system resources, which can lead to inefficiencies.
- **Complex Scheduling**: User-level threads require complex scheduling algorithms to manage threads efficiently.

**Kernel-Level Threads**
- Managed by the operating system kernel
- The kernel is aware of their existence and manages them
- Threads are created and scheduled by the kernel
- Context switching is done by the kernel
- Heavier creation and destruction due to kernel involvement
- Full access to system resources

**Advantages of Kernel-Level Threads**
- **Full Resource Access**: Kernel-level threads have full access to system resources, making them more efficient
- **Simplified Scheduling**: Kernel-level threads use the kernel's scheduling algorithms, simplifying thread management.
    
**Disadvantages of Kernel-Level Threads**
- **Heavier Creation and Destruction**: Kernel-level threads are created and destroyed slower due to kernel involvement.
- **Heavyweight**: Kernel-level threads are heavier, requiring more memory and resources.

**Key Differences**
- **Management**: User-level threads are managed by the application, while kernel-level threads are managed by the kernel.
- **Context Switching**: User-level threads context switch within the application, while kernel-level threads context switch through the kernel.
- **Resource Access**: Kernel-level threads have full access to system resources, while user-level threads have limited access.

## Multi-threading models:
**1. One-to-One Model**
- One user-level thread mapped to one kernel-level thread
- Each user-level thread has its own kernel-level thread

- Advantages:
- Simple to implement
- Efficient context switching

- Disadvantages:
- Resource-intensive
- Limited scalability
    
**2. Many-to-One Model**
- Multiple user-level threads mapped to a single kernel-level thread
- User-level threads share a single kernel-level thread
    
- Advantages:
- Lightweight and efficient
- Fast context switching

- Disadvantages:
- Limited concurrency
- Complexity in thread management
    

**3. Many-to-Many Model**
- Multiple user-level threads mapped to multiple kernel-level threads
- User-level threads can be executed concurrently by multiple kernel-level threads
    
- Advantages:
- Efficient concurrency
- Scalability

- Disadvantages:
- Complexity in thread management
- Context switching overhead