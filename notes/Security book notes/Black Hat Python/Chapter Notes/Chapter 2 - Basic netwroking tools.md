## Main Idea
- Network protocols TCP/UDP clients and servers, the usefullness of Netcat.

## Key Tools
- netcat
- ssh
- paramiko
- ftp

## Important Concepts
- purpose of sockets
- tcp/udp work on ipv4 (and ipv6)
- understanding ports
- hexdump 
## Useful Code 
attacker machine: $python ssh_server.py 

victim machine: python ssh_rcmd.py 

	if you look at the code for both of these scripts you would see that the ATTACKER is listening waiting for VICTIM to type password and we will be authenticated on the ATTACKER machine through ssh.

## My Notes
learning about the functions of ssh and ports. Forward and reverse tunneling 