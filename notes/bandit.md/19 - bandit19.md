# Bandit Level 19 → 20

Tags: 
Date: 

## Goal
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Approach

we see a executable file named `bandit20-do` and the owner is bandit20 but we have some permissions on the file.

## Output / Result
```bash
bandit19@bandit:~$ ls -l
total 16
-rwsr-x--- 1 bandit20 bandit19 14884 Aug 15 13:16 bandit20-do
bandit19@bandit:~$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
```

the setuid is under bandit20 user so if we run 
```bash
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20 
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

the program executes as bandit20 since it sent back the password for bandit20 user
## Commands
* ls -l 
* cat
