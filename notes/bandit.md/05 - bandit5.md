# Bandit lvl 5 → lvl 6

Tags: 
Date:

# Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    - human-readable
    - 1033 bytes in size
    - not executable


# Approach
* Since we are looking for a file with the following parameters we can use the `find` command 


## Output / Result
```bash
bandit5@bandit:~/inhere$ find ./ -type f -size 1033c
./maybehere07/.file2

bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

* If you run find ./ -type f you will get a long list of files but since we know the size we can add that to the parameter search and it gives us the exact file we are looking for.
# Commands user
* cd 
* find 
* cat
