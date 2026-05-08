---
tags:
  - CS446
---
## Deadlock
situation where two or more processes are never able to proceed because each is waiting on the other to compete something (that can only be completed by the latter)
- key concept: circular waiting

### Deadlock Conditions
- mutual exclusion
	- at least one resource must be held exclusively (in a non-sharable mode)
- hold and wait
	- there must be one process holding one resource and waiting for another resource
- no preemption
	- resources are non-preemptable (critical sections cannot be aborted externally)
		- vs. preemptable (can be taken away from a process without hurting its execution)
- circular wait
	- there must be exist a set of processes $[P_1, P_2, \dots, P_n]$ such that $P_1$ is waiting for $P_2$, $P_2$ for $P_3$, $\dots$, and $P_n$ for $P_1$

two approaches to dealing with a deadlock
- proactive: prevention
- reactive: detention and correction

### Deadlock Prevention by Elimination of Circular Waiting
resource allocation graph cycles and deadlock
- if graph has no cycles $\rightarrow$ no deadlock
- if graph contains a cycle
	- definite deadlock if only a single unit per resource - use waits-for-graph (WFG)
		- WFG: variant of resource allocation graph with only processes as nodes
	- otherwise, possible deadlock

prevent deadlock with static ordering of resources
- statically number resources, e.g., $R_0$ is mutex $m_0$, $R_1$ is mutex $m_1$, etc.
- require (by-application-design) process to request resources in strict numerical order
	- to have a deadlock, a process must be holding $R_j$ and requesting $R_i$, where $i < j$

note: e.g., to avoid multi-mutex deadlocks, we can make sure that there is a static global order for all mutexes, and every program always takes and releases locks in that order 

### Dealing With a Deadlock
- ignore it (until it goes away) - ostrich approach
- deadlock prevention - make it impossible for a deadlock to happen
- deadlock avoidance - control allocation of resources
	- provide information in advance about what resources will be needed by processes to guarantee that deadlock will not happen
	- system only grants resource requests if it is guaranteed that the process can obtain all resources it is going to need in every future requests
	- effectively avoids circular-waits (wait dependencies), but it is impractical (and hard) to have to determine in advance all resources that will be needed
- deadlock detection and recovery - look for a cycle in dependencies; break the cycle

### Banker's Algorithm
classic deadlock avoidance approach for resources with multiple units
1. assign a credit limit to each customer (process)
	1. for every process, we must establish its required credit limit (max number of resources expected to be requested) in advance - impractical
2. reject any request that leads to an unsafe state
	1. unsafe state: one where a sudden request by any customer up to their full max credit limit could lead to a deadlock
	2. use a recursive reduction procedure to discover unsafe states and skip them (allow $R_j$ allocation only for safe $P_i$ requests, and iterate to find sequence of only safe $P_i$ requests)
3. in practice: system must keep resource usage well below capacity to maintain a surplus
	1. should rarely have to be invoked due to low resource utilisation

### Deadlock Detection & Recovery

#### Deadlock Detection
- detection
	- traverse the resource allocation graph looking for cycles
	- if a cycle is found, preempt resource (force a process that holds it to release it)
- expensive
	- many processes and resources to traverse
		- cycle detection algorithm (e.g., [[Depth-first search]]) has to be ran and parse every node of the graph (can have multiple connected components)
- algorithm invoked depending on
	- how frequent or likely deadlock is
	- how many processes are likely to be affected when it occurs

#### Deadlock Recovery
after a deadlock has been detected, two main options:
- abort processes
	- abort all deadlocked processes
		- processes need to be started over
	- abort one process at a time until cycle is eliminated
		- system needs to rerun deadlock detection after each abort
- preempt resources (force their release)
	- need to: a) select process and resource to preempt; b) suspend selected process until resource becomes available again; c) allocate released resource to a requesting process
- other methods:
	- priority inversion; can lead to starvation
	- rollback to previous state (used in database systems)

## Race Condition
timing dependent error involving shared state
- data race: concurrent accesses to a shared variable and at least one access is a write
- atomicity bugs: code does not enforce the atomicity required for a group of memory accesses
- order bugs: code does not enforce the order required for a group of memory accesses

concurrent coding difficult because:
- too many schedules (exponential to program size), hard to reason about
- correct concurrent code does not compose $\rightarrow$ can't divide-and-conquer
	- [[Synchronisation]] crosses abstraction boundaries

### Race Detection
data race detection

will only focus on data race detection
- techniques also exit to detect atomicity and order race bugs
- approach 1:
	- happens-before
- approach 2:
	- lockset (eraser algorithm)

#### Happens-before
event $A$ happens-before event $B$ if:
- case 1: when both in the same [[Threads|Thread]]
	- $B$ follows $A$
- case 2: when $A$ in thread $1$, and $B$ in thread $2$, exists a synchronisation event $C$ such that
	- $A$ happens in thread $1$
	- $C$ is after $A$ in thread $1$ and before $B$ in thread $2$
	- $B$ happens in thread $2$
- to detect data race, have to monitor all data accesses and synch operations, watch for:
	- access of shared location $v$ happens in thread $T_1$
	- access of shared location $v$ happens in thread $T_2$
	- no synchronisation operation happens between the accesses
	- one of the accesses is a write

problems:
- expensive
	- requires per-thread:
		- list of all accesses to shared data
		- list of all synchronisation operations
	- high false-negative rate
		- happens-before looks out for data races that will take place during runtime
			- i.e., moments when different threads actually access shared data without any synchronisation operation having taken place in between
			- note: any - approach has no nuance about relationship between shared data and synch operations
		- depends on schedular-controlled interleaving of events to elicit actual data races

#### Eraser
idea: check invariants
- violations of invariants $\rightarrow$ likely data races

what is the tracked invariant?
- the very assumptions about locking and the discipline about protecting shared access
	- we assume that any accesses to shared variables are governed by locks
	- every access is protected by at least one lock
		- any unprotected access is an error according to this discipline

problem: how to find out which lock protects a shared variable dynamically (during runtime)?
- relationship between locks and shared variables is not explicitly declared
	- otherwise could e.g. just perform static code analysis

lockset algorithm: dynamically lock relationships
- idea: governing lock has to be at least one of the ones held at the time of access
1. $C(v)$: a lockset of candidate locks for protecting shared location $v$
2. initialise $C(v)$ to set of all locks
3. upon access to location $v$ by thread $T$, refine $C(v)$
	1. $C(v) = C(v) \cap$ `locks_held(`$T$`)`
4. `if` $C(v) = \emptyset$, report error

problems (too strict)
- initialisation
	- when shared data first created and initialised, no locks normally held
- read-only of shared data
	- shared data only written at initialisation and then only read-from (safe)
- read-write locks
	- remember: allow a single writer and multiple readers
	- read-write locks can be held in either write mode or read mode
		- `read_lock(r_w_m); read(v); read_unlock(r_w_m);`
		- `write_lock(r_w_m); write(v); write_unlock(r_w_m);`

problem mitigation
- initialisation
	- do not refine $C(v)$ until a different thread than creator thread accesses data
		- only one thread creates shared data, locking unnecessary at this phase
- read-shared data
	- keep refining $C(v)$ but don't report error until $v$ has its first write-to happen
		- catches case that $C(v) = \emptyset$ for shared read operations, and at some point there is a write
- reader-writer locks
	- track locks held only when performing write, separately from usual lock-tracking
		- on each `read`$(v)$ by $T$: $C(v) = C(v) \cap$ `locks_held(`$T$`);`
		- on each `write`$(v)$ by $T$: $C(v) = C(v) \cap$ `write_locks_held(`$T$`);`

implementation
- binary (runtime) tool
	- pros:
		- does not require source code
	- cons:
		- loses source code semantics
		- can track memory accesses at word-level granularity
- how to monitor memory access to implement tracking for the lockset algorithm?
	- keep a shadow word for each memory word in the program's data section and on the heap
	- each shadow word stores the index of a lockset
	- a table used to map from lockset index to a set of locks
	- assumption: not excessively many distinct locksets

overview
- successes
	- can help detect bugs in mature software
	- still suffers from limitations;
		- major: benign races ("intentional" races)
- drawbacks
	- slow: monitoring each memory access is costly
		- can incur 10-30x slowdowns
	- improvement:
		- code static analysis
		- smart instrumentation (e.g., sampling)
- lockset algorithm is influential and used by many tools
	- e.g., helgrind (a race detection tool in valgrind)

## Memory Synchronisation Ordering
1. cache (memory) coherence
	1. property concerning an individual memory location
		1. system must appear to execute all threads loads and stores to a single memory location in a total order that respects the program order of each thread
2. memory consistency
	1. property concerning order of access of all memory locations
		1. (sequential consistency model: ) system must appear to execute all threads' loads and stores to all memory locations in a total order that respects the program order of each thread

architectures offer memory ordering instructions 
- e.g., x86 architecture `sfence`, `mefence`, `lfence`
	- `sfence`: processor ensures that every store prior to `sfence` is globally visible before any store after `sfence` becomes globally visible
	- `mfence`: guarantees that every load and store instruction that precedes `mfence`in program order becomes globally visible before any load or store instruction that follows `mfence`
	- `lfence`: performs a serialising operation on all load-from-memory instructions that were issued prior to `lfence`. instruction does not execute until all prior instructions have completed locally, and no later instruction begins execution until `lfence` completes

can be emitted with known tools (extended assembly)

c offers portable atomics
- definitions contained in `<stdatomic.h>
	- atomic types: `atomic_bool`, `atomic_int`, `atomic_long`, ... even with types that an architecture is expected to atomically execute operations (e.g., `int` store), the compiler is free to perform many unexpected optimisations, e.g. combine a variable with another in the memory location, completely remove it from a loop, keep it in a CPU register, etc. atomic types is a portable way to inform the compiler how to properly treat the variable (for concurrency)
	- atomic loading/storing: `atomic_load_explicit()`/`atomic_store_explicit()`. atomically reads and returns/replaces the value of an atomic object. allows specification of `memory_order` semantics to be used (`memory_order_relaxed`, `memory_order_acquire`/`memory_order_release`, ...)
		- memory synchronisation ordering: `atomic_thread_fence(memory_order order)` impose ordering of non-atomic and relaxed atomic accesses, as instructed by the order


### Cache (Memory) Coherence
- performance requires memory caches
	- divided into chunks called cache lines
	- caches create an opportunity for different cores to disagree about memory
- a solution: bus-based approaches
	- snoopy protocols, each CPU listens to memory bus
	- use write-through (vs. write-back) and invalidate when you see a write bit
	- bus-based schemes limit scalability
- modern CPUs use networks
	- (e.g., AMD's hypertransport, Intel's QPI and UPI)
		- CPUs pass each other messages about cache lines 

- modified
	- the cache line is present in current cache, but is dirty. i.e., needs to be written-back to memory at some points in the future, before allowing more reads from memory
	- must invalidate (changes to invalid sate) all copies in other caches before entering this stat
	- the write-back changes the cache line into the shared state
- exclusive
	- the cache line is only present in current cache, and is clean (matches the main memory)
- shared
	- the cache line may be present in other caches as well, and is clean (matches the main memory)
- invalid
	- the cache line is invalid (unused)
- owned (enhances "MOESI" protocol - "owned" state used to represent data both dirty and shared)
	- this cache line is one of several copies in the system (sort of like shared state)
	- this cache cannot modify the copy, and it is dirty (like modified state) and this cache is exclusively responsible to eventually write-back to main memory 
	- has to respond to snoop requests (ensure stale memory isn't used)
	- can have both one owned and multiple shared copies of the same line
		- allows longer deferring of write-back to main memory

#### Core & Bus Actions
- actions performed by CPU core
	- read
	- write
	- evict (if modified, must write-back)
- transactions on bus
	- read: without intent to modify, data can come from memory or another cache
	- read-exclusive: with intent to modify, must invalidate all other cache copies
	- write-back: contents put on bus and memory is updated
- modern machines use cc-NUMA architectures
	- older machines had "dance hall" architectures, with every CPU "dancing" equally with memory
	- in cc-NUMA, each CPU has faster access to some "closer" memory, and slower access to farther memory
	- use a directory to keep track of who is caching what
- shared memory programming & parallel execution with arbitrarily many CPU cores lends itself to dynamic (i.e., runtime) performance optimisations

### Consistency Model
- contract whereby the system guarantees that if the rules of the model's memory semantics are followed, the memory will be consistent and the results of reading, writing, or updating memory will be predictable (repeatable)
- consistency deals with the ordering of operations to multiple memory locations with respect to all processors

#### Strict Consistency
- a write to a variable by any processor needs to be seen instantaneously by all processors
- strongest model, fully deterministic, but only theoretical (instantaneous message-passing is impossible)

#### Sequential Consistency
- if reads and writes of all processes are executed in some sequential order, and the operations of each individual processor appear in this sequence in the order specified by its program
- writes to variables by different processors have to be seen in the same order by all processors
	- a process can see the writes of all other processes, but only its own read operations
- a processor's operations have to appear to be executed instantaneously w.r.t. every other processor
	- e.g., with a globally shared bus, posting a line with information is seen by all processors instantaneously
- model has no notion of time, only order of operations

#### Relaxed Memory Consistency
- relaxation of one or more requirements of sequential memory consistency. 
	- relaxation of program order:
		- relax any or all the ordering of operation pairs, write-after-write, read-after-write, or read/write-after-read
			- i.e., can accomplish increased performance at the cost of memory inconsistency; there is a need for hardware-aware programming (software) to ensure memory consistency through proper synchronisation
	- relaxation of atomicity:
		- a process can view its own writes before any other processors
			- i.e., a processor is allowed to read the value of its own write, and prevents other processors from reading another processor's write before the write is visible to all other processors
- different processor architectures follow different models
	- intel x86 follows the total store order TSO model: "weak ordering" allows reordering of memory operations but ensures that operations to the same memory location are seen in the same order by al processors
	- ARMs have a "weaker" model: non-globally consistent; allows operations to become visible to other processors in a different order than they appear in the program