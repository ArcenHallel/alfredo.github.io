# Bandit lvl 13 → lvl 14

Tags: 
Date:

# Goal

The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on
# Approach
after signing into bandit13 and do some recon
you will see that there is a file ... cat the file and we get a ssh private key for bandit14. 
Since we have a private key we dont need a password to log into bandit14 will simply use the ssh key instead
* cat for the key on bandit13 
* grab ssh key and save to our machine, exit bandit13
* give proper permission to the ssh key file 
* log into bandit14 using ssh key

Once you have logged in to bandit 14 make sure to file the password for this user to continue to bandit 15!
## Output / Result

```bash
bandit13@bandit:~$ ls
sshkey.private
```

(I wont show key so cat the file yourself)

back on your machine give perm to file and log back using  `-i {file}`
```bash
─$ chmod 600 bandit14.key 

ssh -i bandit14.key -p 2220 bandit14@bandit.labs.overthewire.org

```

# Commands user
* ls
* cat 
* ssh -i 
* nano 