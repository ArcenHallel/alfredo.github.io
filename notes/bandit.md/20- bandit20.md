# Bandit Level 20 → 21

Tags: 
Date: 
## Goal
There is a setuid binary in the homedirectory that does the following: it makes a ==connection to localhost on the port== you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think
## Approach
the program says it connects to a given port and will give us the password for bandit21 if we turn in bandit20, so lets use port 7777 as our port right.
we need to connect to another user so lets open another ssh connection with bandit 20
## Output / Result
first bandit20 user - listener 
```bash
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ ./suconnect 
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.

bandit20@bandit:~$ echo '0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO' | nc -lnvp 7777
Listening on 0.0.0.0 7777
Connection received on 127.0.0.1 45458
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

bandit20 - connecting 
```bash
bandit20@bandit:~$ ./suconnect 7777
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
```

using netcat listener on the same port we were able to send the password
## Commands
* ls 
* nc

for the netcat command the 'lnvp' 
* l = listen
* n = no dns lookup
* v = verbose mode
* p = local port