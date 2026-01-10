# Bandit lvl 31→ lvl 32

Tags: 
Date:

# Goal
There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.

Clone the repository and find the password for the next level.

# Approach
so for this one i had help cause i dont know much about git.
from this challenge i learned a couple of this, ill show my work down below 
## Output / Result

nothing new here just git the repo
```bash
bandit31@bandit:~$ mkdir /tmp/dir003
bandit31@bandit:~$ cd /tmp/dir003
bandit31@bandit:/tmp/dir003$ git cline  ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
git: 'cline' is not a git command. See 'git --help'.

The most similar command is
        clone
bandit31@bandit:/tmp/dir003$ git clone  ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit31-git@localhost's password: 
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.

```

```bash
bandit31@bandit:/tmp/dir003$ ls
repo
bandit31@bandit:/tmp/dir003$ cd repo/
bandit31@bandit:/tmp/dir003/repo$ ls
README.md
bandit31@bandit:/tmp/dir003/repo$ git tag
bandit31@bandit:/tmp/dir003/repo$ git log --all
commit 508f78be4568c9cf050249a441800ad36c1fe5bd (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:15 2025 +0000

    initial commit
```

since the log did not show much i cat the file to see if it has any clues
```
bandit31@bandit:/tmp/dir003/repo$ ls
README.md
bandit31@bandit:/tmp/dir003/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
```

here is where i had no clue how to continue but with some help i was able to learn and complete the task

what we have to do is make a file with the details below
Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
    
```
bandit31@bandit:/tmp/dir003/repo$ echo "May I come in?" > key.txt
bandit31@bandit:/tmp/dir003/repo$ ls
key.txt  README.md
bandit31@bandit:/tmp/dir003/repo$ git add key.txt 
The following paths are ignored by one of your .gitignore files:
key.txt
hint: Use -f if you really want to add them.
hint: Turn this message off by running
hint: "git config advice.addIgnoredFile false"
```

the clue here is actually in the above code the "hint: "git config advice.addIgnoredFile false" "
there is a .gitignore file that is ignoring all `*.txt`  files 
so what we do here is remove that configuration with `echo '' > .gitignore` 
once we make the change we commit it and upload it 
```
bandit31@bandit:/tmp/dir003/repo$ cat .gitignore 
*.txt
bandit31@bandit:/tmp/dir003/repo$ echo '' > .gitignore 
bandit31@bandit:/tmp/dir003/repo$ cat .gitignore 

bandit31@bandit:/tmp/dir003/repo$ git add key.txt 
bandit31@bandit:/tmp/dir003/repo$ git commit -m 'upload key.txt'
[master af1fd6a] upload key.txt
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt```

```

after the upload we push the change to the origin master 
then we are prompted for password of bandit31
```bash
bandit31@bandit:/tmp/dir003/repo$ git push origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit31-git@localhost's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 327 bytes | 327.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
```

# Commands user
* 