---
{}
---

#### Your Final Report


|   |   |
|---|---|
|Total marks|37|
|Total Questions|25|
|Questions correctly answered|20|
|Success ratio|80%|
|Marks secured|32|
|Percentage secured|86.49%|

going over notes here, but my grades not bad 

 1) Which of the following terms is commonly used to describe an unsolicited advertising message?

-    Spyware
-    Adware ( Your answer) X
-    Malware
-    ==Spam ( Missed)==

 Your answer to this question is incorrect or incomplete.
 
SPIM stands for "Single Purpose IMplicitly-parallel Instruction-stream Machine." It's a type of computer architecture designed for executing instructions in parallel, particularly suited for applications like digital signal processing and multimedia processing. However, in the context of security, SPIM can also refer to =="Spam over Internet Messaging," which is unsolicited or unwanted messages sent over instant messaging platforms. Depending on the context of your study material, it could refer to either of these meanings.==

2)  Which of the following answers refer to the characteristic features of pharming? (Select 3 answers)
-    Domain hijacking ( Your answer) X
-    ==Traffic redirection ( Your answer)
-    ==Fraudulent website ( Your answer)
-    Password attack
-    ==Credential harvesting ( Missed)==

 Your answer to this question is incorrect or incomplete.

  
Pharming is a cyber attack aimed at redirecting website traffic to a fraudulent website, often for the purpose of stealing sensitive information such as login credentials, financial data, or personal information. Here are some characteristic features of pharming:

1. **Domain Name System (DNS) Manipulation**: ==Pharming attacks often involve manipulation of DNS servers or local hosts files to redirect legitimate domain names to malicious IP addresses.== This can be done through various techniques such as DNS cache poisoning or DNS server compromise.
    
2. **DNS Spoofing**: ==Attackers may spoof DNS responses to redirect users to malicious websites without their knowledge.== This is achieved by impersonating legitimate DNS servers and providing false IP addresses for requested domain names.
    
3. **Hosts File Modification**: Pharming attacks can also involve modifying the hosts file on a victim's computer to redirect specific domain names to malicious IP addresses. This can be done through malware or unauthorized access to the system.
    
4. **SSL/TLS Certificate Spoofing**: In some cases, attackers may use fraudulent SSL/TLS certificates to make the malicious website appear legitimate. This can trick users into believing they are accessing a secure website when they are actually being redirected to a phishing site.
    
5. **Cross-Site Scripting (XSS)**: Pharming attacks may utilize cross-site scripting vulnerabilities on legitimate websites to inject malicious scripts that redirect users to fraudulent websites. This can be particularly effective in cases where users trust the compromised website.
    
6. **Persistent Redirects**: Once a pharming attack is successful, the redirection of traffic to the malicious website can be persistent, meaning users continue to be redirected even after attempts to visit the legitimate site. This can prolong the exposure of users to the attack.
    
7. **Targeting Financial and E-commerce Websites**: Pharming attacks often target financial institutions, e-commerce websites, and other platforms where users are likely to enter sensitive information. ==By redirecting users to fake versions of these websites, attackers aim to steal login credentials, credit card numbers, and other valuable data.==
    

Understanding these characteristic features of pharming can help individuals and organizations take preventive measures to protect against such attacks, such as implementing secure DNS practices, regularly monitoring DNS traffic for anomalies, and deploying anti-pharming solutions.

3) 

| Question                    | Answer                                                                                                   | Your answer                                                                                             | Result         |
| --------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | -------------- |
| Bracketing                  | Providing a high and low estimate in order to entice a more specific number                              | Providing a high and low estimate in order to entice a more specific number                             | Correct answer |
| Confidential bait           | Pretending to divulge confidential information in hopes of receiving confidential information in return  | Pretending to divulge confidential information in hopes of receiving confidential information in return | Correct answer |
| Deliberate false statements | Saying something wrong in the hopes that the person will correct the statement with true information     | Saying something wrong in the hopes that the person will correct the statement with true information    | Correct answer |
| Feigned ignorance           | Pretending to be ignorant of a topic in order to exploit the person’s tendency to educate                | Pretending to be ignorant of a topic in order to exploit the person’s tendency to educate               | Correct answer |
| Denial of the obvious       | ==Saying something wrong in the hopes that the person will correct the statement with true information== | ==Pretending to be ignorant of a topic in order to exploit the person’s tendency to educate==           | Wrong answer   |
| Flattery                    | Using praise to coax a person into providing information                                                 | Using praise to coax a person into providing information                                                | Correct answer |

 Your answer to this question is incorrect or incomplete.

4)  Which of the following is used in data URL phishing?

-    ==Prepending ( Missed)
-    Typosquatting ( Your answer)  X
-    Pretexting
-    Domain hijacking

 Your answer to this question is incorrect or incomplete.

i should give context to what prepending is
source chatGPT:

In cybersecurity, "prepending" typically refers to a technique used in access control lists (ACLs) or firewall rules to prioritize or specify certain rules over others. Here's how it works:

1. **Access Control Lists (ACLs)**: In network security, ACLs are used to control access to resources by permitting or denying traffic based on various criteria such as source IP addresses, destination IP addresses, ports, protocols, etc. When multiple ACL entries match a packet, the device applies the rules in the order they are listed until a match is found.

2. **Prepending**: Prepending involves placing specific rules or entries at the beginning of an ACL or firewall rule set. These rules are evaluated first before the rest of the rules. By doing this, you can prioritize certain traffic or apply specific actions to packets matching those rules before considering other rules in the list.

3. **Example**: For example, let's say you have an ACL with multiple entries to allow or deny traffic to certain destinations. If you prepend a rule to deny traffic from a particular malicious IP address range, that rule will be evaluated first. If the incoming traffic matches this rule, it will be denied, and subsequent rules will not be evaluated for that packet. This can help in blocking known malicious traffic before it reaches the rest of the ACL.

4. **Effectiveness**: Prepending can be an effective strategy in certain situations, especially when dealing with specific threats or when certain rules need to take precedence over others. However, it's essential to carefully plan and manage the order of rules in ACLs to ensure that the desired security policies are enforced effectively without unintended consequences such as allowing unauthorized traffic.

==In summary, "prepending" in cybersecurity refers to the practice of placing specific rules or entries at the beginning of an ACL or firewall rule set to prioritize or specify certain actions for incoming traffic. This technique can help in enforcing security policies and mitigating threats effectively.==

its not hard coded that prepending blocks URL phishing unless you are actively preventing by setting the rules on it 
more sources from GPT;

Prepending is not typically used in the context of URL phishing. URL phishing involves the creation of deceptive or fraudulent web addresses (URLs) that mimic legitimate websites to trick users into divulging sensitive information such as login credentials or financial details.

However, in the broader context of cybersecurity defenses, including firewalls, web filters, or email security solutions, rules can be prioritized or ordered in a way that might mitigate the risk of phishing attacks. For example:

1. **Web Filtering**: Web filtering solutions can use blacklists or reputation-based filtering to block known phishing URLs. Prepending a rule to block access to known phishing domains or URLs could help in preventing users from accessing these malicious sites.

2. **Email Security**: In email security solutions, rules can be prioritized to flag or block emails containing suspicious URLs. Prepending rules to prioritize scanning emails for phishing indicators, such as malicious links or deceptive domain names, could help in detecting and blocking phishing attempts.

3. **Firewalls**: Firewalls can also inspect network traffic for malicious URLs. Prepending rules to prioritize the inspection of web traffic for known phishing patterns or signatures could help in blocking access to phishing sites.

==While "prepending" itself may not directly combat phishing attacks, the strategic ordering of security rules within various cybersecurity defenses can contribute to a comprehensive defense-in-depth strategy aimed at mitigating the risk of phishing and other cyber threats.==

5)  An attacker impersonating a software beta tester replies to a victim's post in a forum thread discussing the best options for affordable productivity software. A while later, he/she follows up by sending the victim private message mentioning the discussion thread and offering free access to a closed beta version of a fake office app. Which social engineering principles apply to this attack scenario? (Select 3 answers)

-    Authority
-    Intimidation
-    Consensus ( Your answer) X
-    ==Scarcity ( Missed)== "closed beta, this implies scarcity"
-    ==Familiarity ( Your answer)== from the scenario these people have had interactions during and later on in the scenario implying familiarity 
-    ==Trust ( Your answer)== since the attacker was impersonating a software beta tester and the victim believed it to be true trust is implyied
-    Urgency

 Your answer to this question is incorrect or incomplete.

this one caught me, the key word "closed beta" you should already know from my gaming back ground that these kinds of things are limited and not given openly, so there would be some scarcity involved with "closed beta access."