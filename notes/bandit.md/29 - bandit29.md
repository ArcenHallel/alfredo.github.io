# Bandit lvl 29 → lvl 30

Tags: 
Date:

# Goal
There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.

Clone the repository and find the password for the next level.
# Approach
we continue to learn more about git and its log functions
## Output / Result
```bash
bandit29@bandit:/tmp/dir001$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit29-git@localhost's password: 
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
Receiving objects: 100% (16/16), 1.44 KiB | 1.44 MiB/s, done.
Resolving deltas: 100% (2/2), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
bandit29@bandit:/tmp/dir001$ ls
repo
bandit29@bandit:/tmp/dir001$ cd repo/
bandit29@bandit:/tmp/dir001/repo$ ls
README.md
bandit29@bandit:/tmp/dir001/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/dir001/repo$ git log
commit 873b7f66c519fabdfcbdde431d75921d2cea369d (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:12 2025 +0000

    fix username

commit c4d522ba8d044c2c42b421b41ddfb364e878b76e
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:12 2025 +0000

    initial commit of README.md
bandit29@bandit:/tmp/dir001/repo$ git log --all
commit 873b7f66c519fabdfcbdde431d75921d2cea369d (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:12 2025 +0000

    fix username

commit d9fa2d0412351c7fa4302313c61f965dbe3b78fc (origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Fri Aug 15 13:16:12 2025 +0000

    add data needed for development

commit 1cd92d39ebcce3cbea6c94798964e8d3e270d449 (origin/sploits-dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Fri Aug 15 13:16:12 2025 +0000

    add some silly exploit, just for shit and giggles

commit c4d522ba8d044c2c42b421b41ddfb364e878b76e
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:12 2025 +0000

    initial commit of README.md

commit 7b12d64a8af41daca3e7fd2edfdc40f18f2257b0
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:12 2025 +0000
    add gif2ascii
```

this is a lot to look at so lets make this easier to look at with  `git log --all --oneline`
```bash
bandit29@bandit:/tmp/dir001/repo$ git log --all --oneline
873b7f6 (HEAD -> master, origin/master, origin/HEAD) fix username
d9fa2d0 (origin/dev) add data needed for development
1cd92d3 (origin/sploits-dev) add some silly exploit, just for shit and giggles
c4d522b initial commit of README.md
7b12d64 add gif2ascii
```

the --oneliner gives us a small piece of the hash that we can use to search the logs
```bash
bandit29@bandit:/tmp/dir001/repo$ git show d9fa2d0
commit d9fa2d0412351c7fa4302313c61f965dbe3b78fc (origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Fri Aug 15 13:16:12 2025 +0000

    add data needed for development

diff --git a/README.md b/README.md
index 1af21d3..bc6ad3d 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials
 
 - username: bandit30
-- password: <no passwords in production!>
+- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```

# Commands user
* 