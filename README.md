# Weenix Operating System Kernel
A Unix-like operating system kernel built with thread scheduling, Virtual File System (VFS/S5FS), and Virtual Memory (VM) management (Weenix OS / USC CSCI 402)

## Overview
Weenix is a small, Unix-like operating system kernel running on x86 architecture inside QEMU. Developed as part of USC's CSCI 402 (Operating Systems), this project covers low-level kernel development across three main phases: thread/process management, file systems, and virtual memory.

> **Note on Academic Integrity:**
Due to course academic integrity policies, the source code is maintained in a private repository. Access can be provided to prospective employers and recruiters upon request.

## Contributors
Developed collaboratively by **[Malhar Patil](https://github.com/malhar-patil)** and **[Ji Hwan Moon](https://github.com/jmoon98)**

## Kernel Architecture
This was a semester long project where we worked on three different parts of kernel architecture
### 1. Processes & Threads
- Built the core execution engine to manage how programs run, switch context, and terminate safely in the system.
- Implemented locks and wait queues (mutexes and condition variables) to coordinate multi-threaded tasks, preventing race conditions and resource deadlocks.

### 2. Virtual File System
- Created a unified interface for the operating system to handle standard file operations like opening, reading, writing, and closing files or directories.
- Connected abstract file operations to physical storage, managing file pointers, directory structures, and data layout on disk.

### 3. Virtual Memory
- Designed the virtual memory system to allocate physical RAM dynamically on demand and isolate process memory spaces from one another.
- Configured user-space address maps, dynamic heap memory growth, and process execution, allowing the kernel to boot into an interactive shell and run user programs.

---
## System Validation & Test Results
To verify kernel stability and correctness across all three layers, the system was tested using built-in diagnostic drivers and exhaustive test suites.

### 1. File System Integrity (`vfstest`)
Validates the Virtual File System and underlying S5FS disk driver by stress-testing path resolution, directory creation and removal, file reads and writes, and file descriptor limits.

<img src="assets/vfstest.gif" width="800" alt="VFS TEST">

### 2. Virtual Memory & Heap Allocation (`memtest`)
Tests the Virtual Memory layer's ability to handle dynamic memory allocation, process heap expansion (`brk`/`sbrk`), memory mapping (`mmap`), and page unmapping without memory leaks.

<img src="assets/memtest.gif" width="800" alt="VFS TEST">

### 3. Memory Pressure & Frame Allocation (`eatmem`)
Pushes physical page allocation to its absolute limit to verify that the kernel's page frame allocator safely handles low-memory constraints and cleans up allocations cleanly.

<img src="assets/eatmem.gif" width="800" alt="VFS TEST">

### 4. Process Creation & Reaping (`forkbomb`)
Rapidly spawns child processes to stress-test process table bounds, page table duplication during process cloning (`fork`), and parent-child process reaping (`waitpid`).

<img src="assets/forkbomb.gif" width="800" alt="VFS TEST">

### 5. Interactive Shell Demo
Demonstrates the fully booted Weenix kernel executing standard file system utilities (`/bin/ls`, `cat`, `mkdir`, `echo`) directly within the interactive userland shell.

<video src = "https://github.com/user-attachments/assets/b0f3f9ed-d18d-4a93-b734-95d3ab56b721" autoplay loop muted playsinline controls></video>


