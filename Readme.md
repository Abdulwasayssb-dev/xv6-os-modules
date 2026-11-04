
# Xv6-KX

## An Extended Kernel Framework for Operating Systems and RISC-V Architecture

### Introduction

Xv6-KX is a kernel extension project based on the xv6-RISC-V operating system. It aims to extend the existing kernel with ten modules covering operating-system management and RISC-V architecture.

### Objectives

- Extend xv6-RISC-V with ten selected kernel modules.
- Study process management, scheduling, synchronization, and inter-process communication.
- Explore virtual memory, traps, system resources, and RISC-V hardware information.
- Test each module using a dedicated user-level test program.

### Part 1: OS Modules — Multitasking

| No. | Module | System Calls | Test Program |
|---|---|---|---|
| 1 | Process Monitor | `procinfo()` | `ps` |
| 2 | System Call Tracer | `trace(mask)` | `trace` |
| 3 | Priority Scheduler + Nice | `setpriority()`, `getpriority()` | `nice`, `schedtest` |
| 4 | Semaphores | `sem_init()`, `sem_wait()`, `sem_post()` | `semtest` |
| 5 | IPC Mailbox | `msend()`, `mrecv()` | `msgtest` |

### Part 2: Architecture Modules — RISC-V

| No. | Module | System Call | Test Program |
|---|---|---|---|
| 6 | Cycle Counter | `getcycles()` | `cyclesbench` |
| 7 | Page Table Dumper | `pgtbl()` | `pgtbltest` |
| 8 | Trap Statistics | `trapstat()` | `trapstat` |
| 9 | Sysinfo | `sysinfo()` | `sysinfotest` |
| 10 | Hart Info | `cpuinfo()` | `cpuinfo` |

### Implementation Approach

1. Study the relevant xv6-RISC-V kernel files.
2. Implement each module in the appropriate subsystem.
3. Register the required system calls.
4. Add user-level test programs.
5. Build and test each module individually.
6. Integrate the modules and test the complete kernel.

### Expected Outcomes

The project is intended to demonstrate ten kernel extensions covering multitasking, process communication, synchronization, virtual memory, system monitoring, and RISC-V architecture.

### Reference

Base project: https://github.com/mit-pdos/xv6-riscv

### Project Status

Implementation and testing status will be updated as each module is completed.
