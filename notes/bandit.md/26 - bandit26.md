# Bandit lvl 26 → lvl 27

Tags: 
Date:

# Goal
Good job getting a shell! Now hurry and grab the password for bandit27!

# Approach
there is a file `bandit27-do` that looks to be our only hint



## Output / Result
```bash
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ file bandit27-do 
bandit27-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=35d353cf6d732f515a73f50ed205265fe1e68f90, for GNU/Linux 3.2.0, not stripped
bandit26@bandit:~$ 
bandit26@bandit:~$ 


```

```bash
bandit26@bandit:~$ ./bandit27-do 
Run a command as another user.
  Example: ./bandit27-do id
bandit26@bandit:~$ 
```

to run this .exe its asking to run as another user lets run lets find out who can run this file 

```bash
bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
```

bandit27 has permissions to besides bandit26(us) but we cant run so we dont have the proper permissions to use it

what we can do is manipulate the system in thinking we are bandit27 with 

```bash
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
bandit26@bandit:~$ 
```
# Commands user
* ls
* file
* id
* cat