In an OS multiple processes are executing concurrently this can lead to issues if multiple processes try to access a same shared resource and can lead to inconsistency of data 
Synchronization is the process of coordinating the execution of processes in such a way that no two process can have access to a shared resource at the same time 
one the basis of synchronization the process can be categorized into two
1. Independent process -- execution of one process does not affect other process
2. cooperative process -- execution of one process affects other process 

Race Condition --
	Race condition is a problem where more than one process manipulate a shared resource at the same time and the outcome depends on the order of the execution

Critical Section Problem --
	- to avoid race condition one must identify the codes in critical section in each process 
	- critical section is a code segment that can be accessed by only one process at a time. it contains shared variables which need to be synchronized to maintain consistency of data variables 
	- the important feature of the system is that when one process is executing in its critical section no other process is allowed to execute in its critical section
	![[critical section.png]]
	1. entry section --
		each process must request permission to enter its critical section processes may go to critical section only through entry section
	2. Exit section -- 
		each critical section is terminated by exit section
	3. Remainder Section --
		the code after exit section is remainder section


> [!IMP] Solution to critical section problem must satisfy the following condition
> **1. Mutual Exclusion:** Only one process can be in the "critical section" at a time.
> **2. Progress:** If no process is currently in the critical section and others are waiting, a decision must be made about who goes next. This decision can't be delayed forever
> **3. Bounded Waiting:** There's a limit to how many times other processes can enter the critical section after a process has requested to do so


## What is a Semaphore?

A semaphore is a variable or abstract data type used to control access to a common resource by multiple threads or processes in a multithreaded or multiprocessor environment. It helps in managing the access to shared resources and preventing critical section problems.

#### Operations on Semaphores

Semaphores have two primary operations:

##### Wait (P) Operation

- This operation decrements the semaphore value by 1. If the semaphore value is greater than 0, the operation succeeds, and the process continues execution. However, if the semaphore value is 0, the process is blocked and added to the semaphore's waiting queue until the semaphore value becomes positive again.
```
	Wait(S){
		while(S<=0);
		s--;
	}
```

##### Signal (V) Operation

- This operation increments the semaphore value by 1. If there are processes waiting in the semaphore's queue (i.e., the pre-increment value was negative), one of the waiting processes is removed from the queue and resumes execution. Otherwise, the increment simply increases the available resource count.
```
	Signal(S){
		s++;
	}
```

#### Types of Semaphores

There are two main types of semaphores:

##### Binary Semaphores

- Binary semaphores can have only two values: 0 and 1. They are similar to mutual exclusion locks (mutexes) and are used to ensure that only one process can access a critical section at a time. If the value is 1, a process can enter the critical section; if the value is 0, the process must wait.

##### Counting Semaphores

- Counting semaphores can have any non-negative integer value. They are used to manage resources where multiple processes can access the resource simultaneously up to a certain limit. The semaphore value represents the number of available resources. When the value reaches 0, any further attempts to decrement the semaphore will block the calling process until resources are released.

## Bounded Buffer Problem (Producer and Consumer Problem)
The Bounded Buffer Problem, also known as the Producer-Consumer Problem, is a classic synchronization problem in operating systems and concurrent programming. 

### Problem Description

- **Buffer**: There is a finite buffer of size N that can store N data items.
- **Producers and Consumers**: Multiple producer processes write data into the buffer, and multiple consumer processes read data from the buffer.
- **Synchronization Need**: The producers and consumers must be synchronized to prevent data races, buffer overflows, and underflows.

### Key Issues

- **Buffer Overflow**: Producers must not write to a full buffer.
- **Buffer Underflow**: Consumers must not read from an empty buffer.
- **Mutual Exclusion**: Only one process can access the buffer at a time to prevent data corruption.

### Solution Using Semaphores

To solve this problem, we use three semaphores:

- `empty`: Counts the number of empty slots in the buffer.
- `full`: Counts the number of filled slots in the buffer.
- `mutex`: Ensures mutual exclusion when accessing the buffer.

### Pseudocode

#### Producer Function

```
do {
    wait(&empty);// Wait until there is an empty slot
    wait(&mutex);// Acquire the mutex lock
    // Insert data into the buffer
    signal(&mutex);// Release the mutex lock
    signal(&full);// Signal that a slot is now full
} while (TRUE);
```

#### Consumer Function

```
do {
    wait(&full);// Wait until there is a filled slot
    wait(&mutex);// Acquire the mutex lock
    // Remove data from the buffer
    signal(&mutex);// Release the mutex lock
    signal(&empty);// Signal that a slot is now empty
} while (TRUE);
```


## Dining Philosophers problem

- There are five philosophers sitting around a circular table.
- Each philosopher has a plate of spaghetti in front of them.
- There are five forks placed between each pair of adjacent philosophers.
- Each philosopher needs two forks to eat: one from their left and one from their right.
- Philosophers alternate between thinking and eating.
- To eat, a philosopher must pick up both adjacent forks.

	A naive approach involves using semaphores to represent the chopsticks. Each philosopher waits to pick up the left chopstick, then waits for the right chopstick.
	initially the elements of chopstick are initialized to 1 as the chopsticks are on the table and not picked up by anyone

```
void philosopher(int i) {
    while (1) {
        wait(&chopstick[i]); // Pick up left chopstick
        wait(&chopstick[(i + 1) % 5]); // Pick up right chopstick
        eat();
        signal(&chopstick[i]); // Put down left chopstick
        signal(&chopstick[(i + 1) % 5]); // Put down right chopstick
        think();
    }
}
```

in the above structure the first wait operation is performed on `chopstick[i]` and `chopstick[(i+1) % 5]` this means that the philosopher i has picked up the chopstick on his side and then eating is performed 
after that signal operation is performed on `chopstick[i]` and `chopstick[(i+1) % 5]` indicating the philosopher has put down the chopsticks 