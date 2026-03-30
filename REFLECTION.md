# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

I realized that multithreading is not only about creating threads, but also about managing their execution times and interactions with the common program logic. For instance, in this assignment, each process was represented by a Process object that implements the Runnable interface, and the scheduler used Thread objects to execute them. This was an interesting experience for me because I could see the distinction between the process itself and the Java thread executing it. Another interesting lesson I learned from this assignment was that the thread lifecycle becomes more understandable if it is associated with some kind of scheduling discipline, such as the Round-Robin discipline, because I could see the exact times at which a process was granted CPU access, suspended, and resumed in the queue. Finally, I learned that the lifecycle of a thread, including methods such as start(), join(), and sleep(), is directly affected by the execution order of the threads in the simulation. I was particularly interested in how the scheduler used join() to wait for the completion of the execution of a thread before switching to the next thread in the queue. I think this assignment made multithreading look more practical because I could see the effects of multithreading in the output of the program, rather than just reading about it in theory.

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

However, the most difficult part in this assignment was implementing waiting time tracking properly in Feature 3. At first, it seemed easy to calculate waiting time for a process. However, in Round Robin Scheduling, it is possible that a process is re-queued many times. This means that waiting time is not simply the time elapsed from its creation to its first execution. Rather, it is the total time that it has been waiting in the queues over its entire lifespan. Another part that was difficult in this assignment was understanding that every time it is re-queued, it is as if it is a new Thread, even though it is the same logical process. On top of that, there was also Unicode formatting in the starter code that caused problems during compilation on Windows. This part was also difficult as it was combining operating systems and Java thread behavior at once.

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

I overcame these challenges through small steps and tests. For instance, I first read and understood the README and starter code for the scheduler loop. Then, I implemented one feature at a time and checked if it compiled and ran as expected. For the waiting time problem, I tracked the life cycle of a process through the queue and pinpointed exactly where it enters the ready queue and resumes execution. This guided me on where to record time and add up waiting time. When the compiler complained about the file encoding, I checked if it was a specific compile command and if it was set to UTF-8. The best approach in solving these problems was to debug. For instance, I read the code, implemented a small change, and then ran it. After that, I checked if it worked as expected.


---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

The concepts of multithreading are used in many practical scenarios in which multiple threads need to proceed concurrently. One such scenario is in a web browser, in which multiple threads can be used for rendering web pages, accepting user input, sending network requests, and executing scripts in the background without freezing the user interface during such activities. Another scenario is in a web server in which multiple client requests are handled concurrently, in which multiple threads can be used to process different client requests without causing all clients to wait for one client's long-running request to finish. The idea of Round-Robin, which we learned in this assignment, is also used in operating systems in which time-sharing is done among running processes. In games and other multimedia applications, multiple threads can be used for rendering, audio processing, physics simulation, and input processing concurrently. This assignment has taught me that multithreading is not only used in programming but also in time-sharing in practical scenarios. It has also taught me that proper management of multiple threads is also required because threads are only useful if their execution is properly managed.


---

## Additional Reflections (Optional)

### What would you like to learn more about?

I would like to explore synchronization mechanisms such as `synchronized`, locks, semaphores, and monitors in more depth. I also want to gain a clearer understanding of race conditions and deadlocks, since they appear to be the next important step after learning the basics of thread creation and scheduling.


---

### How confident do you feel about multithreading concepts now?

Intermediate

I feel more confident than before since I am able to understand the basic lifecycle of threads, how a scheduler can control the execution of a program, and how timing information can be tracked within a simulation. I need more practice working on complex problems involving concurrency, especially how to protect shared data and debug complex thread interactions.


---

### Feedback on the assignment

I found this assignment helpful because it related Java programming with the concept of operating systems in a real sense. The code provided made it easier to concentrate on understanding the scheduling behavior. The feature-based structure also provided guidance in the development process. The documentation section was also helpful in that it made me explain my understanding of the code rather than just implementing it.
