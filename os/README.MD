# OS Design

## Table of Contents

- 1. System Requirements.
  - 1.1. Functional.
  - 1.2. Non Functional.
- 2. Approaches with tradeoffs.
- 3. Virtualization.
  - 3.1. CPU virtualization.
  - 3.2. Memory virtualization.
- 4. Concurrency.
  - 4.1. Basic synchronization mechanisms.
  - 4.2. Typical problems.
- 5. Durable storage.
  - 5.1. File systems.
  - 5.2. RAID.
  - 5.3. How HDD works?
  - 5.4. How SSD works?

## 1. System Requirements

Here is some overview. Lets say that no OS exist on Earth.
And you, as time traveler, know all the benefits an OS can give. What are they?
Knowing them, please, convince everybody that creating OS is necessary.

We can talk about several system types:

- Real-time.
- Embedded.
- General purpose.

For now let's concentrate on creating general purpose system.

### 1.1. Functional

- Computer should run several processes.
  - To be able to create software for different levels.
    (i.o user can use browser, but browser don't have to know about drivers and stuff).
  - To be able to utilize resources more efficiently.
  - To be able to be used simultaneously by several users.
- Each process should be treated equally.
  - Similar policies should be applied to each process.
  - Equal processor's time.
  - Equal memory allocation management.
- Overall system should have good balance between being interactive and efficient.
- System should be able to store data somehow.
  - Let's say we have both HDDs and SSDs available.
- System should be able to work with different kind of devices attached.
- Several users should be able to work with system via commandline interface.

### 1.2. Non Functional

- Security
  - Processes should not affect each other in any way.
    - Can't read/write other memory.
    - Can't steal processor's time.
    - Can't abuse system workflow any other way.
  - Users should not access each other's files.
- Performance
  - Resources utilization should be maximized.
  - System should be highly interactive.
- Reliability
  - Saved files should not be lost.
  - System must be transparent of what it does.

## 2. Approaches with tradeoffs.

What approaches do we have? Why modern operational systems use virtualization?

- 1. Bare metal programming
  - **Description**: aa
  - **Examples**: aa
  - **Limitations**: aa
- 2. Single-program operating environments
- 3. Cooperative multitasking with direct memory access
  - **Description**: Program volanteers to give control over resources to other programs.
  - **Examples**: Early Mac Os, Windows 3.x.
  - **Limitations**: Security considerations. Program can capture resources and never give them back.

## 3. Virtualization
