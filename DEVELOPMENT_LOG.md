# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 24, 2026, 7:15 PM]
**What I did**: I created the repository, modified the code to include my student ID

**Details**:
- I cloned my GitHub repository to my computer
- I opened SchedulerSimulation.java, reviewed the code, and checked how it works
- I checked that the random seed was using my student ID to make sure that the output of the simulation was unique
- I read the README to get an overview of all four parts of the assignment

**Challenges**: I was having difficulty understanding the starter code because there was a lot of formatted output

**Solution**: I read the code from top to bottom, separated the code for the Process class from the rest of the code, and took some brief notes on what each section of the code was for

**Time spent**: 35 minutes

---

### Entry 2 - [March 30, 2026, 5:00 PM]
**What I did**: Implemented feature 1 by adding priority to the processes

**Details**:
- Added a priority attribute to the Process class
- Assigned random priority values between 1 and 5 to the processes
- Updated the message displayed in the ready queue to display the priority value
- Compiled and ran the program to verify that each process displayed its priority value as it entered the queue

**Challenges**: The priority had to be assigned in the constructor and remain associated with the process as it was re-entered into the queue

**Solution**: Added a getter for priority and passed it as an argument to the constructor for each process

**Time spent**: 40 minutes

---

### Entry 3 - [March 30, 2026, 5:30 PM]
**What I did**: Implemented feature 2 for counting context switches

**Details**:
- Added a static counter variable in SchedulerSimulation
- Increased the counter whenever a process's thread started running
- Printed out the total number of context switches at the end of execution
- Again, tested the program and verified that it looked correct

**Challenges**: Determining exactly where to count context switches in this program

**Solution**: Placed it right before currentThread.start() since that is when the CPU is given to a process in the scheduler loop

**Time spent**: 30 minutes

---

### Entry 4 - [March 30, 2026, 6:00 PM]
**What I did**: Implemented Feature 3 for waiting time tracking

**Details**:
- Added columns to track process creation time, queue entry time, and waiting time
- Started tracking time when each process enters the ready queue
- Updated process details when the scheduler starts running the process
- Added a table with details of process name, burst time, and waiting time at the end

**Challenges**: Waiting time is not continuous, as it is possible for a process to leave the CPU and re-enter the queue

**Solution**: I tracked each time the process enters the queue using System.currentTimeMillis() and added waiting time before dispatching each process, which includes waiting time for all periods.

**Time spent**: 55 minutes

---

### Entry 5 - [March 30, 2026, 6:30 PM]
**What I did**: I checked all three features to see if they work as expected

**Details**:
- I compiled the program using UTF-8 encoding
- I ran the simulation in full, checking the priority output, context switch total, and waiting time table
- I checked to see if the final output was consistent with the requirements in the README file and the PDF
- I checked to see if the old Round-Robin logic was still functioning

**Challenges**: The source file contains Unicode characters, such as box drawing characters, which are used to format the output, but the default settings for Java on Windows would cause encoding issues

**Solution**: I compiled the source file using javac -encoding UTF-8 SchedulerSimulation.java, which resolved the issue with the formatted output

**Time spent**: 35 minutes

---

### Entry 6 - [March 30, 2026, 7:00 PM]
**What I did**: I completed the documentation and GitHub work.

**Details**:
- I wrote my answers in the files for the reflection question and the technical question.
- I wrote this log.
- I made individual commits for each feature with proper commit messages.
- I pushed all the completed features into the GitHub repository after testing them.

**Challenges**: I had to change my GitHub account first before pushing my commits.

**Solution**: I used my correct GitHub account, verified my repository, and then pushed my feature commits.

**Time spent**: 45 minutes

---

## Summary

**Total time spent on assignment**: 3 hours 40 minutes

**Most challenging part**: The most challenging part was to track the waiting time for multiple re-queues in an accurate manner, along with ensuring the correctness of the logic for the scheduler

**Most interesting learning**: The most interesting learning experience was to see how a process could be represented by multiple thread objects over various rounds, whereas the process state would remain the same

**What I would do differently next time**: I would have planned the documentation in an earlier stage, so that some of the important output examples could be saved for use in the report files