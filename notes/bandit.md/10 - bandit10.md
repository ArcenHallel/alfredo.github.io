# Bandit lvl 10 → lvl 11

Tags: 
Date:

# Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data

# Approach
since the file is in a base64 format we can decode it using `base64 -d` 

## Output / Result
```bash
bandit10@bandit:~$ cat data.txt 
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
bandit10@bandit:~$ base64 -d data.txt 
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

```

# Commands user
* cat 
* base64 
* 