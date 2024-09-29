### what is an operating system?
An Operating System is a collection of System level programs that help the user to interact with computer hardware.
It is used to manage all the resources of a computer system. The main task of OS is to control, co-ordinate and supervise of hardware to all users
It handles memory resources, control I/O, schedule jobs, handle error, provide security and protection so on.

### Categories of Operating System:
1. Single User Single Tasking: only one user can perform a single task at a time
2. Single User Multi Tasking: Allows Single user can execute more than one task at a time.
3. Multi User Multi Tasking: allows many different user to take advantage of the computer resources simultaneously.
4. Real time OS (RTOS): mainly used in embedded system executes the processes  very quickly.
5. Distributed OS: The data is stored and processed in multiple remote location. all the resources are distributed over the network and accessed remotely.
6. Time sharing OS: each user is given a specific amount of time to use the resources and execute tasks.
7. Multi Programming OS: has multiple processes in the state of execution at the same time.
8. Batch Processing OS: specific number of tasks are grouped into batches and sent at once to execution.
9. Multi threading OS: allows different part of a program to be run simultaneously.
10. Multi processing OS :a single CPU has more than one processor and tasks are divided among these processor.
11. Network OS: The Operating system is stored on a single server and all the clients access the OS remotely through the network 
12. Embedded OS: are designed to work on small Microcontrollers usually are application Specific 
13. Mobile OS: OS that are specifically designed to run on mobile Devices. such as android and tablet

### Computer System Overview:
A computer system is collection of **Hardware, System and application Software, users, OS.**
hardware consist of CPU, memory, I/O devices which are altogether used to provide basic computing resources for the computer system.
An OS is core software that controls the execution of an application program and acts as an interface between the user of a computer and computer hardware.
Application programs are programs that perform specific tasks and perform system calls to communicate with the OS.
System Programs are the set of utility programs supplied with the OS to provide basic  services for the computer users
users are the people who interact with the computer system.

### functions of OS:
1. Memory Management: An OS deals with the allocation and deallocation of the memory and other storage devices to system programs as well as user programs
2. Processor Management: An OS deals with the assignment of Processor to different tasks 
3. Device Management: An OS deals with the co-ordination and assignment of the different output and input devices
4. File management: An OS deals with the storage of files and accessing these files
5. Error detecting: production of dumps, error messages, traces and debugging error 
6. Security: OS keeps track of authentication of programs and users to protect sensitive data
7. Control over system performance: An OS performs recording delays between request for a service and response from the system.
8. Coordination between Software and users: Coordination and assignment of compilers interpreters, assemblers and other software to various users of the computer system
9. job accounting: An Os keeps the track of time and resources used by the jobs and users

## types of OS:
#### Batch OS:
it is one of the oldest OS. In this the programs are collected together in a batch and sent to processing at once 
memory in batch OS is usually divided into two areas namely OS and user program area
batch processing is implemented by the kernel which resides in one part of computers memory the remaining memory is used for servicing a user job- the current job in the batch
**Advantages**: overhead per program is reduced, increased performance, huge amount of data can be processed efficiently, execution of job becomes fast
**Disadvantages**: No interaction is possible with the user while the job is being executed, batch systems are costly, it is difficult to debug a program in batch OS, due to lack of protection scheme one batch job can affect pending jobs, there is certain wastage of memory.

#### Multi programming OS:
more than one program or job can be executed at a time. Single CPU divides its time between more than one job. allow concurrent execution of jobs or program
more than one programs or jobs are present in the memory at a time
the job pool consist of number of jobs the OS picks job from the pool many jobs are kept in the memory simultaneously. the number  of jobs present in the memory at a time is called the degree of multiprogramming. if a job require I/o then OS switches to another job and executes it CPU is never idle 
**Advantages:** efficient memory utilization. High CPU utilization. More CPU throughput. Supports multiple simultaneous interactive user
**Disadvantages:** user cannot interact with job being executed. The programmer cannot modify a program to study its behavior while program is being executed. Jobs may have different sizes so powerful memory is required. CPU scheduling is must 

#### Multi tasking OS:
A running state of a program is called a process or task. A CPU handling multiple tasks at a time is known as multitasking. A multitasking OS can handle multiple tasks together by applying multiprogramming technique. It supports two or more processes running simultaneously. In multitasking environment os system ensures that multiple tasks run on a single system by sharing CPU time. 
**cooperative multitasking:** Let program decide when they want to run. programs decide when they wish to let other tasks run
**preemptive multitasking:** it moves the control of the cpu to the OS letting each process run for a given amount of time and then switching to another task. this prevents one process from taking complete control of the system and thereby making it seem as it if crashed this is the most common method used.
**Advantages:** helps in increasing the overall productivity of the user by performing a number of tasks at the same time
**Disadvantages:** it requite more system resources. CPU speed must be high.

#### Multiprocessor OS:
uses two or more processors within a computer two or more CPU's within a single computer system. 
**Asymmetric:** In this system a specific task is assigned to each processor the system has a master processor and other are slave processors. A master processor controls the system and slave processor follows the instruction to perform task.
**Symmetric:** in symmetric there is no master slave concept used all the processors are peer processor they perform all tasks within a OS
**Advantages:** it increased throughput by increasing the number of processors more work is done in a shorter period of time. can also save money compared to single systems because the processors can share peripherals. increases reliability. higher performance
**Disadvantages:** if one processor fails it will affect speed. Multiprocessor systems are expensive. Complex OS and large main memory is required 

#### Distributed OS: 
it is basically a computer network in which two or more autonomous computer are connected their hardware and software interconnections to facilitate communication. a distributed system consists of a collection of computers connected through a network and distribution middle ware which enables computers to coordinate their activities and to share the resources of the system.
**Advantages** reliable, speed, performance, Sharing of resources.
**Disadvantages**: troubleshooting, networking, complex, security.

#### Network OS:
runs on server and provides the server the capability to manage data, users, groups, security, application, and other networking functions
the primary purpose of the network os is to allow shared file and printer access among multiple computers in a network
**Advantages:** Centralized servers are highly stable, Security is server managed, upgrades to new technologies and hardware can be easily integrated into the system, remote access to servers is possible from different locations and types of system.
**Disadvantages** high cost of buying and running a server, dependency on a central location for most operations, regular maintenance and updates are required. 

## what does an OS do?
1. schedules all operations and manages all the computing resource
2. provides proper use of resources in the OS of the computer system
3. provide an environment for running user programs 
4. supports operations and services that require communication over network
5. provide an interface to the user to communicate with the system hardware
6. manages the computer system resources in an efficient manner 
7. provide security to ensure only authorized persons can access data and information or perform certain tasks on the computer system
8. executes user programs and to make solving user problems easier
9. provides file management which refers to storing and manipulating data 
10. provides overall control to the computer system

## OS operations:
Modern OS are interrupt-driven. The operating system sits idle if there is no event to occur, such as no process to execute.
**Interrupts and ISR**
Events are almost always signaled by the occurrence of an interrupt. For each type of interrupt, a separate segment of code in the OS determines what type of action should be taken. An ISR (Interrupt Service Routine) is provided to deal with the interrupt.
**Multi-programmed Environment**
In a multi-programmed environment, computer resources are shared among several programs simultaneously. Though sharing of resources improves resource utilization, it also increases problems. An error in one program can adversely affect the execution of other programs.

## Dual mode operation
The execution of operating system code and user code must be separated in order to ensure the correct execution of the program two separate modes are needed:
1) User mode
2) Kernel mode
A bit called mode bit is added to the hardware of the computer to indicate the current mode for kernel the bit is 0 and for user the bit 1 
the booting process starts in kernel mode whenever interrupt occurs the hardware switches from user mode to kernel mode
the transition form user mode to kernel mode occurs when the application requests the help of OS or an interrupt or a system call occurs 

## Operating System Structure

An Operating System (OS) is a software that manages computer hardware resources and provides a platform for running application software. The OS structure can be categorized into four main types: Simple, Monolithic, Layered, and Microkernel.

1. **Simple Operating System Structure**
	**Architecture**
	In a simple OS, all the system services and device drivers are part of a single kernel. The kernel provides a set of APIs for applications to interact with hardware resources.
	
	**Advantages**
	Efficient: Direct access to hardware resources, resulting in faster performance.
    Simple: Easier to develop and maintain due to a single kernel module.
    
	**Disadvantages**
	Security: A vulnerability in the kernel can compromise the entire system.
    Scalability: Adding new features or device drivers can make the kernel bloated and complex.
    
	**Examples**: Early versions of Windows, macOS, and Linux

2. **Monolithic Operating System Structure**
	**Architecture**:
	In a monolithic OS, all system services and device drivers are part of the kernel, which runs in supervisor mode. The kernel provides a set of APIs for applications to interact with hardware resources.
	
	**Advantages**:
	efficient: Direct access to hardware resources, resulting in faster performance.
    Simple: Easier to develop and maintain due to a single kernel module.
    
    **Disadvantages**:
    Security: A vulnerability in the kernel can compromise the entire system.
    Scalability: Adding new features or device drivers can make the kernel bloated and complex.
    
    **Examples**: Windows, macOS, and Linux (to some extent)

3. **Layered Operating System Structure**
	**Architecture:**
	In a layered OS, the system is divided into multiple layers, each providing a specific set of services. The layers are stacked on top of each other, with each layer relying on the services provided by the layer below it.
	
	**Layers:**
    **Hardware Layer**: The underlying computer hardware.
    **Machine Control Layer:** Manages hardware resources like CPU, memory, and I/O devices.
    **Process Management Layer:** Manages process scheduling, creation, and termination.
    **File System Layer:** Provides file management services like file creation, deletion, and access.
    **Network Layer**: Manages network communication and data transfer.
    **Application Layer:** Provides APIs for applications to interact with lower layers.
    
    **Advantages:**
    **Modularity**: Each layer can be developed, tested, and maintained independently.
    **Flexibility**: New layers can be added or removed as needed.
    **Scalability**: Easier to add new features or device drivers without affecting the entire system.
    
    **Disadvantages**
    **Complexity**: More complex to develop and maintain due to multiple layers.
    **Performance**: Additional overhead due to layer-to-layer communication.
    
    **Examples**: Modern versions of Windows, macOS, and Linux

4. **Microkernel operating system structure**
	**Architecture:**
	In a microkernel OS, the kernel is minimal and only provides basic services like process scheduling, inter-process communication (IPC), and memory management. Other system services and device drivers run in user mode as separate processes.

	**Advantages:**
	**Security**: Fault isolation ensures that a failure in one service doesn't affect the entire system.
    **Scalability**: Easier to add new features or device drivers without affecting the kernel.

	**Disadvantages:**
	**Performance**: Additional overhead due to IPC and context switching between user and kernel modes.
    **Complexity**: More complex to develop and maintain due to multiple user-mode processes.
    
    Examples: QNX, Symbian, and some embedded systems
    
![[OS structures.png]]

## Booting:
the process of starting the computer and loading the OS is known as booting.
Booting the system is done by loading the kernel into main memory and starting its execution 
the program called bootstrap loader is used to located the kernel and load it into the memory
on a computer system a small piece of code known as bootstrap loader locates the kernel loads it into memory and starts its execution 
when a cpu is powered up the instruction register is loaded with a predefined memory location and execution starts there at that location is the initial bootstrap loader which stores the location of kernel and loads it into the memory

## System calls:
System call provides an interface between a running program and an operating system 
a system call is the programmatic way in which a computer program requests a service from the kernel of the operating system 
the interface between a process and an operating system is provided by system calls. 
these calls are generally routines and are written in c and c++ 
the process is generally executing in user mode when it does a system call the control shifts to kernel mode which executes system call and then returns to user mode
the process executed in user mode till the system call interrupts 
after that the system call is executed in the kernel mode on a priority basis 
once system call execution is over the control returns to user mode
the execution of user process resumed in kernel mode

types of system call:
Process control: these system call deals with processes some examples of these include end kill abort load fork etc
File management: these types of system calls are used to handle or dealing with files examples include read delete open etc
device management: these system calls are used for device management examples include request device release device read and write device operations
Information maintenance: these system calls can handle information and its transfer between the operating system and the user program examples include get time or date set time or date
communication: these system calls are useful for inter process communication IPC examples of these include creating and deleting connection send and receive messages read and write messages etc.