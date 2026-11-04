
# Xv6-KX
## An Extended Kernel Framework for Operating Systems and RISC-V Architecture

---

## Project Information

**Submitted by:**

- Abdul Wasay (BCS-F24-E07)
- Tayyab Shehzad (BCS-F24-E16)
- Mohsin Abdullah Khan (BCS-F24-E36)

**Submitted to:** Sir Raza ul Haq

**Semester:** CS 5th Semester (Self)

**Department:** Computer Science

**Subject:** Computer Architecture & Operating Systems

---

## 1. Introduction

Xv6-KX is a kernel extension project based on the xv6-RISC-V operating system. The project aims to improve the learning and functionality of the existing kernel by adding ten selected modules related to operating-system management and RISC-V architecture. These extensions provide additional system calls and test programs to demonstrate how important kernel components work.

## 2. Project Objectives

- Extend the xv6-RISC-V kernel with ten selected modules.
- Improve process monitoring, scheduling, synchronization, and inter-process communication.
- Add tools for inspecting virtual memory, traps, system resources, and processor information.
- Understand how user programs interact with kernel services through system calls.
- Test each module with a dedicated user-level test program.

## 3. Selected Modules

### Part 1: OS Modules — Multitasking

| No. | Module | Main Function | Test Program |
|:---:|---|---|---|
| 1 | Process Monitor | Provides information about running processes through `procinfo()`. | `ps` |
| 2 | System Call Tracer | Tracks selected system calls using `trace(mask)`. | `trace` |
| 3 | Priority Scheduler + Nice | Sets and reads process priorities to support scheduling experiments. | `nice`, `schedtest` |
| 4 | Semaphores | Provides wait/post operations for process synchronization. | `semtest` |
| 5 | IPC Mailbox | Allows processes to exchange messages using `msend()` and `mrecv()`. | `msgtest` |

### Part 2: Architecture Modules — RISC-V

| No. | Module | Main Function | Test Program |
|:---:|---|---|---|
| 6 | Cycle Counter | Reads processor cycle information through `getcycles()`. | `cyclesbench` |
| 7 | Page Table Dumper | Displays page-table information for virtual-memory study using `pgtbl()`. | `pgtbltest` |
| 8 | Trap Statistics | Reports selected trap and interrupt statistics using `trapstat()`. | `trapstat` |
| 9 | Sysinfo | Reports system resource information, such as available memory, using `sysinfo()`. | `sysinfotest` |
| 10 | Hart Info | Provides per-hart or CPU information through `cpuinfo()`. | `cpuinfo` |

---

## 4. Working of Selected Modules

### Module 1: Process Monitor — `procinfo()`

The user runs the `ps` test program, which calls `procinfo()`. The kernel checks its process table and returns the process information supported by the implementation, such as process IDs and process states. The test program displays this information for monitoring.

### Module 2: System Call Tracer — `trace(mask)`

A user program calls `trace(mask)` and provides a mask that identifies the system calls to monitor. When a selected system call is made, the kernel detects it and reports its information, such as the process ID, system-call name or number, and return value, according to the project design.

### Module 3: Priority Scheduler + Nice — `setpriority()`, `getpriority()`

A process uses `setpriority()` to request a priority change and `getpriority()` to read its current priority. The scheduler uses the stored priority when choosing processes to run. The `nice` and `schedtest` programs can be used to check priority values and compare scheduling behavior.

### Module 4: Semaphores — `sem_init()`, `sem_wait()`, `sem_post()`

A semaphore is initialized with a starting value. A process calls `sem_wait()` before entering a protected section; if the resource is unavailable, it waits. After using the resource, the process calls `sem_post()` to release it and allow a waiting process to continue. The `semtest` program checks synchronization between processes.

### Module 5: IPC Mailbox — `msend()`, `mrecv()`

A process uses `msend()` to place a message in a mailbox. Another process uses `mrecv()` to receive the message. The kernel manages the mailbox and coordinates sending and receiving, including waiting behavior if required by the design. The `msgtest` program checks message exchange between processes.

### Module 6: Cycle Counter — `getcycles()`

The `getcycles()` system call reads the RISC-V cycle-counter information available to the kernel and returns it to a user program. The `cyclesbench` program can take readings around a task and compare them to estimate the number of processor cycles used. Results may vary with the environment and execution conditions.

### Module 7: Page Table Dumper — `pgtbl()`

The `pgtbl()` system call asks the kernel to display or provide page-table information for a process. The kernel walks the relevant page-table entries and reports mapped virtual pages and their associated details, as supported by the implementation. The `pgtbltest` program is used to verify the output.

### Module 8: Trap Statistics — `trapstat()`

The kernel records selected trap and interrupt events while the system runs. A user program calls `trapstat()` to retrieve the collected statistics. The `trapstat` test program displays the results so that trap and interrupt activity can be examined.

### Module 9: Sysinfo — `sysinfo()`

The `sysinfo()` system call gathers system resource information from kernel-managed data, such as available memory and process-related counts if implemented. The `sysinfotest` program calls the system call and displays the returned values.

### Module 10: Hart Info — `cpuinfo()`

On RISC-V, a hart is a hardware thread that executes instructions. The `cpuinfo()` system call obtains the supported per-hart or CPU details from the kernel, such as the current hart identifier. The `cpuinfo` test program displays the returned information.

---

## 5. Implementation Approach

The project will be implemented by modifying the relevant kernel files, registering the required system calls, and adding user-level test programs to the xv6-RISC-V build.

Each module will be developed and tested separately before integration. Testing will verify that the system calls return expected results and that existing xv6 functions continue to work correctly.

## 6. Expected Outcomes

The completed project is expected to provide a working xv6-RISC-V kernel with ten additional features. It will help demonstrate process and resource management, synchronization, communication between processes, and access to RISC-V architectural information.

Test programs will provide a simple way to verify the behavior of each extension.

## 7. Conclusion

Xv6-KX is a practical kernel-extension project that combines operating-system concepts with RISC-V architecture. By implementing and testing the ten selected modules, the project will strengthen understanding of kernel design, system calls, and low-level system operation.

---

## Reference

**Base Operating System:** [MIT xv6-RISC-V](https://github.com/mit-pdos/xv6-riscv)

---

**Project:** Xv6-KX  
**Domain:** Operating Systems and Computer Architecture  
**Platform:** xv6-RISC-V
