---
tags:
  - CS446
---
- early computers
	- programs use physical memory addresses directly
	- [[Operating systems|Operating system]] loads job, runs it, unloads it
- multiprogramming paradigm changed everything
	- want to have multiple processes in memory simultaneously
- consider multiprogramming directly on physical memory
	- what happens if OS needs to expand?
	- what if `vim` needs more memory than is on the machine?
	- what if OS tries to erroneously write to memory address `0x7100`?
	- what does `gcc` have to know it will run at `0x4000`
	- what if `vim` isn't using most of its memory

## Issues of Sharing Physical Memory
- protection
	- a bug in one process can corrupt memory in another
	- must somehow prevent process $A$ from clobbering process $B$'s memory
	- also prevent process $A$ from even being able to observe process $B$'s memory
- abstraction
	- a process shouldn't require specific physical memory locations
	- processes often require large amounts of contiguous memory (program [[Stacks|Stack]], large [[Data structures|]], etc.)
- resource exhaustion
	- developer typically assumes machine has "enough" memory
	- sum of sizes of all processes often greater than physical memory

## Virtual Memory Goals
- give each program its own virtual address space
	- at runtime, memory management unit translates each `load`/`store`
	- application doesn't see physical memory address
- enforce protection
	- prevent one process from messing with another's memory
- allow programs to "see" more memory than exists
	- ability to "swap-out" some memory sections to disk

## Virtual Memory Advantages
can re-locate program while running
- run partially in memory, partially "evict"/"swap-out" to disk

most of a process's memory may be idle
- can write idle parts to disk until they become needed
- let other processes use memory of idle part
	- like CPU virtualisation: when a process is not using CPU, switch-over to executing a different process. when a memory region is unused, "switch" it over to a different process

challenge
- virtual memory introduces an additional layer to memory accessing
	- can impact performance

## Load-Time Dynamic Linking
- compiler makes distinguishable in the symbol table:
	- global definitions which are routines/variables exported by the file being compiled
	- external refs corresponding to external routines/variables
- linker has to "patch" at loading-time the addresses of symbols
	- first determine where process will reside in memory
		- e.g., techniques like address space layout randomisation guards against buffer overflow attacks
	- then adjust all references within program
- problems?
	- "patching" is required for each run, and is time-consuming
	- how to move an entire process that is already in memory?
	- what if not contiguous free region can fit the program?

## Base & Bound Registers
two special privileged registers
- base and bound
- on each `load`/`store`/`jump`:
	- physical address equals base plus virtual address
	- also check: $(0 \leq \text{ VA } < \text{ Bound } )$
- so move process into memory:
	- properly adjust base register
- what happens on context switch?
	- OS has to reload the CPU's base and bound registers

## Virtual Address Space
- programs `load`/`store`/`jump` to virtual addresses
- actual memory uses physical addresses
- the virtual-to-physical-managing hardware is the memory management unit (MMU)
	- usually part of CPU
		- can be configured through privileged instructions
	- translates from virtual-to-physical addresses
	- gives a per-process view of the memory, called the "virtual address space"

## Virtual Address Space Through Base & bound Registers: Trade-offs
advantages
- cheap in terms of hardware (two registers)
- cheap in terms of CPU cycles
	- perform adding logical address and base (to determine virtual-to-physical mapping), and compare (to ensure bound within limits) in parallel inside the MMU

disadvantages
- if we rely on using just this extra layer:
	- growing a process's virtual address space is expensive or impossible
	- no systematic way to share code or data among different processes

## Segmentation
- let processes have multiple base and bound registers
	- virtual address space built from many segments
	- can share/protect memory at segment-level granularity
- how?
	- each virtual address has to somehow indicate the specific segment that it corresponds to
		- has to contain this as part of its information

segmentation mechanics
- each process has its own associated "segment table", set up by the operating system
- each virtual address indicates a segment and offset
	- top buts of virtual address select segment, low bits select offset

## Segmentation Trade-offs
advantages
- multiple segments per process
- can facilitate shared memory
- don't need entire process to reside in memory at all times
- variable segment boundaries

disadvantages
- requires MMU translation hardware, which can impact performance 
- segments can overlap
- segment mechanics not completely transparent to program
	- e.g., default segment faster or uses shorter instructions. overriding use of the default segment possible with special instructions override bytes

## Fragmentation
fragmentation is the inability to use free memory
- over time, have to suffer from either of:
	- external fragmentation: variable-sized pieces $\equiv$ many small holes
	- internal fragmentation: fixed-sized pieces $\equiv$ no external holes, but forced internal wasting

## Paging for Virtual Memory Management
- divide memory up into fixed-size pages
	- eliminates external fragmentation
- mappings of virtual pages to physical pages
	- a higher level of virtual memory mapping
	- each process has a separate such mapping
- allow OS to gain control on certain operations
	- read-only pages trigger trap to OS on-write
	- invalid pages trigger trap to OS on-read or on-write
	- OS can change mapping and resume application

## Paging Trade-offs
- eliminates external fragmentation
- simplifies allocation, freeing, and memory backing with storage
- average internal fragmentation of $0.5$ per segment
- allocate any physical page to any process
- can store idle virtual pages on disk ("swapping-out")

## Paging Data Structures
- pages are fixed size
	- virtual address has two parts: virtual page number (VPN) and offset
	- least significant 12 bits of address are page offset
	- most significant bits are virtual page number (VPN)
- page tables
	- for each process the OS maintains a page table
	- maps virtual page number (VPN) to physical page number (PPN)
		- PPN also called page frame number
	- VPN is the index into the page table contains its PPN correspondence (if valid) 
	- page table contains one page table entry (PTE) per each page of the address space
	- page table entry also includes buts for protection validity etc. 

## Page Table Entries
- page table entries control mapping
	- the physical page number determines the physical page
	- the valid bit indicates whether the page exists in memory
		- checked each time the virtual address tries to use this PTE
		- page fault when absent
	- the protection bits say what operations are allowed on this page
		- read, write, execute
		- protection fault on disallowed operation
	- the reference bit says whether the page has been accessed
		- it is set when a read or write to the page occurs
	- the modified bit says whether the page has been written to 
		- it is set when a write to the page occurs
	- the caching bit enables/disables caching of the page
		- related to translation lookaside buffer 

## Paging Advantages
- easy to allocate memory
	- memory comes from a "freelist" of fixed-size chunks
	- allocating a page is just removing it from the "freelist"
	- external fragmentation is not a problem
- easy to "swap-out" chunks of a proram
	- all chunks are the same size
	- use valid bit to detect references to "swapped-out" pages
	- pages are a convenient multiple of the disk block size 

## Paging Limitations
- does not alleviate internal fragmentation
	- process may not use memory in whole multiples of a page
- memory referencing overhead
	- at least two references per address lookup. page table first, then memory lookup
	- solution: use a hardware cache of lookups - the TLB
- actual memory required to hold contents of a page table can be significant
	- need one PTE per page

## Managing Page Tables
- why use 4 KB pages?
	- empirical choice, but not smaller because:
		- more page tables needed,
		- likely more page faults
	- also, larger page tables incur increased internal fragmentation
- size of the page table for a 32-bit addess space w/ 4 KiB pages
	- too much overhead to incur for every single process spawned
- observation: we really only need to map the address space portion actually being used
- how to map only what is actually being sued?
	- could dynamically extend page table...
		- does not work if address space is sparse
	- use one more level of indirection: two-level page tables

## Two-level Page Tables
virtual addresses have three parts:
- page directory number
	- one page directory per-process, that maps virtual addresses to one of the secondary page tables
- secondary page number
	- multiple page tables per-process, each mapping secondary page numbers to physical pages 
- offset
	- location into the physical page where the specified address is located

evolution
- two-level page tables aim to reduce the overhead of storing page tables, but with just adding 1 more level
	- each page table previously cost 4 MiB to store
- now, with 1024 secondary page tables
	- each secondary page $2^{10}$ PTEs, thus has a size of 4 KiB
	- size of all secondary page tables is 4 MiB
- but we only need to allocate secondary page tables which correspond to master page table

how to access secondary page tables?
- page directory must hold physical address of page tables, not virtual addrsses
	- but to read/write to memory, we need to use virtual addresses
- solution 1) have 1 page table that is used to point back to page directory
	- now to the MMU, all page tables appear as if they were pages, and we can access all their page table entries as if we were accessing just normal integers
- solution 2) keep 2 arrays for every page directroy
	- one contains physical addresses of its page tables, the other contains virtual addresses of its page tables, so we can access their contents

## x86 Paging
- paging enabled by a paging bit in a control register 
	- only privileged OS code can manipulate control registers
- normally 4 KiB pages (architecture may support other sizes)
- page directory: 1024 page directory entries
	- each contains physical address of a page table
- page table: 1024 page table entries
	- each page table entry contains physical address of a virtual 4 KiB page
	- each page table covers 4 MiB of virtual memory

## x86 Paging and Segmentation
- ia-32 architecture supports combined paging and segmentation
	- a virtual address space consists of multiple segments, and each segment is formed by multiple pages
	- 1) segment bus + pointer avl = linear address
	- 2) linear addresses translated to physical address via usual page translation
- two levels of protection and translation checking
	- segmentation model: architecture supports four privilege levels
	- paging model: architecture supports only two, so 0-2 = kernel-level, 3 = user-level
- why do we ant both paging and segmentation?
	- short answer: we don't - just adds overhead
	- long answer: has some fringe/incidental uses
		- already mentioned in previous slide, can be used as follows:
			- 1) segments for logically related units
			- 2) pages to partition segments into fixed-size hunks
				- tends to be complex
		- VMware runs Guest OS in privilege level CPL 1 to trap stack faults

## Where Does the OS Live?
- in its own separate virtual address space 
	- can't do this on most hardware
	- also would make it harder to parse any syscall arguments passed as pointers
- common approach: "sharing" the same virtual address space as the process
	- i.e., there exist some "shared" page table mappings
		- remember: each process has its own separate page table mappings
	- can use protection bits to prohibit user code from accessing memory belonging to the kernel-owned part of the common virtual address space
- typically all kernel text, most data are at same virtual address for every address space
- i.e., for every per-process page table mapping
	- on x86, must manually set up page tables for this usually just map kernel into contiguous virtual memory at the phase when bootloader puts kernel into contiguous physical memory
	- in some cases hardware can also place physical memory somewhere in virtual address space
- the kernel virtual memory mappings are the same across all processes
	- implications:
		- when we context switch to another process, although it involves changing the page tables, the kernel virtual memory addresses are still valid after the context switch
		- all objects created in kernel functions are accessible across all processes
		- memory for user processes will be `free()`d when it exits, but memory objects allocated within the kernel code using `malloc()` should be explicitly `free()`d

## Addressing Page Tables
where do we store the secondary page tables which access address space
- possibility 1): reserve physical memory
	- consistent to address, no translation required
	- but, allocated secondary page tables consume memory for lifetime of each virtual address spac
- possibility 2): general virtual memory
	- "cold" pages can be "swapped-out" to disk as we've seen so far
	- so entire secondary page tables can also be "swapped-out"
		- but! have to keep page directories from being "swapping-out"
			- called "wiring"
				- avoid circular page faults

if we're "swapping-out" secondary page tables, could as well "swap-out" entire OS address space
- possible, but some special code and data need to remain "wired"

kernel address space is also mapped
- first, identify mappings
	- i.e., virtual addresses and physical addresses are the same
	- generally up to 4 MiB
- after identity mapping the kernel is mapped to some other virtual addresses
	- e.g., Linux, Windows

a process's PCB contains the physical address of its page directory

## Efficient Translations
our original page table approach already carries 2x the cost of memory access
- one indirection into the page table, another indirection to the actual physical address

now two-level page tables 3x the cost
- two indirections into the page directory and the secondary page table, one more to the actual physical address
- worse, 64-bit architectures support 4-level page tables
- and this assumes that the target page table is already in memory

how can we use paging but also reduce lookup cost?
- cache translations in hardware

the translation lookaside buffer
- TLB managed by MMU

## Translation Loookaside Buffer
- translates a virtual page number into a page table entry
	- not to physical addresses, this is done by the MMU
	- translation can be done in a single machine cycle
- TLBs implemented in hardware
	- typically 4-way to fully-associative memory 
	- cache keys/tags are virtual page numbers
	- cache values are page table entries
	- with PTE + offset, the MMU can directly calculate physical address
- intuition: TLBs exploit locality
	- processes only use a handful of pages at a time
	- 32 - 128 page table entries out of all the process's pages
	- only need page table entries for those pages to be present and "mapped" in the TLB cache
	- hit rates are very important

## TLB Management
- address translations for most instructions are handled using the TLB
	- >99% of translations, but misses do happen
- who loads translations into the TLB?
	- hardware-managed MMU
		- knows where page tables are in main memory
		- OS responsible for maintaining page tables, and hardware accesses them directly
		- page tables have to be in hardware-defined format
			- inflexible
- software-managed TLB OS
- TLB faults to the OS, OS finds appropriate page table entry, loads it into the TLB
- must be fast
- CPU ISA offers instructions for manipulating TLB
- page tables can be in format convenient for OS
	- flexible
- OS responsible to ensure that TLB and page tables are consistent
	- e.g., when it changes the protection bits of a PTE, it needs to invalidate the PTE if it is in the TLB
- on process context switch the TLB needs to be reloaded
	- invalidate TLB entries of a VPN
	- but we might want to flush the TLB entries of a VPN for specific PCIDs
- when the TLB misses and a new page table entry has to be loaded:
	- a cached page table entry must be evicted
	- choosing which page table entry to evict is called the TLB replacement policy
	- implemented in hardware, often simple algorithmically
		- e.g., least-recently-used

## Swapped Virtual Memory
- pages can be moved between memory and disk
	- use disk to simulate larger virtual memory than physically available 
	- this process is called "swapping-in"/"swapping-out"
- gradually swapping a process over time
	- initially, pages are allocated from memory
	- when memory fills up, allocating a page requires some other page to be evicted
	- evicted pages go to disk
	- done by the OS, and invisible to the application
- extreme design case: demand paging
	- swapping-in a page from disk into memory only if an access attempt is made
	- main memory essentially acts as a cache fro the disk

## Page Faults
what happens when a process accesses a page that has been evicted?
1. when the OS evicts a page, it sets the PTE as invalid and modifies the location of the page to point to the swap file
2. when a process accesses that page, the invalid PTE access causes a trap
	1. page fault
3. the trap is handled by the OS page fault handler
4. handler uses the invalid PTE to locate missing page in swap file
5. reads page into a physical memory frame, updates PTE to point to that and as valid
6. restart process's instruction that caused the fault
7. but where does it put it? have to evict something else...
	1. OS usually keeps a pool of free pages around so that allocations do not immediately cause evictions

## All Together
a simple situation: process is executing on the CPU, and it issues a read to an address

the read goes the TLB in the MMU
1. TLB performs a lookup using the virtual page number of the address
2. common case is that the virtual page number finds a TLB match, and returns a page table entry for the mapping for this address
3. TLB validates that protection its of page table netry allow reads
	1. if it would fail, protection fault
4. page table entry specifies which physical frame holds the page
5. MMU combines the physical frame + offset into a physical address
6. MMU then reads from that physical address, returns value to CPU

## TLB Misses and Protection Faults
two other things can also happen:
- TLB miss:
	- TLB does not contain a cached page table entry mapping this virtual address
- protection fault:
	- PTE in TLB, but memory access violates PTE protection bits

reloading the TLB
- if the TLB does not contain the Mapping, two possibilities:
- 1) MMU hardware loads page table entry from page table in memory
	- hardware-managed TLB, OS not involved in this step
	- OS has already set up the page tables, so that the hardware can access it directly
- 2) trap to the OS - software-managed TLB
	- OS intervenes and performs lookup in page table, loads the page table entry into TLB
	- OS returns from fault handler, TLB continues
	- an architect will only support one method or the other
- a page table lookup can cause a recursive fault if page table has been "swapped-out"
	- assuming page tables themselves are in OS part that is mapped to virtual address space
- when TLB has page table entry it restarts translation
	- common case: page table entry refers to a valid page in memory
	- uncommon case: TLB faults again on page table entry because of its protection bits

protection faults
- page table entry can indicate a protection faults
	- read/write/execute bits - operation not permitted on page
	- invalid bit - page is not allocated, or page is not present in physical memory
- TLB traps to the OS
	- R/W/R - protection fault: OS usually will forward the fault back up to process
	- invalid - page fault:
		- virtual page not allocated at all in address space of process
			- OS forwards the fault back up to process (e.g., segmentation fault)
		- page not currently present in physical memory 
			- OS allocates physical frame, reads form disk, maps page table entry to allocated physical frame

## Advanced Functionalities Through Virtual Memory "Tricks" 
- copy-on-write
- memory-mapped files
- shared memory

## Copy-on-write
- OSs spend al of of time copying data
	- system call arguments between user and kernel space (for security and reliability)
	- entire address spaces to implement `fork()`
- copy-on-writeL defer copies as long as possible (avoid altogether if possible)
	- instead of copying pages, create shared mappings of parent pages in child's virtual address space
	- shared pages are protected as read-only in parent and hcild
	- reads happen as usual, but a write generates a protection fault $\rightarrow$ trap to OS $\rightarrow$ copy to page $\rightarrow$ change page mapping in child's page table $\rightarrow$ restart write instruction
- what the `fork()` c-library function actually does...

## Memory-mapped Files
- memory-mapped files enable processes to do file I/O using loads and stores
	- instead of performing system calls
- bind a file to a virtual memory region
	- page table entries map virtual addresses to physical frames holding file's data
- initially, all pages mapped to a file are invalid
	- OS reads a page form the file when invalid page is accessed
	- OS only writes a page to the file when it is evicted, or region unmapped
		- if page is not modified/dirty, no write to file is needed at all
			- this is another use of the first bit in page table entries
- file essentially also acts as backing store for that region of the virtual address space
	- virtual address space not backed by "real" files also called anonymous virtual memory

advantages
- uniform access for files and memory
- less copying
	- similar motivation as with copy-on-write

drawbacks
- process has less control over data movement
	- OS handles faults in a way that is invisible to process
- does not generalise to streamed I/O

importantly
- facilitate shared memory and inter-process communication 
	- several processes can memory-map the same file
		- allows pages in memory to be shared
	- memory persistence
		- enables processes to share memory sections that persist independently of the lifetime of a certain process

## Shared Memory
- private virtual address spaces protect applications form each other
	- usually exactly what we want to accomplish
- but data sharing might also be desired
	- parents and children processes in a `fork()`ing web server or poxy will want to share the same in-memory cache
- we can use shared memory to allow processes to share data using direct memory references
	- both processes will be able to see updates to the shared memory segment
	- process B can immediately read an update by process A
	- remember: requires synchronisation through shared objets performing some synchronisation mechanism
- implement sharing using page tables:
	- have page table entries in both page tables map to the same physical frame
	- each page table entry can have different values for its protection its
	- must take care to update both page table entries when page becomes invalid
- can map shared memory at same or different virtual addresses in each process's address space
	- different: flexible but the values of pointers inside the shared memory segment are invalid
	- same: non-portable, but values of pointers inside shared memory are valid
- also caution: pointer in shared memory segment referencing address outside the shared memory segment.