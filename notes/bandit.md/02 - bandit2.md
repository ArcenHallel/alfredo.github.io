# Bandit lvl 2 → lvl 3

Tags: 
Date:

# Goal
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory

# Approach
* This is the same approach as lvl 1, we cant just cat the file so we use cat ./ *filename*
* ls - la gives us the name of every file (even hidden ones), i used it here just to make sure i wasn't missing anything.
## Output / Result
```bash
bandit2@bandit:~$ ls
--spaces in this filename--
bandit2@bandit:~$ ls -la
total 24
drwxr-xr-x   2 root    root    4096 Aug 15 13:16 .
drwxr-xr-x 150 root    root    4096 Aug 15 13:18 ..
-rw-r--r--   1 root    root     220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root    root    3851 Aug 15 13:09 .bashrc
-rw-r--r--   1 root    root     807 Mar 31  2024 .profile
-rw-r-----   1 bandit3 bandit2   33 Aug 15 13:16 --spaces in this filename--
bandit2@bandit:~$ cat ./--spaces\ in\ this\ filename-- 
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

# Commands user
*  cat ./
* ls 
* ls - la 