## Main Idea
learning about windows processes and how to monitor them so we can see what to exploit and potentially perform privilage escalation.

creating a service for us to exploit, and creating process monitor. 
going over windows access tokens


| Privilege name    | Access that is gratned                                                                                                                                 |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| seBackupPrivilege | this enables the user process to back up files and directories, and grants READ access to files no matter what their access control list (ACL) defines |
| seDebugPrivilege  | This enables the user process to debug other processes. it also includes obtaining process handles to inject DLLs or code into running processes.      |
| seLoadDriver      | This enables a user process to load or unload drivers.                                                                                                 |

## Key Tools
- WMI (windows management instrumetation)
- pywin32 ( this is deprecated)
- netcat.py ( we made our own netcat in chapter 2)

## Important Concepts
- code injection
- netcat.py 
- 

## Useful Code Pattern
(directory monitor snippet)

## My Notes
- we make a service and plant a listener, after performing our privilage escalation we can connect to our listener and check $whoami, if our attack worked then we will be into that service with whatever permissions that service has.
- Could expand this into a real file integrity monitor