---
tags:
  - CS446
---
how the [[Operating systems|Operating system]] determines which [[Processes|Process]] to run
- if $0$ runnable, run idle loop (or halt CPU)
- if $1$ runnable, run that process
- if $> 1$ runnable, must make scheduling decision

simplistic $1$st idea: scan process table for first runnable process
- expensive and unfair (smaller PIDs prioritised)

better idea: FIFO scheduling
- put tasks on back of [[Queues|Queue]], pull them from front:
		- Pintos does this - see `ready_list` in `thread.c`

even better: priority scheduling

## How to Regain Control
- must switch from user mode to kernel mode

cooperative multitasking:
process voluntarily yield control back to operating system
- how/when? with system calls that relinquish CPU
	- trustworthiness: operating system needs to trust user process

true multitasking:
operating system "preempts" process by periodic [[Interrupts]]
- processes are assigned time slices (quanta) of execution
- dispatcher counts timer interrupts before [[Context switching|Context switch]]
	- operating system needs to trust no one

### Preemption
- temporarily interrupting an executing task, with the intention of resuming it later
- taking over performed by an external preemptive schedular with no assistance/cooperation from the task

### Cooperative Multitasking: Yielding Control of CPU
- voluntarily, e.g. `sched_yield`
- forced, e.g. on a system call, page fault, illegal instruction, etc.


### True Multitasking: Preemption
- periodic timer interrupt
	- indicates that running process used up time slice (quantum), schedule another
		- time slice: the period of time for which a process is allowed to run in preemptive multitasking system
	- (device) interrupt
		- disk request completed / packet arrived on network
			- process previously waiting now becomes runnable

## Scheduling Goals
scheduling works at two levels in an operating system
- determining the multiprogramming level - number of jobs loaded into memory
	- moving jobs to/from memory called "swapping"
- deciding what job to run next to guarantee "good service"
	- what constitutes "good service" can vary across different criteria

associated operations: long-term scheduling and short-term scheduling decisions
- long-term scheduling happens infrequently
	- significant overhead in swapping a process out of memory
- short-term scheduling happens frequently
	- want to minimise the overhead of scheduling
	- want fast context switches, fast process state queues manipulation

## Scheduling Considerations/Restrictions

### Starvation
- when a process is prevented from making progress because some other process holds the resource it requires
	- resource could be the CPU, or a lock

- starvation usually a side-effect of the scheduling algorithm
	- e.g., a high-priority process always preventing a low-priority process from running
	- e.g., one thread always beating another when acquiring a lock
- starvation can also be a side-effect of a simplistic [[Synchronisation]] algorithm
	- e.g., a constant supply of readers that always blocks out writers

## Scheduling Criteria
how the effectiveness of a scheduling algorithm is measured:
- arrival time (AT): time instance that process enters the ready state
- response time (RT): time interval from process arrival to first response (initial getting of CPU) (i.e., time initially spent in ready state)
	- $T_{ \text{ arrival } } - T_{ \text{ start } }$ (lower is better)
- CPU utilisation (%CPU): fraction of time CPU spends doing work (higher is better usually)
- throughput: number of processes that complete per unit time
	- number of jobs/time (higher is better)
- turnaround time (TT): time interval from process arrival to its completion
	- $T_{ \text{ complete } } - T_{ \text{ arrival } }$ (lower is better)
- burst time (BT): time interval required by the process for its uninterrupted execution
- waiting time (WT): total time process spends in the ready queue not executing on the CPU
	- $\text{ WT } = \text{ TT } - \text{ BT }$ (lower is better)
- average waiting time (AWT): time interval each process waits in ready queue on average

which scheduling criteria to us
- batch systems
	- aims for job: throughput, turnaround time (supercomputers)
- interactive systems
	- aim to minimise response time for interactive jobs (PC)
		- utilisation and throughput are often traded off for better response time
- usually optimise average measure
- sometimes also optimise for min/max or variance
	- e.g., minimise the maximum response time
	- e.g., users prefer predictable response time, over a faster but highly variable response time

## Scheduling Decision
when is a CPU scheduled? scheduling decisions may take place when a process
1. switches from running to waiting state
2. switches from running to ready state
3. switches from new/waiting to ready state
4. exist

- non-preemptive schedulers use $1$ and $4$ points only
- preemptive schedulers run at all four points

## Scheduling Jobs With Computation & I/O
- scheduling algorithm can also improve throughput
	- if jobs require both computation and I/O
- CPU is one of several devices employed by jobs
	- CPU runs compute jobs, disk drive runs disk jobs, etc.
	- with network, part of a job may run on remote CPU
- scheduling single-CPU system with $n$ I/O devices $\rightarrow$ like scheduling for an asymmetric (e.g. $n + 1$) - CPU multiprocessor
	- result: when all I/O devices and CPU do work $\rightarrow (n + 1)$-fold throughput gain 

### First-Come First-Serve (FCFS)
run jobs in the order that they arrive:
- e.g., $P_1$ needs $24$ seconds, $P_2$ needs $3$ seconds, and $P_3$ needs $3$ seconds
	- assume $P_2$, $P_3$ arrived immediately after $P_1$, we will have:
- throughput: $3$ jobs / $30$ seconds = $0.1$ jobs per second
- turnaround time: $P_1$:$24$ seconds, $P_2$:$27$ seconds, $P_3$:$30$ seconds
	- average TT: $(24 + 27 + 30) / 3 = 27$
- waiting time: $P_1$:$0$ seconds, $P_2$:$24$ seconds, $P_3$:$27$ seconds
	- average WT: $(0 + 24 + 27) / 3 = 17$

if we had scheduled things differently:
- e.g., $P_1$ needs $24$ seconds, $P_2$ needs $3$ seconds, and $P_3$ needs $3$ seconds
	- schedule $P_2$, $P_3$ first, then $P_1$, we have:
- throughput: $3$ jobs / $30$ seconds = $0.1$ jobs per second
- turnaround time: $P_1$:$30$ seconds, $P_2$:$3$ seconds, $P_3$:$36$ seconds
	- average TT: $(30 + 3 + 6) / 3 = 13$ (previous: $27$)

scheduling algorithm can reduce average TT
- minimising waiting time can improve response time (RT) and turnaround time (TT)

FCFS algorithm is non-preemptive
- once CPU time has been allocated to a process, other processes can get CPU time only after the current process has finished or gets blocked
- this property of FCFS scheduling is called the convoy effect

### Shortest Job First (SJF)
choose the job with the smallest expected CPU burst time (BT):
- e.g. three jobs available, CPU bursts are $P_1$:$8$ seconds, $P_2$:$4$ seconds, $P_3$:$2$ seconds 
- waiting time (WT): $P_1$:$6$ seconds, $P_2$:$2$ seconds , $P_3$:$0$ seconds 
	- average waiting time (AWT): $(0 + 2 + 6) / 3 = 2.67$

SJF has provably optimal (minimum) average waiting time (AWT)
- as long as preemption is not allowed

previous example
- three jobs available, CPU bursts are $P_1$:$8$ seconds, $P_2$:$4$ seconds, $P_3$:$2$ seconds
	- number of possible schedules: $3!$

two schemes
- non-preemptive: once CPU given to the process it cannot be preempted until it completes its CPU burst
- preemptive: once a new process arrives, if its CPU bursts is less than remaining time of currently executing process $\rightarrow$ preempt current process
	- known as the shortest remaining time first (SRTF)
		- advantages: reduces average waiting time (AWT)

#### Overview
schedule the process with the shortest burst time
- degrades to FCFS if processes have the same burst times (BTs)

benefits
- minimises average waiting time (AWT); provably optimal if no preemption is allowed
- shortest remaining time first (SRTF) covers case of preemptive scheduling

limitations
- can potentially lead to unfairness or starvation of long jobs
- impractical: difficult to know process's CPU burst time (BT) beforehand
	- estimate CPU burst length based on past
		- e.g. exponentially weighted moving average (EWMA)
			- $t_n$ actual length of process's $n$th CPU burst
			- $\tau_{n + 1}$ estimated length of process's $(n + 1)$th CPU burst

## Exponentially Weighted Moving Average
technique used for timeseries smoothing

## Round Robbin (RR) - Preemptive Scheduling
- solution to fairness and starvation
	- each job is given a time slice called a quantum
	- preempt job after duration of a quantum
	- when preempted, move to back of FIFO queue
- advantages:
	- fair allocation of CPU across jobs
	- low average waiting time (AWT) when job lengths vary
	- good for responsiveness for a small number of jobs
- disadvantages:
	- context-switches are frequent and need to be very fast
	- varying-sized jobs are good - what about same-sized jobs?
		- assume two jobs of burst time (BT) $= 100$ seconds each:
		- even if context switches were free:
			- average turnaround time (ATT) with RR $= 199.5$ seconds
			- average turnaround time (ATT) with FCFS $= (100 + 200) / 2 = 150$ seconds
- how to pick quantum?
	- should be larger compared to context switch cost
	- should be larger than the majority of bursts
	- but not so large that system reverts to FCFS-like behaviour
- typical values: 1 - (order-of:) $100$ msec

## Priority Scheduling
- associate a numeric priority with each process
	- e.g., smaller means higher-priority (Unix/BSD) - vs. - smaller means lower-priority (Pintos)
- give CPU to the process with highest-priority
- priority scheduling is general approach (applies to both preemptive or non-preemptive strategies)
	- obvious correlation with previous: SJF $\equiv$: $\frac{1}{ \text{ expected CPU Burst Time (BT) } }$

problem: starvation - jobs with low-priority could wait indefinitely
solution:
- "age" jobs
	- increase priority as a function of waiting time (WT)
	- decrease priority as a function of occupied CPU utilisation time

## Priority Inversion
caveat using priority scheduling with synchronisation primitives
- priority scheduling rule:
	- 1) always pick the highest-priority thread ...
	- 2) unless a lower-priority thread is holding a resource the higher-priority one has requested
- potential priority inversion problem setupL
	- two tasks initially:
		- $H$ at high-priority
		- $L$ at low-priority
	- then another tasks arrives:
		- $M$ at medium-priority (can preempt $L$)

two tasks: $H$ at high-priority, $L$ at low-priority
- $L$ acquires lock $k$ for exclusive use of a shared resource $R$
- $L$ is preempted; $H$ gets picked to run (priority-queue schedular)
- $H$ tries to acquire lock $k$, but it gets blocked until $L$ releases lock $k$ (i.e., is finished using $R$)
- $L$ gets picked up to run again; makes some progress but doesn't release lock $k$ just yet ...
- $M$ enters system medium-priority; $H$ is still blocked on lock $k$, so $M$ gets picked to run due to its higher-priority over $L$ (priority-queue schedular)

i.e., $L$ unable to release $k$ in time, $H$ unable to run despite having higher-priority than $M$

has happened in real-word software
- the root cause for a famous Mars PathFinder failure in 1997
- low-priority data gathering task and a medium-priority communications task prevented the more critical high-priority bus management task from running

## Priority Donation
if a thread attempts to acquire a resource (lock) that is currently being held, it donates its effective priority to the holder of that resource. this must be done recursively until a thread holding no locks found, even if the current thread has a lower-priority than the current resources holder
- i.e., whenever a high(er)-priority task has to wait for some shared resource that is currently held by an executing low(er)-priority task:
	- the low(er)-priority task will temporarily be assigned the priority of the highest-priority task waiting on that resource, for the duration of its use of the shared resource
- how it works
	- since the low(er)-priority task's priority gets temporarily boosted, it keeps any medium-priority tasks from getting picked by the priority schedular over the (originally) low(er)-priority task
		- once resource is released, low(er)-priority task returns to its original low(er)-priority value

example $1$: three tasks: $H$ (prio 2) - $M$ (prio 4) - $L$ (prio 8)
- $L$ holds lock $k$
- $M$ requests lock $k \rightarrow L$ priority raised to $L' =$ `max_prio`$(M;L) = 4$
- then $H$ requests lock $k \rightarrow L$ priority raised to $L'' =$ `max_prio`$(H;L) = 2$

example $2$: three tasks: $H$ (prio 2) - $M$ (prio 4) - $L$ (prio 8)
- $L$ holds lock $k_1$, and $M$ holds lock $k_2$
- $M$ requests lock $k_1 \rightarrow L$ priority raised to $L' =$ `max_prio`$(M;L) = 4$
- then $H$ requests lock $k_2 \rightarrow M$ priority raised to $M' =$ `max_prio`$(H;M) = 2$, ... but $M$ has also requested (still waiting on) lock $k_1$, ... so $L$ priority re-raised to $L'' =$ `max_prio` $(M';L'') = 2$

## Combining Algorithms
different types of jobs have different preferences
- interactive, CPU-bound, "batch", systems, etc.; one-size-fits-all impossible

we can combine scheduling algorithms to optimise for multiple bojectives
- have multiple queues
- use a different algorithms for each queue 
- move processes between queues

example: multi-level feedback queues (MLFQ)
- multiple queues representing different job types
- each queue is associated to a priority
	- a job in higher-priority queue can preempt any jobs in the lower-priority queue
	- jobs on same queue could use the same scheduling algorithm, typically RR

## Multi-level Queue Scheduling
goal $1$: optimise turnaround time (TT) for "batch" jobs
- shorter jobs scheduled to run first
	- not pure SJF, use time slice technique

goal $2$: minimise response time for "interactive" jobs
challenge:
- no prior knowledge of type of job, what the next burst is, etc.
- let a job define its "`nice`-ness value"
	- like an indicative (static) priority
	- actual scheduling priority (dynamically) determined by kernel schedular
		- `nice`-ness technique used for "normal" - i.e., non - "realtime" - jobs

idea:
- adapt a process's actual priority based on its history - "feedback"

method:
- rule $A$: processes start at highest-priority
- rule $B$: if job uses its entire time slice, demote its priority
	- i.e., jobs with longer required time slices progressively moved to lower-priorities

problems:
- unforgiving + starvation
- can "game" the system
	- e.g., performing I/O right before time slice ends

mitigation:
- periodically boost priority for jobs that haven't been scheduled
- account for job's total run time at its priority level (instead of looking at just current time slice)

### MLFQ in BSD
- every runnable process on one of $32$ runqueues
	- kernel runs task on highest-priority non-empty runqueue
	- round-robin (RR) among tasks on same runqueue
- priorities for tasks computed dynamically
	- tasks moved between runqueues to enact priority changes
	- adaption boudns to ensure dedication of certain ranges, e.g. bottom-half kernel (interrupts), top half-kernel tasks, then real-time user tasks, and after that time-sharing/idle user tasks
- favour interactive jobs that use less CPU

#### Process Priority Calculation in BSD
- `p_nice` - user-settable weighting factor, value range $[-20, 20]$
- `p_estcpu` - per task estimated CPU usage
- `p_usrpri` - task priority - (runqueue determined as `p_usrpri/4`)
	- `p_usrpri` $\leftarrow 50 + ($ `p_estcpu` $/ 4) + 2 \cdot$ `p_nice`
	- calculated every $4$ ticks, value bounded in $[$`PRI_AX` $= 50$, `PRI_MIN` $= 127]$
- `p_estcpu` calculation
	- incremented (decreases priority) whenever timer interrupt fins task to be in running state `p_estcpu` $\leftarrow$ `p_estcpu` $+ 1$
	- decayed (increase priority) every second that task is in runnable state
	- `p_estcpu` $\leftarrow ( 2 \cdot$ `load` $/ 2 \cdot$ `load` $+ 1) \cdot$ `p_estcpu` 
	- `load` - average of length of the runqueue and the short-term sleep-queue over last minute
- sleeping task increases in priority
- `p_estcpu` not updated while task is in waiting state
	- instead, separate `p_slptime` keeps count of sleep time
- when task becomes runnable again:
	- `p_estcpu` decayed (increases priority) once task re-enters the runnable state
	- `p_estcpu` $\leftarrow ( 2 \cdot$ `load` $/ 2 \cdot$ `load` $+ 1)$^`p_slptime` $\cdot$ `p_estcpu` 
	- approximated decay ignoring `p_nice` and the past values that `load` had while it was sleeping

## Symmetric Multi-Processing (SMP)
- shared-memory multi-processing
- small number of CPUs
- same access time to shared main memory
- multi-level dedicated cache memory
	- L1 cache: private - per CPU core
	- L2 - L3 - L3 cache: shared - between cores

### Global Queue of Processes/Threads
- one ready queue shared across all CPUs
- advantages
	- good CPU utilisation
	- fair to all processes/threads
- disadvantages
	- not scalable (contention for global queue lock)
	- poor cache locality
- Linux 2.4 used global queue of processes/threads

### Per-CPU Queue of Processes/Threads
- static partitioning of processes/threads to CPUs
- advantages
	- easy to implement
	- scalable (no contention on ready queue)
	- better CPU cache locality
- disadvantages
	- load-imbalance (some CPU's have more processes)
		- unfair to processes/threads, and lower CPU utilisation

### Hybrid Queue of Processes/Threads
- use both global and pre-CPU queues
- balance jobs across queues
- for each process/thread, introduce an associated "processor affinity"
	- allows us to add process/thread to a specific CPU's queue if recently ran on the same CPU
		- the one it has "affinity" for
	- CPU cache state may still present
- Linux 2.6 uses a similar approach

### Multiprocessor Scheduling Issues
- must decide on more than which tasks to run
	- must decide on which CPU to run which task
- moving between CPUs has costs
	- more cache misses, depending on architecture. more TLB misses too
- processor affinity-based scheduling
	- try to have task scheduled on same CPU
		- benefit from locality of the data, cache utilisation or interaction with other tasks
			- but also have take care of load balancing
			- have to perform cost-benefit analysis when deciding whether to migrate
			- affinity scheduling can become harmful, particularly when high-percentile latency is critical
- desired to have related threads/processes running at the same time
	- good if threads access same resources
	- even more important if processes need to communicate often, otherwise communication events have to leave messages and insure the penalty of context switches
- gang scheduling - schedule all CPUs synchronously
	- ensure that if two or more related threads/processes need to communicate with each other, they will all be ready to communicate at the same time
- how?
	- global context-switching across all CPUs
		- with synchronised quanta, easier to schedule related threads/processes together

## Real-Time Scheduling
- type 1: soft real-time
	- non-critical systems, "soft" guarantees
- type 2: hard real-time
	- highly critical systems, "hard" guarantees
- for a system that must handle periodic and aperiodic events
	- e.g., processes $A, B, C$ must be scheduled every $100, 200, 500$ ms, require $50, 30, 100$ ms each
- various scheduling strategies
	- e.g., earliest deadline first (EDF) - works if tasks meet the schedulability test, otherwise fails badly. rate-monotonic scheduling (RMS) - deadlines equal to periods, assign higher-priority to shorter period
	- schedulability test: for EDF: $\sum{ \frac{C_t}{T_i} } \leq 1$ (where $C_i$ is the worst-case computation time and $T_i$ is the inter-arrival periods)

## Linux $O(1)$ Schedular

### Goals
- avoid starvation
- boost interactivity
	- fast response to user despite high load
	- achieved by inferring interactive processes and dynamically promoting their priorities
- scale well with number of processes
	- $O(1)$ scheduling
- symmetric multi-processing (SMP) goals
	- scale well with number of CPUs
	- load balancing: no CPU should be idle if their is work
	- CPU affinity: no random migration of processes between CPUs

### Overview
- multilevel queue schedular
	- each queue associated with a priority
	- a process's priority may be adjusted dynamically
- two classes of processes
	- real-time-class tasks - priorities $[0, 99]$
		- always schedule highest-priority processes ($0$ highest)
		- can have FCFS (`SCHED_FIFO`) or RR (`SCHED_RR`) processes at same priority level
	- normal-class tasks - priorities $[100, 139]$
		- RR for processes with same priority (`SCHED_NORMAL`)
		- priority with aging
		- aging implemented efficiently (pointer swapping)

### Normal-class (`SCHED_NORMAL`) Tasks
- each CPU's runqueue contained two arrays of priority queues
	- active array and expired array
		- total 40 priorities $[100, 139]$ - smaller number $\equiv$ higher priority

### Scheduling Algorithm for Normal-class (`SCHED_NORMAL`) Tasks:
1. find highest-priority non-empty queue for the active array `rq->active`; if none are left in active, simulate agin by swapping expires and active arrays
	1. efficient: active and expired arrays accessed by pointer, only have to do pointer-swapping
2. next $=$ first task on that queue 
3. adjust next's priority using a heuristic
4. context switch to next
5. when next has used up its time slice, insert next to the right priority queue of the expired array `rq->expired` and call `schedule()` again

### Simulated Aging
- traditional aging algorithm
	- problem: $O(n)$ - every task is examined and "aged" by adjusting its priority on each `schedule()` call
- simulated aging (with $O(1)$ schedular algorithm):
	- swapping active with expired always gives low(er)-priority tasks a chance to run
		- advantage: $O(1)$
		- tasks are touched only when they start or stop running

### Find Highest-priority Non-empty Queue
- time complexity: $O(1)$
	- depends on the number of priority levels, not the number of tasks

### Implementation
- a bitmap for fast lookup
	- 140 queues $\rightarrow$ need five 32-bit integers to represent their state
	- few compares are required to find the first non-zero bit
	- also, there exist hardware-level instructions to find the first non-zero bit
		- `bsf` (bit scan forward - searches the source operand for the least significant bit that is set) on Intel

### Heuristic-based Priority Adjustment

#### Goal
dynamically increase priority of interactive processes
- to determine if it is interactive, use:
	- step ratio
	- mostly in sleeping state: considered as interactive or I/O-bound
	- mostly in running state: considered as non-interactive or CPU-bound

#### Implementation
- track per-process `sleep_avg`
	- before switching-out a task, subtract from `sleep_avg` how many ticks it ran
	- before switching-in a task, add to `sleep_avg` how many ticks it was blocked for, up to a maximum of `MAX_SLEEP_AVG` (10 ms)

### Calculating Time Slices
- stored in `task_struct.time_slice`
- processes start at 120 by default
- static priority: `nice`-ness value $[19, -20]$
	- inherited from the parent process
	- altered by user (negative require special permission)
- dynamic priority: based on static priority and runtime behaviour (interactive/CPU-bound)
- higher-priority processes get mapped to a larger time slice (different time slice per priority-queue)
- how priority was used to map time slice (`task_timeslice()` in `sched.c`):
	- `if (priority < 120); time_slice = (140 - priority) * 20`
	- `if (priority >= 120); time_slice = (140 - priority) * 5`
- how dynamic priority was adjusted during runtime:
	- `bonus = min(10, (sleep_avg/100));`
	- `dynamic_priority = max(100, min(static_priority - bonus + 5, 139));`

## Linux Schedular

### Real-time-class Scheduling
- the Linux kernel can be build with the `PREEMPT_RT` patch for soft real-time scheduling
	- remember: no hard real-time guarantees
- all real-time tasks have higher priority than any conventional tasks
	- Linux $O(1)$ schedular: real-time-class priorities $[0, 99]$, normal-class priorities $[100, 139]$
	- Linux completely fair scheduler (CFS)L real-time-class priorities $[1, 99]$
	- normal-class priority $0$
- process can be converted to real-time via the `sched_setscheduler()` system call or the `chrt` command

#### Real-time-class Policies
- `SCHED_FIFO`
	- static priorities
	- process is only preempted for a higher-priority process
	- no time quanta, it runs until it blocks or it yields voluntarily
	- static priority-level queues, FCFS within same priority level
- `SCHED_RR`
	- same as above, but with time quanta within the same priority level

#### Normal-class Processes
these have `SCHED_NORMAL` scheduling policy

#### Multi-processor Scheduling
- per CPU runqueues
- possible for one processor to be idle while others have jobs waiting in their runqueues
- periodically rebalance runqueues
	- migration threads move processes from one runqueue to another
- note: the kernel always locks the runqueues in the same order for deadlock prevention
	- remember: static ordering of resources

## Linux Completely Fair Schedular (CFS)
default schedular for normal-class tasks
- uses per-CPU runqueues
- CFS no longer deals with priorities 
	- `chrt -m` shows `SCHED_OTHER` has $0$ priority levels
- per-CPU runqueues nodes are time-ordered tasks that are kept sorted by [[Red-black trees]]

no longer deals with priorities
- per-CPU runqueue nodes are tasks that are kept sorted with respect to the virtual "execution time" they have received
	- nodes are indexed by `task_struct.vruntime` - i.e., virtual "execution time" in nanoseconds
		- not actual runtime (ticks), e.g., the `vruntime` value is affected by `nice` priority level using a load weighting factor
	- always kept sorted by `rbtree` operations; leftmost node always corresponds to tasks that has received the least virtual "execution time"
		- note: a less "nice" process is accounted for as having received less virtual "execution time" as compared to a default `nice-ness` with the same ticks, will therefore end up more to the leftmost part of the `rbtre`
- red-black tree operations always maintain tasks sorted
	- $O( \log{n} )$ time
- also, CFS schedular assigns a proportion of the CPU to a process (rather than a fixed-time time slice)
	- this means the actually time slice each process will get, is continuously adaptable, proportionally to the current load and weighted by the process' `nice`-ness value