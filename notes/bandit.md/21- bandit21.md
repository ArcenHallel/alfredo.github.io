# Bandit Level 21 → 22

Tags: 
Date: 

## Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
## Approach
following what the goal says lets check out the `/etc/cron.d/` and will go from there
## Output / Result

```bash
bandit21@bandit:$ cd /etc
bandit21@bandit:/etc$ cd cron.d
bandit21@bandit:/etc/cron.d$ ls
behemoth4_cleanup  cronjob_bandit23  leviathan5_cleanup    sysstat
clean_tmp          cronjob_bandit24  manpage3_resetpw_job
cronjob_bandit22   e2scrub_all       otw-tmp-dir
```

once in /etc/cron.d we see a file `cronjob_bandit22` if we cat the file it tells us what its doing. we see its using another file called `/usr/bin/cronjob_bandit22.sh`
```bash
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22 
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```

cat the file and we see its changing permissions of another file under `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`
```bash
bandit21@bandit:/usr/bin$ cat cronjob_bandit22.sh 
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

```

so lets cat that tmp file and see what we get
```bash
bandit21@bandit:/usr/bin$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

and our output looks like a password!
## Commands
* cd 
* ls
* cat