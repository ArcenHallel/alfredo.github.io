# Bandit lvl 4 → lvl 5

Tags: 
Date:

# Goal
 The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

# Approach
* I couldn't post the non-human readable format in so ill add a picture to show what it looks like but all i did is cat every file individually till i got the password i was looking for (which was not in non-human readable format)

## Output / Result
```bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file02  -file04  -file06  -file08
-file01  -file03  -file05  -file07  -file09
bandit4@bandit:~/inhere$ cat ./-file00
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

![[Pasted image 20250916192028.png]]
# Commands user
* ls 
* cd 
* cat ./