---
title: The concept of the process and its types
summary: You will be very inerested. Project about processes in two parts.  
tags:
  - Deep Learning
date: '2023-05-12T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

links:
  - icon: twitter
    icon_pack: fab
    name: Follow
    url: https://twitter.com/georgecushen
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---

# Part 1. What is a process?

1.1 Concept of process

    - This program is in the running state;

    - Some object that runs on the processor.

     At its core, all software that runs under the operating system on our computer, even sometimes including the OS itself, is organized as a set of processes.

     Processes are a minimal primitive that allows you to organize some multitasking.

     As an executable object, a process allows the parallel execution of multiple programs on the system (the CPU switches between programs)

     All software running on a computer, including the OS itself, is organized as a set of processes.

     1.2 Composition of the process.

     Let's see what the process consists of. The process consists of three main components (Fig. 1):

     1. Executable code;
     2. Data associated with it, necessary to perform this

     programs;

     3. Context - information for the OS, necessary to control the process.

     This information is used to switch between processes, to save and restore the process state:
     — Process number;
     - CPU registers;

     — The contents of the stack.
     Thus, the context is the basis for switching processes.

     The OS maintains a list of all processes in the system. It can be more complex, or it can be the simplest.

Bottom 0 address, top maximum. At the maximum is the stack, then the heap, which grow in opposite directions, the data and the program code.

It is important to understand that each process has its own address space.

In the diagram, the virtual address space starts from zero and ends with a certain maximum, which consists of segments: code, data, and stack.

When you start a program (for example, MS Word) in the OS, the following happens: - A place in memory is allocated.

Each process runs in its own virtual address space, which consists of:

- Stack segment - used for function calls and system calls;

- Data segment - static and dynamic variables allocated from the heap (everything you need to work);

- Code segment - program code, usually given read-only access.

Running the same program multiple times spawns new processes, each with its own virtual address space and environment. Those. this scheme will be for each running process.

***1.3 Types of processes***

There are two types of processes:
1) System processes;
2) User processes.
System processes can spawn other processes.

The user process cannot spawn another process, it accesses the OS through a system service request, which performs this function.

Context and process handle.

During the existence of the process, its execution can be repeatedly interrupted and continued. In order to resume the execution of a process, it is necessary to restore the state of its operating environment at the moment of interruption. The state of the operating environment is determined by the state of the registers, the operating mode of the processor, pointers to open files, information about incomplete I/O operations, error codes for system calls. This information is called process context.

***1.4 Process Control Block (PCB) This block is of constant size for all processes in the OS.***

Contains all the information necessary to perform any action on the process - suspending, then restoring the process, uploading to disk, and loading from disk.

Process IDs

- Process number (the so-called PID - Process IDentificator)

- User information

- Process state - registers, stack pointers. Process state:

  Information for the scheduler - the priority that this process has;

- Privileges - access to memory, valid instructions; 5

- Information about the virtual memory assigned to the process;

- Statistical information and restrictions (time limits

     execution, statistics on elapsed CPU time);

- I/O - resource ownership, open files, dedicated devices.

# Chapter 2 Process States

     ***2.1 Dispatch***

     Dispatcher - Sends processes to run, allocates CPU time, and switches CPU from one process to another.

     At any moment in time, any process can be in any state: at least it is waiting for I / O, executing, ready to execute, and you can also come up with a number of additional intermediate states.

     Consider two models of process states.
     2.2 The first process state model

     The ultimate goal of any operating system is to perform some work, a task, to respond to a user request...

     There are three main states of the process (Fig. 2):

     1. Execution (executed on the CPU);
     2. Readiness (temporarily stopped);
     3. Locks (waiting for an external event);

