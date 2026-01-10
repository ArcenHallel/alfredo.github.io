# Bandit lvl 18 → lvl 19

Tags: 
Date:

https://nasrallahbaadi.com/posts/Bandit-15-20/
# Goal

The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.
# Approach

this one we are going to use remote command execution
## Output / Result

we keep getting kicked out from the connection by logging in normally
```bash
└─$ ssh bandit18@bandit.labs.overthewire.org -p 2220

Byebye !
Connection to bandit.labs.overthewire.org closed.
```

what we know is that there is a file named readme in the home dir, so lets try some remote command execution by adding in  `cat readme`
```bash
└─$ ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit18@bandit.labs.overthewire.org's password: 
Permission denied, please try again.
bandit18@bandit.labs.overthewire.org's password: 
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```
# Commands user
* ssh
* cat