# Bandit lvl 27 → lvl 28

Tags: 
Date:

# Goal

There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.

Clone the repository and find the password for the next level.
# Approach
this one is super straight forward but it gave me some issues.
## Output / Result
first make a /tmp dir or use one that you have been using.
```bash
bandit27@bandit:/tmp$ mkdir help000
bandit27@bandit:/tmp$ cd help000
```

```bash
bandit27@bandit:/tmp/help000$ git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

!!! You are trying to log into this SSH server on port 22, which is not intended.
!!! If you are trying to log in to an OverTheWire game, use the port mentioned in
!!! the "SSH Information" on that game's webpage (in the top left corner).

bandit27-git@localhost: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

i keep getting denied access and one clue we have is  
`!!! You are trying to log into this SSH server on port 22, which is not intended.`
the entire bandit game we have not used any other port then 2220 for ssh connections. 

```bash
bandit27@bandit:/tmp/help000$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit27-git@localhost's password: 
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
```

the biggest change here is `bandit27@bandit:/tmp/help000$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo` we are specify port 2220

```bash
bandit27@bandit:/tmp/help000$ ls -la
total 1284
drwxrwxr-x    3 bandit27 bandit27    4096 Oct  6 00:39 .
drwxrwx-wt 7121 root     root     1302528 Oct  6 00:40 ..
drwxrwxr-x    3 bandit27 bandit27    4096 Oct  6 00:40 repo
bandit27@bandit:/tmp/help000$ cd repo/
bandit27@bandit:/tmp/help000/repo$ ls
README
bandit27@bandit:/tmp/help000/repo$ cat README 
The password to the next level is: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN 
```
# Commands user
* cd 
* mkdir 
* git clone
* ssh
* ls -la 
* cat