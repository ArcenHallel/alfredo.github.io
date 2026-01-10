---
{}
---
#### Your Final Report

|   |   |
|---|---|
|Total marks|33|
|Total Questions|25|
|Questions correctly answered|16|
|Success ratio|64%|
|Marks secured|24|
|Percentage secured|72.73%|


1)  Which of the following answers refer to an office equipment that combines the functionality of multiple devices? (Select 2 answers)

-    ==MFD ( Missed)== MFD Multifunction Device
-    IoT ( Your answer) X
-    ==MFP ( Missed)== MFP Multifunction Printer
-    PED
-    ==MFA ( Your answer)

2)  A type of OS characterized by low delay between the execution of tasks required in specific applications, such as in military missile guidance systems or in automotive braking systems, is known as:

-    UNIX ( Your answer)
-    Windows NT
-    POSIX
-    ==RTOS ( Missed)==
## RTO
RTOS stands for Real-Time Operating System. It's an operating system designed to manage the resources of a computing system, such as hardware resources (CPU, memory, peripherals) and software resources (tasks, processes), with a primary focus on meeting real-time requirements.

Here are some key characteristics and features of RTOS:

1. **Deterministic Behavior**: RTOSs prioritize deterministic behavior, meaning that tasks or processes have guaranteed response times within specified deadlines. This is essential for applications where timing predictability is critical, such as industrial automation, automotive systems, medical devices, and aerospace applications.
    
2. **Task Scheduling**: RTOSs typically include scheduling algorithms optimized for real-time requirements, such as priority-based scheduling, fixed-priority scheduling, or rate-monotonic scheduling. These algorithms ensure that high-priority tasks are executed with minimal delay, meeting their deadlines.
    
3. **Interrupt Handling**: RTOSs provide efficient interrupt handling mechanisms to respond to external events or hardware interrupts promptly. Interrupt latency, the time between the occurrence of an interrupt and the execution of the corresponding interrupt service routine, is kept to a minimum to meet real-time constraints.
    
4. **Resource Management**: RTOSs manage hardware resources, such as CPU time, memory, and I/O devices, efficiently to ensure that tasks can access the resources they need without contention or deadlock. This includes mechanisms for task synchronization, mutual exclusion, and inter-process communication.
    
5. **Deterministic Timing**: RTOSs often provide mechanisms for precise timing control, such as timers, clocks, and time-sensitive APIs, to facilitate the implementation of real-time tasks and applications.
    
6. **Reliability and Fault Tolerance**: RTOSs are designed to be highly reliable and fault-tolerant, with features such as task watchdog timers, error detection and recovery mechanisms, and fault isolation capabilities to ensure system robustness and stability.
    

RTOSs are widely used in embedded systems and applications where real-time performance, reliability, and predictability are paramount. They provide a foundation for building mission-critical systems that require precise timing, responsiveness, and resilience in challenging environments. Popular examples of RTOSs include FreeRTOS, VxWorks, QNX, and RTEMS.
##

3)  An integrated circuit combining components normally found in a standard computer system is referred to as:

-    HSM
-    TPM ( Your answer) X
-    ==SoC ( Missed)== system on chip
-    BIOS

4)  A lightly protected subnet (previously known as a DMZ) consisting of publicly available servers placed on the outside of the company's firewall is called:

-    Honeynet
-    Virtual Private Network (VPN) 
-    Extranet ( Your answer) X 
-   ==Screened subnet ( Missed)

5)  Which of the following destruction tools/methods allow(s) for secure disposal of physical documents? (Select all that apply)

-    ==Shredding ( Your answer)
-    Hard drive sanitization
-    ==Burning ( Your answer)
-    Low-level formatting
-    Degaussing ( Your answer) X is not documentation

6)  Digital signatures provide: (Select 3 answers)

-    ==Integrity ( Your answer)
-    ==Authentication ( Missed)
-    Confidentiality
-    Authorization
-    ==Non-repudiation ( Your answer)
-    Accounting ( Your answer) X

***the hash: integrity 
signature: non-repudiation
key: authentication


7)  Examples of key stretching algorithms include: (Select 2 answers)

-    ROT13
-    Twofish ( Your answer) X
-    ==Bcrypt ( Missed)== Bcrypt is a password hashing algorithm that converts a user's password into a fixed-length string of characters that can be securely stored in a database.
-    DSA
-    ==PBKDF2 ( Your answer)== In cryptography, PBKDF1 and PBKDF2 are key derivation _functions with a sliding computational cost, used to reduce vulnerability to brute-force_ attacks.

 8) Pseudo-random data added to a password before hashing is called:

-    Shim
-    ==Salt ( Missed)
-    Seed
-    IV ( Your answer) not for passwords
## IV
Salting and Initialization Vectors (IVs) are both techniques used in cryptography, but they serve different purposes and are used in different contexts. Here's a breakdown of the differences between salting and IVs:

1. **Purpose**:
    
    - **Salting**: The primary purpose of salting is to defend against dictionary attacks and rainbow table attacks in password hashing. Salting involves adding a unique, random value (the salt) to each plaintext password before hashing it. This makes it computationally infeasible for attackers to precompute hashes for common passwords because they would need to generate separate rainbow tables for each salt value.
    - **Initialization Vector (IV)**: The primary purpose of an IV is to ensure that each encryption operation produces a unique ciphertext, even when encrypting the same plaintext with the same key. IVs are used in block cipher modes of operation, such as CBC (Cipher Block Chaining), to introduce randomness and prevent patterns in the plaintext from being preserved in the ciphertext.
2. **Usage**:
    
    - **Salting**: Salting is typically used in the context of password hashing algorithms, such as bcrypt, PBKDF2, or Argon2, to protect stored passwords in databases. Each password is hashed with its unique salt value, and both the salt and the hashed password are stored together.
    - **Initialization Vector (IV)**: IVs are used in symmetric encryption algorithms, such as AES (Advanced Encryption Standard), to ensure the security of encrypted data. Each encryption operation requires a unique IV, which is often generated randomly or pseudo-randomly and may be transmitted alongside the ciphertext or stored alongside it.
3. **Scope**:
    
    - ==**Salting**: Salting is specific to password hashing algorithms and is primarily concerned with protecting passwords stored in databases.==
    - ==**Initialization Vector (IV)**: IVs are specific to symmetric encryption algorithms and are used to ensure the security and uniqueness of encrypted data.==

In summary, salting and IVs are both cryptographic techniques used to enhance security, but they are applied in different contexts and serve different purposes. Salting is used in password hashing to defend against dictionary and rainbow table attacks, while IVs are used in symmetric encryption to ensure the uniqueness and security of encrypted data.