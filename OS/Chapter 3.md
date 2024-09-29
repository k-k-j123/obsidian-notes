## Basic Scheduling Concept
- CPU scheduling is important because the overall system utilization and performance as well as the response time of processes depend on how the processes are scheduled to run
- the scheduler is the kernel component responsible for deciding which programs should be executed on the CPU. A scheduler selects a job/task which is to be submitted next for execution
-  scheduler selects one of these programs for execution on the CPU A preempted program is added to the set of programs waiting for the CPU

## Scheduling parameters
1. CPU utilization: is defined as the percentage of time the CPU is busy in executing processes for higher utilization i.e CPU must not be idle and must be always keep executing some process.
2. Throughput: one measure of work is the number of processes that are completed per time unit called throughput.
3. Turnaround time: it is the difference between the time a process enters the system and the time it exits the system. it is the total time CPU takes to execute the process.
4. Waiting time: the time that a process has to wait in the ready queue before it is executed by the CPU
5. Balanced Utilization: it is defined as the percentage of time all the system resources are busy