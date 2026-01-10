# Bandit lvl 14 → lvl 15

Tags: 
Date:

# Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
# Approach

this one i had a hard time trying to explain how you should know what to do next.....
best to say read about ports and understand how the operate and mess around with telnet or netcat these are one of the most used tools when it comes to ports and networking
## Output / Result

```bash
bandit14@bandit:~$ telnet localhost 30000
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

Connection closed by foreign host.
```
# Commands user
* 