# Bandit lvl 3 → lvl 4

Tags: 
Date:

# Goal
 The password for the next level is stored in a hidden file in the inhere directory.

# Approach
* once i logged into the machine i `ls` to see what we have in the current dir and noticed a folder, so `cd` into fold then `ls`, nothing shows up but from our hit we know that the file is hidden in the inhere dir so, `ls` again but  `ls -la` instead to show hidden files.

## Output / Result

```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Aug 15 13:16 .
drwxr-xr-x 3 root    root    4096 Aug 15 13:16 ..
-rw-r----- 1 bandit4 bandit3   33 Aug 15 13:16 ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ...Hiding-From-You 
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```
# Commands user
*  ls
* cd
* ls -la 
* cat