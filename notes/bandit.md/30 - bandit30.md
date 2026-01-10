# Bandit lvl 30 → lvl 31

Tags: 
Date:

# Goal
There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

Clone the repository and find the password for the next level.
# Approach
this one was really easy and does not need much explaining. here we are using tags
## Output / Result
```bash
bandit30@bandit:/tmp$ mkdir dir002
bandit30@bandit:/tmp$ cd dir002
bandit30@bandit:/tmp/dir002$ ls
bandit30@bandit:/tmp/dir002$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo 
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit30-git@localhost's password: 
Permission denied, please try again.
bandit30-git@localhost's password: 
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.

```

this is pretty much the same but instead of hash we use tags
```bash
bandit30@bandit:/tmp/dir002$ ls
repo
bandit30@bandit:/tmp/dir002$ cd repo/
bandit30@bandit:/tmp/dir002/repo$ git log --all
commit de654f201881f820c364f176ffcdea2876431bee (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:14 2025 +0000

    initial commit of README.md
bandit30@bandit:/tmp/dir002/repo$ git tag
secret
bandit30@bandit:/tmp/dir002/repo$ git show secret 
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```

# Commands user
* 