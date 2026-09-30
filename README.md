# OS Kernel Extension Project

## Student Information

**Name:** Abdul Wasay

**Project:** Operating System Kernel Extension

---

## Selected Modules

The following modules have been selected for my kernel extension project.

### Part 1: OS Modules — Multitasking

| # | Module | Subsystem | Syscalls | Test Program |
|---|--------|-----------|----------|--------------|
| 1 | Process Monitor | Process Table | `procinfo()` | `ps` |
| 2 | System Call Tracer | Syscall Dispatcher | `trace(mask)` | `trace` |
| 3 | Priority Scheduler + Nice | Scheduler | `setpriority()`, `getpriority()` | `nice`, `schedtest` |
| 4 | Semaphores | Sleep/Wakeup Synchronization | `sem_init()`, `sem_wait()`, `sem_post()` | `semtest` |
| 5 | IPC Mailbox | Inter-Process Communication | `msend()`, `mrecv()` | `msgtest` |

### Part 2: Architecture Modules — RISC-V

| # | Module | Subsystem | Syscall | Test Program |
|---|--------|-----------|---------|--------------|
| 6 | Cycle Counter | CSRs (`cycle` / `time`) | `getcycles()` | `cyclesbench` |
| 7 | Page Table Dumper | Virtual Memory (Sv39) | `pgtbl()` | `pgtbltest` |
| 8 | Trap Statistics | Traps and Interrupts | `trapstat()` | `trapstat` |
| 9 | Sysinfo | Physical Memory Allocator | `sysinfo()` | `sysinfotest` |
| 10 | Hart Info | Multicore / Per-CPU State | `cpuinfo()` | `cpuinfo` |

---

## Project Scope

This project will extend an existing operating system kernel by implementing the selected OS and RISC-V architecture modules.

The implementation will include:

- OS modules supporting multitasking
- RISC-V architecture-related modules
- New system calls
- User-space test programs
- Kernel-level integration and testing
- Documentation and architectural diagrams

---

## Module Reservation

**The above modules are reserved for my project.**

Implementation and detailed documentation will be added in later stages.
