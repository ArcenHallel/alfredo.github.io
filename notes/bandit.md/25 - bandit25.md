# Bandit lvl 25 → lvl 26

Tags: 
Date:

# Goal
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

    NOTE: if you’re a Windows user and typically use Powershell to ssh into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.



# Approach
since the goal is hinting that the shell for bandit26 is not /bin/bash, but something else we should look at the passwd file and see what shell or program is running when logging in as bandit26

## Output / Result
when we log in as bandit26 we instantly get logged out.
```bash
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost
Could not create directory '/home/bandit25/.ssh'.
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ECDSA key fingerprint is SHA256:98UL0ZWr85496EtCRkKlo20X3OPnyPSB5tB5RPbhczc.
Are you sure you want to continue connecting (yes/no)? yes
Failed to add the host to the list of known hosts (/home/bandit25/.ssh/known_hosts).
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames
  _                     _ _ _   ___   __  
 | |                   | (_) | |__ \ / /  
 | |__   __ _ _ __   __| |_| |_   ) / /_  
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
 |_.__/ \__,_|_| |_|\__,_|_|\__|____\___/
Connection to localhost closed.
bandit25@bandit:~$
```

why is this happening? lets check out the /etc/passwd/bandit26 file to get more information.
```bash
bandit25@bandit:~$ cat /etc/passwd | grep -i bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
```

```bash
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

more ~/text.txt
exit 0
```

the clue here is the `more ~/text.txt` what happening is when we log in its reading that `text.txt` file using command `more`

looking at the man pages of `more` https://man7.org/linux/man-pages/man1/more.1.html under COMMANDS 
```bash

       v
           Start up an editor at current line. The editor is taken from
           the environment variable VISUAL if defined, or EDITOR if
           VISUAL is not defined, or defaults to vi(1) if neither VISUAL
           nor EDITOR is defined.
```

we can get into the `showtext.txt` once in vim editor we can execute commands.
To prevent the .txt file from auto reading we can minimize the terminal to allow us to get into the editor.
![[Pasted image 20251005164144.png]]

then we can press "v" this will get us into the editor.

once in vim ( you need to know a little about how vim works)
we can execute commands 
lets check out the value of shell by using `:set shell`
![[Pasted image 20251005164649.png]]

we get back `shell=/usr/bin/showtext` its still reading that showtext.txt, but since we we can edit this value lets change it back to `shell=/bin/bash` by using `:set shell=/bin/bash` and then running `:shell`
![[Pasted image 20251005165125.png]]
# Commands user
* ssh 
* cat 
* vim
* 