# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Jawad Abdulaziz Jdoua |
| **Student ID** | 446050595 |
| **University Email** | 446050595@std.psau.edu.sa |
| **GitHub Username** | 446050595 |
| **Repository Link** | (https://github.com/446050595/OS-Assignment3-Jawad-Jdoua) |
 
---

## 🎥 Video Link

**Video Link**: (https://drive.google.com/file/d/1120c4DGeMjDU-y6iSXdcm8GgBBEMs3WD/view?usp=sharing)

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45

---

## Your Development Log

### Entry 1 - [11/20]
**What I did**:Set my student ID and prepared my repository for the assignment.

**Details**:Set my student ID to 446050595 in the Java source code.

Checked my GitHub repository.

Committed the student ID change to GitHub.

**Challenges**:Making sure my repository and student information were correctly set up before starting the synchronization features.

**Solution**:Checked the repository and confirmed that my student ID was set correctly.



**Time spent**:20

---

### Entry 2 - [11/21]
**What I did**:Implemented Feature 1 to protect the shared ready queue.

**Details**:Added a ReentrantLock to the ReadyQueue class.

Used the lock to protect shared queue data from simultaneous access by CPU threads.

Used try and finally to make sure the lock is released.

Committed and pushed Feature 1 to GitHub.



**Challenges**:Multiple CPU threads could access the ready queue at nearly the same time, which could cause race conditions.



**Solution**:I used mutual exclusion with a ReentrantLock to control access to the shared queue.

**Time spent**:20

---

### Entry 3 - [11/22]
**What I did**:Implemented Feature 2 to protect the shared statistics.

**Details**:Added a ReentrantLock to protect the shared statistics.

Protected the update methods for contextSwitchCount, completedProcessCount, and totalServiceTime.

Protected the getter methods as well.

Committed and pushed Feature 2 to GitHub.



**Challenges**:Several CPU threads could update the same counters at the same time, causing lost updates.

**Solution**:I used a shared statistics lock and made sure that the lock was released in a finally block.

**Time spent**:30

---

### Entry 4 - [11/22]
**What I did**: Implemented Feature 3 using a counting semaphore.

**Details**:Added a counting semaphore to the ReadyQueue class with an initial value of zero.

Called release() when a process was added to the queue.

Used acquire() so CPU threads wait until a process becomes available.

Added a shutdown signal to wake up CPUs when the last process finishes.

Committed and pushed Feature 3 to GitHub.

**Challenges**:I needed to make sure that CPUs blocked on the semaphore could still terminate when all processes were completed.



**Solution**:I added a shutdown signal using release(totalCPUs) when the last process finished.



**Time spent**:20

---

### Entry 5 - [11/24]
**What I did**:Tested the final version of the synchronization program.



**Details**:Compiled the Java program using javac SchedulerSimulationSync.java.

Ran the program five times.

Checked the four verification lines in every run.

Confirmed that all shared values were consistent and busy-waiting polls were zero.

Confirmed that the program terminated without the watchdog message.

**Challenges**:The compiled .class file was missing when I first tried to run the repeated tests.



**Solution**:: I compiled the Java source file again and ran the tests using java -cp . SchedulerSimulationSync.



**Time spent**:15

---

### Entry 6 - [11/24]
**What I did**:Performed repeated tests on the final synchronization program.

**Details**:Recompiled SchedulerSimulationSync.java.

Executed the program five times.

Verified that all 20 processes completed successfully in every run.

Confirmed that context switches were 35 and total service time was 50408 ms.

Confirmed that busy-waiting polls remained zer


**Challenges**:The compiled Java class file was missing when I first attempted to run the repeated tests.



**Solution**:Recompiled the source code and executed the program again using java -cp . SchedulerSimulationSync.



**Time spent**:15

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

I learned that synchronization is important when multiple threads access shared data at the same time. A race condition can happen when two threads read and update the same variable before either update is completed. In this assignment, I used ReentrantLock to protect critical sections in the ready queue and shared statistics. I also learned that using try and finally makes sure the lock is released even if an exception happens. The counting semaphore helped me replace busy waiting with blocking, so CPUs wait until a process is available. I was surprised that the original starter could have race conditions even though the program looked simple

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part was implementing the counting semaphore and making the CPUs stop correctly. I understood that acquire() makes a CPU wait when no process is available, but I had to think about what happens when all processes finish. If the other CPUs stay blocked, the program may never terminate. I also needed to understand the correct initial value of the semaphore. I solved this by initializing it to zero and releasing it whenever a process was added. The shutdown signal was important because it allowed the blocked CPUs to wake up and terminate.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I overcame the challenges by working on one feature at a time instead of changing everything together. I read the assignment instructions and checked the Java code to understand how the ready queue and CPU threads worked. After implementing each feature, I compiled and ran the program to check for errors. When Java could not find the main class during repeated testing, I compiled the source file again using javac. I also ran the final program five times and checked the verification results in every run. Asking for help and following the errors step by step helped me understand the synchronization problems better.
## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is useful in banking applications when multiple transactions access the same account balance. A lock can prevent two transactions from updating the balance incorrectly at the same time. It is also useful in ticket booking systems, where multiple users may try to reserve the same seat. A shared database counter on a website also needs protection when many users update it simultaneously. Semaphores can be used to control access to a limited number of resources, such as available printers or database connections. These examples are similar to my assignment because multiple threads share resources and need to access them safely.



### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

The original starter had a race condition because multiple CPU threads could read and update the same shared counter without mutual exclusion. For example, CPU-1 and CPU-2 could both read contextSwitchCount as 12, then both calculate 13 and write it back, so one increment is lost. The RaceWindow.pause() makes this problem easier to reproduce, but the same problem can happen on a real machine because a thread can be interrupted between reading and writing a shared value. Race conditions are difficult to detect because they depend on thread timing and may not happen in every run.



[PASTE YOUR REAL ORIGINAL STARTER OUTPUT HERE. If it crashed, paste the exception and WATCHDOG message instead. Do not use the final output in this section.]
[Original starter output is still needed]
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Context switches (quanta executed)     expected 35       observed 35       ✔
Completed processes                    expected 20       observed 20       ✔
Total service time (ms)                expected 50408    observed 50408    ✔
Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
✔ All shared values are consistent.
```
[Paste the verification block of your final version here (all lines ✔)]
```

**Explanation of the timeline:**
CPU-1 reads contextSwitchCount and gets 12.

CPU-2 reads the same value before CPU-1 writes its update.

CPU-1 writes 13.

CPU-2 also writes 13 because it calculated the value from the old value 12.

The counter becomes 13 instead of 14, so one update is lost.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I used a ReentrantLock in ReadyQueue to protect the shared queue data, including the list and map. I used one separate ReentrantLock in SharedStats to protect the three statistics and their getter methods. I chose one lock for the statistics because it makes the code simpler and protects all three counters consistently, although independent updates may wait for each other. The ready queue has a different lock because it is a separate shared resource, and separating the locks avoids unnecessary blocking between queue operations and statistics operations. The locks provide mutual exclusion, but the default ReentrantLock is not fair, so bounded waiting is not guaranteed.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the original starter, a CPU used busy waiting by checking the ready queue repeatedly and sleeping for 20 milliseconds when the queue was empty. This wastes CPU time, and the original starter's busy-waiting poll count should be taken from my original run. In my final code, the semaphore starts at zero because no process has been signalled as available before the queue receives processes. After the initial 20 add() calls, its value represents 20 available processes, and each acquire() consumes one available-process signal. When the last process finishes, the last CPU calls release(SharedStats.totalCPUs) to wake blocked CPUs so they can terminate instead of waiting forever.



## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
This is similar to the Producer-Consumer problem, also known as the bounded-buffer problem. The ready queue is the shared buffer, and the CPU workers are consumers when they take processes from it. They can also act as producers when they re-enqueue processes that have not finished their execution.
**Classical problem and roles**:
[Name the problem; who is the producer, who is the consumer?]

**Semaphores for a bounded queue (name and initial value)**:
[Name the three semaphores and their initial values.]

**Deadlock scenario and prevention**:
[Describe the scenario and the necessary condition you would break.]

## Summary

**Key concepts I understood through these questions:**
1.
2.
3.

**Concepts I need to study more:**
1.
2.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
