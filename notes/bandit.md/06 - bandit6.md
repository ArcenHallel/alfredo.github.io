# Bandit lvl 6 → lvl 7

Tags: 
Date:

# Goal
The password for the next level is stored somewhere on the server and has all of the following properties:

    - owned by user bandit7
    - owned by group bandit6
    - 33 bytes in size

# Approach
Going off bandit5, we use the same command `find` , but we add `user` and `group` to our command instead
	for science I want you to try `bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33` without the 2>/dev/null    :^)
## Output / Result
```bash
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password

bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password 
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj


```

# Commands user
* find 
* 2>/dev/null
* cat