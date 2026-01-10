# Bandit lvl 15 → lvl 16

Tags: 
Date:

# Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.


# Approach

its to use SSL encryption but telnet sends everything unencrypted... so thats out of the question

since we need to connect to a port with SSL encryption we are going to be using openssl with 2 subcommands,
* -quiet: this is print less information so we dont clutter our screen ( you can still try without this command to see the type of info we get back)
* -connect: with this we specify what we are connecting to
## Output / Result

```bash
bandit15@bandit:~$ openssl s_client -quiet -connect localhost:30001
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx


```
# Commands user
* openssl