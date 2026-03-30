# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

A process is defined as an independent program in execution with its own memory space and resources. On the other hand, a thread is defined as a smaller execution unit within a program in execution. The memory and resources are shared by different threads within a program. Due to this difference, it is easier to manage and create threads compared to processes. This is because creating and handling threads is faster compared to handling processes. In this assignment, we used threads due to the fact that only CPU time sharing between tasks within a Java program had to be simulated. There was no need to invoke other operating system programs. This is due to the fact that if we had used other programs, it would have been difficult to manage and share information like the ready queue, process map, and time values.


---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

If the process is not finished within its allocated time quantum, the process is suspended and put back into the ready queue, allowing the execution of other processes first. It is not given continuous access to the CPU, as Round Robin is based on fairness and time-sharing concepts. After the execution of the remaining ready processes, the process is executed again at some later time with another thread. From the output of my program, P1 executed one time quantum, had remaining time, and was put back into the ready queue.

Example from my output:
```
P1 executing quantum [3000ms]
P1 completed quantum 3000ms | Remaining time: 328ms
P1 yields CPU for context switch
P1 (Priority: 5) enters the ready queue | Burst time: 3328ms
```

**Explanation of example:**
The above output indicates that process P1 was running for one quantum of time, which is 3000 ms. However, it was still having 328 ms of time left. Thus, it was not able to complete. Hence, it gave up the CPU and returned to the ready queue. The scheduler allowed all the processes to execute once again before P1 was scheduled. This is the main behavior of the Round-Robin scheduling algorithm.

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

In this simulation, the logical process P1 can be associated with more than one Java Thread object, as a new thread is created for every re-queuing of the logical process. The state change descriptions above are for a single dispatch cycle of P1, and this continues if P1 still has remaining time. This helped me understand that the process data remains the same, but a new thread object is created for every round.

1. **New**: P1 is in the 'New' state immediately after addProcessToQueue() creates new Thread(process) for it.

2. **Runnable**: P1 is in the 'Runnable' state after currentThread.start() is called by the scheduler. This is because, at this point, P1 is ready to be selected by the JVM for execution.

3. **Running**: P1 is in the 'Running' state while its run() method is executing and consuming CPU time.

4. **Waiting**: During execution, P1 invokes Thread.sleep(stepTime) to simulate CPU time consumption in stages. This makes P1 enter the 'Waiting' state until sleep is completed.

5. **Terminated**: P1 is in the 'Terminated' state when its run() method completes its execution. If P1 still has time left, then the scheduler creates a new thread for the next round of execution. If not, then P1 is complete.

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Interactive Operating System Tasks

**Description**: 
An operating system may have numerous active tasks, and all of them may need to be executed within a certain time. The tasks may include a text editor, a browser, a terminal, and a service. However, no task should be able to lock out the entire operating system for a long time.

**Why Round-Robin works well here**: 
Round Robin works well for this scenario since all the active tasks are allocated a certain time, and then the operating system moves on to the next task. This way, all the tasks are executed within a certain time, and no task locks out the entire operating system.

### Example 2: Multi-client Server Handling Requests

**Description**: 
A server could have multiple client sessions or worker threads that need CPU time allocation to serve all the requests. Some of these processes might be short, while others could be longer.

**Why Round-Robin works well here**: 
This is where Round Robin scheduling is effective in allocating CPU time among all active worker threads. A long-running process should not be allowed to dominate all other processes. Round Robin scheduling is effective in situations where there are many clients that need CPU time allocation.
---

## Summary

**Key concepts I understood through these questions:**
1. The distinction between process and thread in terms of resources, memory, and overhead.
2. The process of Round-Robin Scheduling, which involves re-queuing unfinished processes.
3. The states of threads in the process of creation, execution, waiting, and termination.

**Concepts I need to study more:**
1. Synchronization of processes, protection of shared data.
2. Deadlocks, debugging of concurrency.
