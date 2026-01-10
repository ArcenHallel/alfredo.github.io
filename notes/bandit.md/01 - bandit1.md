# Bandit lvl 1 → lvl 2

Tags: 
Date:

# Goal
The password for the next level is stored in a file called - located in the home directory

# Approach
* Its as simple as cat a file, but the problem is that this file is a  "*./file*" so you need to do a specific command for these kind of files.

## Output / Result
```bash
bandit1@bandit:~$ cat -
__
^C        
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```



# Commands user
* cat ./-