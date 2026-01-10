 ***Task 4 Mapping with ATT&CK Navigator

###
* How many MITRE ATT&CK techniques are attributed to APT33? 31

* Upon applying the IaaS platform filter, how many techniques are under the Discovery tactic? 13
for this task we are just messing with MITRE and this last question confused me since i did not understand what it was asking me, but i had to toggle off all the other filters and only leave the IaaS filter and then look under the discovery techniques 
####


 ***Task 6 STRIDE Framework***
the last task in the scenario through me off, do a rerun of it and follow the stride model everything but the S3 bucket i had right.



### DREAD Framework


| DREAD           | definition                                                                                                                                                                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Damage          | The potential harm that could result from the successful exploitation of a vulnerability. This includes data loss, system downtime, or reputational damage.                                                                                 |
| Reproducibility | The ease with which an attacker can successfully recreate the exploitation of a vulnerability. A higher reproducibility score suggests that the vulnerability is straightforward to abuse, posing a greater risk.                           |
| Exploitability  | The difficulty level involved in exploiting the vulnerability considering factors such as technical skills required, availability of tools or exploits, and the amount of time it would take to exploit the vulnerability successfully.     |
| Affected Users  | The number or portion of users impacted once the vulnerability has been exploited.                                                                                                                                                          |
| Discoverability | The ease with which an attacker can find and identify the vulnerability considering whether it is publicly known or how difficult it is to discover based on the exposure of the assets (publicly reachable or in a regulated environment). |
The categories are commonly phrased with the following questions to ingest the definitions provided above quickly:

* Damage - How bad would an attack be?
* Reproducibility - How easy is it to reproduce the attack?
* Exploitability - How much work is it to launch the attack?
* Affected Users - How many people will be impacted?
* Discoverability - How easy is it to discover the vulnerability?


| DREAD Score     | 2.5                                                                                        | 5                                                     | 7.5                                                              | 10                                                                |
| --------------- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------- |
| Damage          | Minimal infrastructure information disclosure                                              | Minimal information disclosure related to client data | Limited PII leak                                                 | Complete data leak                                                |
| Reproducibility | Multiple attack vectors requiring technical expertise                                      | Minor customisation for public exploits needed        | Little prerequisite technical skills needed to run the exploit   | Users with public exploits can successfully reproduce the exploit |
| Exploitability  | Almost no public exploits are available and need customisation of scripts                  | Complicated exploit scripts available in the wild     | Minimal technical skills are required to execute public exploits | Reliable Metasploit module exists                                 |
| Affected Users  | Almost none to a small subset                                                              | Around 10% of users                                   | More than half of the user base                                  | All users                                                         |
| Discoverability | The significant effort needed to discover the vulnerability chains for the exploit to work | Requires a manual way of verifying the vulnerability  | Public scanning scripts not embedded in scanning tools exist     | Almost all known scanning tools can find the vulnerability        |

Given this guideline, we can assess some known vulnerabilities in the application. Below is an example of scoring provided for each vulnerability.

    Unauthenticated Remote Code Execution (Score: 8)

        Damage (D): 10
        Reproducibility (R): 7.5
        Exploitability (E): 10
        Affected Users (A): 10
        Discoverability (D): 2.5

    Insecure Direct Object References (IDOR) in User Profiles (Score: 6.5)

        Damage (D): 2.5
        Reproducibility (R): 7.5 
        Exploitability (E): 7.5
        Affected Users (A): 10 
        Discoverability (D): 5

    Server Misconfiguration Leading to Information Disclosure (Score: 5)

        Damage (D): 0
        Reproducibility (R): 10
        Exploitability (E): 10
        Affected Users (A): 0
        Discoverability (D): 5





### What is the STRIDE Framework?

The STRIDE framework is a threat modelling methodology also developed by Microsoft, which helps identify and categorise potential security threats in software development and system design. The acronym STRIDE is based on six categories of threats, namely:

| Category               | Definition                                                                                         | Policy Violated |
| ---------------------- | -------------------------------------------------------------------------------------------------- | --------------- |
| Spoofing               | Unauthorised access or impersonation of a user or system.                                          | Authentication  |
| Tampering              | Unauthorised modification or manipulation of data or code.                                         | Integrity       |
| Repudiation            | Ability to deny having acted, typically due to insufficient auditing or logging.                   | Non-repudiation |
| Information Disclosure | Unauthorised access to sensitive information, such as personal or financial data.                  | Confidentiality |
| Denial of Service      | Disruption of the system's availability, preventing legitimate users from accessing it.            | Availability    |
| Elevation of Privilege | Unauthorised elevation of access privileges, allowing threat actors to perform unintended actions. | Authorisation   |

To understand the framework better, let's deep-dive into each category and discuss some examples.

* Spoofing 
    * Sending an email as another user.
    * Creating a phishing website mimicking a legitimate one to harvest user credentials.
* Tampering
    * Updating the password of another user.
    * Installing system-wide backdoors using an elevated access.
* Repudiation
    * Denying unauthorised money-transfer transactions, wherein the system lacks auditing.
    * Denying sending an offensive message to another person, wherein the person lacks proof of receiving one.
* Information Disclosure 
    * Unauthenticated access to a misconfigured database that contains sensitive customer information.
    * Accessing public cloud storage that handles sensitive documents.
* Denial of Service
    * Flooding a web server with many requests, overwhelming its resources, and making it unavailable to legitimate users.
    * Deploying a ransomware that encrypts all system data that prevents other systems from accessing the resources the compromised server needs.
* Elevation of Privilege
    * Creating a regular user but being able to access the administrator console.
    * Gaining local administrator privileges on a machine by abusing unpatched systems.


| Scenario                                                                                                                                              | Spoofing | Tampering | Repudiation | Information Disclosure | Denial of Service | Elevation of Privilege |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | --------- | ----------- | ---------------------- | ----------------- | ---------------------- |
| Sending a spoofed email, wherein the mail gateway lacks email security and logging configuration.                                                     | ✔        |           | ✔           |                        |                   |                        |
| Flooding a web server with many requests that lack load-balancing capabilities.                                                                       |          |           |             |                        | ✔                 |                        |
| Abusing an SQL injection vulnerability.                                                                                                               |          | ✔         |             | ✔                      |                   |                        |
| Accessing public cloud storage (such as AWS S3 bucket or Azure blob) that handles customer data.                                                      |          |           |             | ✔                      |                   |                        |
| Exploiting a local privilege escalation vulnerability due to the lack of system updates and modifying system configuration for a persistent backdoor. |          | ✔         |             |                        |                   | ✔                      |







### PASTA Frame Work

﻿﻿What is the PASTA Framework?

﻿PASTA, or Process for Attack Simulation and Threat Analysis, is a structured, risk-centric threat modelling framework designed to help organisations identify and evaluate security threats and vulnerabilities within their systems, applications, or infrastructure. PASTA provides a systematic, seven-step process that enables security teams to understand potential attack scenarios better, assess the likelihood and impact of threats, and prioritise remediation efforts accordingly.

1) Define the Objectives

    Establish the scope of the threat modelling exercise by identifying the systems, applications, or networks being analysed and the specific security objectives and compliance requirements to be met.
    
2) Define the Technical Scope

    Create an inventory of assets, such as hardware, software, and data, and develop a clear understanding of the system's architecture, dependencies, and data flows.
3) Decompose the Application

    Break down the system into its components, identifying entry points, trust boundaries, and potential attack surfaces. This step also includes mapping out data flows and understanding user roles and privileges within the system.
4) Analyse the Threats 

    Identify potential threats to the system by considering various threat sources, such as external attackers, insider threats, and accidental exposures. This step often involves leveraging industry-standard threat classification frameworks or attack libraries.
5) Vulnerabilities and Weaknesses Analysis

    Analyse the system for existing vulnerabilities, such as misconfigurations, software bugs, or unpatched systems, that an attacker could exploit to achieve their objectives. Vulnerability assessment tools and techniques, such as static and dynamic code analysis or penetration testing, can be employed during this step.
6) Analyse the Attacks

    Simulate potential attack scenarios and evaluate the likelihood and impact of each threat. This step helps determine the risk level associated with each identified threat, allowing security teams to prioritise the most significant risks.
7) Risk and Impact Analysis

    Develop and implement appropriate security controls and countermeasures to address the identified risks, such as updating software, applying patches, or implementing access controls. The chosen countermeasures should be aligned with the organisation's risk tolerance and security objectives.

## PASTA Methodology Guidelines


| Define the Objectives                       | Set clear and realistic security objectives for the threat modelling exercise.<br>    Identify relevant compliance requirements and industry-specific security standards.                                                                                                                    |
| ------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Define the Technical Scope                  | Identify all critical assets, such as systems and applications, that handle sensitive data owned by the organisation.<br>    Develop a thorough understanding of the system architecture, including data flows and dependencies.                                                             |
| Decompose the Application<br>               | Break down the system into manageable components or modules.<br>    Identify and document each component's possible entry points, trust boundaries, attack surfaces, data flows, and user flows.                                                                                             |
| Analyse the Threats<br>                     | Research and list potential threats from various sources, such as external attackers, insider threats, and accidental exposures.<br>    Leverage threat intelligence feeds and industry best practices to stay updated on emerging threats.                                                  |
| Vulnerabilities and Weaknesses Analysis<br> | Use a combination of tools and techniques, such as static and dynamic code analysis, vulnerability scanning, and penetration testing, to identify potential weaknesses in the system.<br>    Keep track of known vulnerabilities and ensure they are addressed promptly.                     |
| Analyse the Attacks<br>                     | Develop realistic attack scenarios and simulate them to evaluate their potential consequences.<br>    Create a blueprint of scenarios via Attack Trees and ensure that all use cases are covered and aligned with the objective of the exercise.                                             |
| Risk and Impact Analysis<br>                |     Assess the likelihood and impact of each identified threat and prioritise risks based on their overall severity.<br>    Determine the most effective and cost-efficient countermeasures for the identified risks, considering the organisation's risk tolerance and security objectives. |

Benefits of Using the PASTA Framework

This framework, being risk-centric, offers numerous benefits for organisations seeking to enhance their security posture through threat modelling.

* The framework is adaptable to unique objectives and helps organisations align with compliance requirements by systematically identifying and addressing security risks while ensuring proper security controls are in place.
* Like the other frameworks, PASTA fosters collaboration between stakeholders, such as developers, architects, and security professionals, promoting a shared understanding of security risks and facilitating communication across the organisation.
* In addition, the PASTA methodology helps organisations meet compliance requirements by systematically identifying and addressing security risks and ensuring that appropriate security controls are in place.
* Lastly, the primary reason to use PASTA is its comprehensive and systematic process, ensuring a thorough analysis of the entire risk landscape. Organisations can proactively address security risks by employing PASTA, tailoring the seven-step methodology to their unique needs, and maintaining a solid security posture.

Application of PASTA Framework

To apply the concepts discussed in this task, let's simulate a scenario wherein we can use the PASTA framework.

Scenario: Your organisation is known for its online banking platform, catering to many users across the Asia Pacific region. To ensure its resiliency to potential threats, you are tasked to conduct a threat modelling exercise using the PASTA framework.

As the leader of this initiative, you will be working with different teams to create a thorough threat modelling plan. Together, you aim to identify potential security threats and protect your online banking platform, ensuring the safety of your customers' information.



| Team<br>                  | Roles and Responsibilities<br>                                                                                                                              |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Development Team          | Responsible for building systems and applications used by the organisation.<br>                                                                             |
| System Architecture Team  | Responsible for designing the overall architecture of the cloud services used by the organisation.<br>                                                      |
| Security Team             | Provide expertise on threats, vulnerabilities, and risk mitigation strategies.<br>                                                                          |
| Business Stakeholder Team | Provides valuable input on critical assets and business processes, and ensures alignment between the initiative and the organisation's strategic goals.<br> |
You must follow the seven-step PASTA process in choosing whom to approach for the information you need for this threat modelling exercise.

##
### ***Task 8 Conclusion***


| framework            | use case applications                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MITRE ATT&<br>CK<br> | Unlike DREAD and STRIDE, which focus more on potential risks and vulnerabilities, ATT&CK provides a practical and hands-on approach by mapping adversary tactics.<br><br> * Assess the effectiveness of existing controls against known attack techniques used by threat actors.                                                                                                                                                                                                   |
| DREAD                | DREAD offers a more numerical and calculated approach to threat analysis than STRIDE or MITRE ATT&CK, making it excellent for clearly prioritising threats.<br><br>*  Qualitatively assess the potential risks associated with specific threats.<br>* Prioritise risk mitigation based on the collective score produced by each DREAD component.                                                                                                                                   |
| STRIDE               | <br><br>While other frameworks like MITRE ATT&CK focus on real-world adversary tactics, STRIDE shines in its structure and methodology, allowing for a systematic review of threats specific to software systems.<br><br>* Analyse and categorise threats in software systems.<br>* Identify potential vulnerabilities in system components based on the six STRIDE threat categories.<br>* Implement appropriate security controls to mitigate specific threat types.             |
| PASTA                | Excellent for aligning threat modelling with business objectives. Unlike other frameworks, PASTA integrates business context, making it a more holistic and adaptable choice for organisations.<br><br>* Conduct risk-centric threat modelling exercises aligned with business objectives.<br>* Prioritise threats based on their potential impact and risk level to the organisation.<br>* Build a flexible methodology that can be adapted to different organisational contexts. |


