# Weenix Operating System Kernel
A Unix-like operating system kernel built with thread scheduling, Virtual File System (VFS/S5FS), and Virtual Memory (VM) management (Weenix OS / USC CSCI 402)

## Overview
Weenix is a small, Unix-like operating system kernel running on x86 architecture inside QEMU. Developed as part of USC's CSCI 402 (Operating Systems), this project covers low-level kernel development across three main phases: thread/process management, file systems, and virtual memory.

> **Note on Academic Integrity:**
Due to course academic integrity policies, the source code is maintained in a private repository. Access can be provided to prospective employers and recruiters upon request.

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

![VFS TEST]('')
