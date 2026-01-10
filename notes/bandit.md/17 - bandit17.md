# Bandit lvl 17 → lvl 18

Tags: 
Date:

# Goal

There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19
# Approach

there are 2 files we have to sort them and find the 2 strings that got changed

## Output / Result

```bash
bandit17@bandit:~$ cat passwords.* | sort | uniq -u
CgmS55GVlEKTgx8xpW8HuWnHlBKP924b
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

```
# Commands user
* cat 
* sort 
* uniq