---
{}
---

**~read the scenario~**

10.10.10.whatever- indicates its a private IP.
outside global IP 216.40.231.9

port 80 /http
port 443/ https
1) connect 10.0.0.105:49152 to comptia.org/aboutus
the 10.10.0.105  is connecting to comptia page on 77.72.206.25:443<--- comptias webserver IP

1) connect 10.0.0.108:49152 to comptia.org/events/all-events 10.10.0.108 is connecting to comptia page on 77.72.206.25:443<--- comptias webserver IP

NAPT(network address port translation) firewall 
inside local IP: 10.0.0.1
outside global IP:216.40.231.9

2) firewall open connections for: 216.40.231.9:60105
                          216.40.231.9:60108
	they are passing through the same firewall so the only difference is the ports they are passing through

3) server reply to 216.40.231.9:60108 and 216.40.231.9:60105

comptia will not see the internal IP address instead the firewalls IP will be shown.

60105 
      >both are [ephemeral ports](https://www.ncftp.com/ncftpd/doc/misc/ephemeral_ports.html)
60108 

#networking #Security+ #comptia #firewall 

##########################################################################
_____________________
##########################################################################

**~read the scenario~**

in this scenario  the firewall was misconfigured, so we have to go back and reconfigure and make some adjustments.

- allow web traffic and domain name resolution to 198.134.5.6.
- disallow all traffic from 208.91.196.105
- ensure there is an implicit deny on the firewall rules.

| source         | source port | destination  | destination port | protocol | action |
| -------------- | ----------- | ------------ | ---------------- | -------- | ------ |
| any            | any         | 198.134.5.32 | 8080             | tcp      | permit |
| any            | any         | 198.134.5.6  | 80               | tcp      | permit |
| any            | any         | 198.134.5.6  | 53               | udp      | permit |
| 208.91.196.105 | any         | any          | any              | tcp/udp  | deny   |
| any            | any         | any          | any              | any      | deny   |

port [8080](https://www.speedguide.net/port.php?port=8080) is sometimes used for http traffic
port [53](https://www.speedguide.net/port.php?port=53) is associated with DNS

#dns #https #firewall #comptia #networking 

##########################################################################
_____________________
##########################################################################

-  only internal users(developers) should have elevated user accounts
- clients should have minimal access.
- all systems/accounts currently belong to the same security group.
- admin has not created any new security groups
- admin should not use default accounts
- there should be four descriptive levels of security defined for permission types
- groups will provide the required permissions to resources.
- customers can access only the front-end server.
- applications and storage will not use user accounts for access


| system/entity   | container    | back-end server | front-end server | users        |
| --------------- | ------------ | --------------- | ---------------- | ------------ |
| access type     | programmatic | programmatic    | user account     | clients      |
| security groups | private      | private         | public           | subscription |
| policy/role     | internal     | internal        | extrenal         | customers    |

the management account currently uses [root] access. an [user account] account should be used instead.
a development best practice would be to utilized an [secret key](https://www.investopedia.com/terms/p/private-key.asp) or any application that are in development.


- for access type the container and back-end server should not accessible by the front-end server or users.
- front-end is a webpage so it should be exposed to the public since its public facing 
- back-end should be private and programmatic to allow APIs to access 
- since in the scenario stated that no user access had not been assigned, everyone was using root access account which should ***NEVER HAPPEN***.
- in development [secret keys](https://www.investopedia.com/terms/p/private-key.asp)  are used to make sure the data that they are working with is encrypted and can not be viewed in plain text. anyone without the key will only see gibberish 

##########################################################################
_____________________
##########################################################################

this scenario is talking about digital signature.
SHA-1 hashes are always the same length no matter what.
alice creates the sha-1.....then encrypts it with ............ to create 

sha-1 ------------------> Alice's Private key --------------> digital signature

next, alice attaches.....        ...to the original message.....     ... to deliver to bob.

alice digital signature------------> to the original message-------> to bob

bob decrypts the original message containing.....    ....using....         ....resulting in the sha-1 has of the original message.

bobs digital signature -------------------> alices's public key------------------> 6071B45FC3

bob then performs a comparison of the hash/message digest results.............. and find his computed hash is ............. therefore can bob confirm the messages integrity 

bob------------------------------------------> 9071845CE3-------------------------------------->No

6071B45FC3 and 9071845CE3 from what is suppose to be alice's message the hashes do not match and we have lost integrity.

message digest or hash is sometimes called a fingerprint in this scenario 

##########################################################################
_____________________
##########################################################################

in this scenario we are offboarding a ex employee which had administration access.

C:\Users\Administrator net user bob /active: no
C:\Users\Administrator net user administrator: Enf0rc3Le@$tPr1v!lege


	Network Security Devices:    Action: Change Credentials 
		- Administrator 
		- Alice

	AD Security Groups:          Action: Change Credentials 
		- Service Administrator
		- Data Administrator
		- Domain Controllers

	Windows Server on Azure:     Action: Change Credentials
		- Administrator 
		- Alice
		- Bob

since bob was the system admin before and had administrator access to the system we need to change credentials and remove bobs full access 

whenever sysadmin leaves the company its important to do proper off boarding since they have access to administrator privileged access

##########################################################################
_____________________
##########################################################################

mimkatz is used to target SAM: windows *security account manager* 
if you had muli-factor authentication to logging in, even if your account credentials are compromised you still need to use your multi-factor authentication to log in.



hybrid attacks are exactly as it sounds using 2 forms of attack example: using haveibeenpwnded.com and using some OSINT by gathering information from other sources to figure out the password



| attacker 1 | file used                                                              | password attack    | tool used       | protection method against attack:                                      | vitcim 1 |
| ---------- | ---------------------------------------------------------------------- | ------------------ | --------------- | ---------------------------------------------------------------------- | -------- |
|            | windows security account manager (sam) registry hive (samdump::hashes) | offline attack     | mimikatz        | 3 factor authentication application: windows active directory          |          |
| attacker 2 | files(s) used                                                          | password attack    | tool used       | protection method against attack:                                      | vitcim 2 |
|            | /wordlist/rockyou.txt.gz, captured_hashes.txt                          | brute force attack | hashcat         | 3 factor authentication application: oracle database 19c, amazon linux |          |
| attacker 3 | file used                                                              | password attack    | tool used       | protection method against attack:                                      | vitcim 3 |
|            | sha1-hased-passwords-                                                  | hybrid attack      | john the ripper | 2 factor authentication application: enterprise azure AD               |          |


attack 1 is using windows. we know this cause of the windows security account manager (sam) and mimikatz is used specificly for SAM attacks 

attack 2 /wordlist/rockyou.txt.gz, captured_hashes.txt is linux so, we can assume hashcat is being used along with the rockyou.txt, also in the scenario it states the rockyou.txt and "hashes" giving us more assurance that hashcat is being used.

attack 3 we know sha1 is being used also the scenario states website haveibeenpwned is also being used with john the ripper so we have multiple attacks in play here.

##########################################################################
_____________________
##########################################################################


https://www.comptia/org 198.134.5.6
Scenario 1:
	"I'm trying to browse this website using an ip address when i do , my browser displays a certificate error. what's wrong?"

answer 1 : the cert is configured with FQDN not with the IP in the domain 
answer 2: connecting using https://www.comptia/org  instead will likely solve the issue.

Scenario 2:
	"I know my certificate is configured correctly, so are you saying my issue may be client related?"

https://www.comptia/org 198.134.5.6 

answer 1: client is missing chain of trust.
answer 2: install root CA-G2 Cert
answer 3: install secure CA-G2 Cert

in this question, it shows us the cert is given by go daddy and it looks to be in good standing, but in the client machine the Certs from godaddy are not present on the list 


##########################################################################
_____________________
##########################################################################

Message: I received an email from a routine vendor asking for a copy of a purchased order. they are always friendly and ask how everyone is. they asked if it was ok to send a purchase order back for an update. an hour later I received an email with purchase order document attached. I clicked and opened it. it was a document that asked to verify banking information, which i provided. HELP!

looked at email message - received from <jim@t0psupplymerchant.com (top supply merchant) />

DIAGNOSIS: spear phishing  ADVERSARY TECHNIQUE: typo squatting   ADVERSARY TATCTIC: familiarity 

	spear phishing because it was a targeted email attack. typo squatting cause that email is suppose to be "top supply merchant not t0p supply merchant" and the tactic is familiarty since the vendor is a known person 

Message: I received an email from IT to install the remote app to fix my pc, i had to ship out a few boxes, so I let the support person work as he was in a rush. when I came back my computer was on a pornography site and it keeps doing pop ups. what were you fixing anyways?

found dns (hosts file) to be misconfigured with malicious entries 

DIAGNOSIS: phishing  ADVERSARY TECHNIQUE: Pharming    ADVERSARY TATCTIC: Urgency 

	so this was a phishing attack since our client recevived a email from IT to install remote app fix: the technique used is Pharming since the DNS host file was targetted: and the tactic is urgency because the support person was in a hurry 


Message: I received a call from one of our vice presidents. well, he said he was the vice president. he was a little angry bout the faxes not working. I'm new here and i thought it was best to help him. he sent me a file he needed faxed ASAP, I opened it and there was no document but now every hour my applications close and my computer reboots, i keep losing my work!

found script running in scheduled tasks to force a computer restart.

DIAGNOSIS: vishing   ADVERSARY TECHNIQUE: logic bomb    ADVERSARY TATCTIC: authority 

	this is going to be a vishing attack since our client received a call from your "vice president": this seems to be a logic bomb because every hour our clients computer shuts off making it seem that there is a scheduled tasks thats making this happen: the tactic is authority since the "vice president" called and said he needs this done ASAP 

##########################################################################

this scenario is talking about RAID 1 and RAID 5

what RAID 1 is a mirror of the disk, so it will reflect exactly what disk 0 has
RAID 1 usually has 2 disk the 0 and 1 disk and in this scenario it had a 3rd disk and was used to throw us off. It can be done thought its not common but can be done. 

| RAID 1 | Disk 0 | Disk 1 | Disk 2 |
| ------ | ------ | ------ | ------ |
|        | bit 1  | bit 1  | bit 1  |
|        | bit 1  | bit 1  | bit 1  |
![[Pasted image 20240506222815.png]] ![[Pasted image 20240506222928.png]] 
 * Would RAID 1 configuration protect data if one complete disk was lost? Yes.

RAID 5 does parity what it means is you need 3 disk and the parity goes on all 3 disk and if one of the disk fail the parity along with the remaining disk will rewrite the data on the newly added disk 

![[Pasted image 20240506230306.png]]

| RAID 5 | Disk 0     | Disk 1     | Disk 2     |
| ------ | ---------- | ---------- | ---------- |
|        | bit 1      | bit2       | parity bit |
|        | bit 2      | parity bit | bit 1      |
|        | parity bit | bit 1      | bit 2      |
* parity is used to check for errors, it wont fix the errors.

##########################################################################

| incident/entitiy            | 1. identify which cyber kill chain attack state is occurring : | 2. identifiy an incident response process mitigation set: | 3. identify and inciduent response process future prevention step: | 4. idnentify which exercise(s) will strengthen incident response: |
| --------------------------- | -------------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------ | ----------------------------------------------------------------- |
| 1. federal goverment agency | action on objective                                            | eradication                                               | lessons learned                                                    | all exercises                                                     |
| 2. major bank               | exploitation                                                   | containment                                               | perperation                                                        | all exercises                                                     |
| 3. major retail             | installation                                                   | containment                                               | perperation                                                        | all exerices                                                      |

1) Incident 1 -Federal Government Agency 
  * US-CERT (CISA) alerts the agency to possible data exfiltration detected on its networks. The government agency activates the CIRT (your org)
  * hacker1 us dangerously close to the most sensitive personnel databases. the CIRT manages to isolate and remediate hacker1.
  * during a secondary review of agency systems, the CIRT discovers hacker2 had already established a foothold and engaged in C2 data-exfiltration for weeks. 

2) Incident 2 - major bank:

* when examining web application firewalls (WAFs) the CIRT discovered hacker1 attacking a misconfigured bank firewall.
* hacker1 is relaying commands to back-end cloud servers (or "testing them") to extract data about bank servers architecture and topology, the hacker's actions suggest advanced knowledge of the cloud service provider's infrastructure.
* hacker1 has not executed exfiltration or injected malicious code; has succeeded in taking advantage of a misconfiguration in WAF to gain unauthorized access.

 3) Incident 3 - major retailer: 
* after an audit of the VPN infrastructure, the CIRT discovers that hacker1 (and other accomplices) have already stolen and used existing VPN credentials. the CIRT detects a lack of network segmentation.
* hacker1 and others, now labeled hackergroup1, have created multiple footholds and multiple administrator accounts.
* the CIRT focuses on hacker4, observing that the hacker is delivering weaponized code into point-of-sales POS data servers to expand persistence.

##########################################################################

ARO: 5 attacks per year
SLE: 50,000 USD
ALE: 5 x 50,000 = 250,000
ALEm: 80%

we need to do a quantititive and qualitive process
	this is quantititive process
$(ALE* ALEm) - cost of solution$
         $cost of solution$

calculation $250,000$ * .80 - $50,000$
		$50,000$
ROSI 300%        solution saves ($) $150,000

Risk management strategy action: mitigation

recommendation: purchase net-gen SIEM with UEBA/SOAR

$250,000*0.8 = 200,000 (ALE* ALEm)$

$200,000 - 50,000 = 150,000 (now subtract SLE)$

$150,000/ 50,000 = 3 (then divide the cost by SLE)$

on the last step we have to do a qualitive process
justify your recommendations based on the impact and probability of IP theft 

High: since our CEO stated much concern that hackers are going to be relentless 

IP theft probability: High - it is stated in the scenario that IP theft will be high and our CEO is also concerned.
