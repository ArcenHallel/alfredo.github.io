---
{}
---
#### Your Final Report

|   |   |
|---|---|
|Total marks|30|
|Total Questions|25|
|Questions correctly answered|18|
|Success ratio|72%|
|Marks secured|25|
|Percentage secured|83.33%|

 1) Which of the following answers refer to vulnerability databases? (Select 2 answers)

-    DBA ( Your answer) database administator?
-    ==CVE ( Your answer)
-    DBaaS (database as a service)
-    ==NVD ( Missed)==  **National Vulnerability Database** (NVD)
-    AIS (automated indicator sharing)

 * **need to pay more attention to the questions, i should of known this.**


## IOC
==IoC stands for "Indicator of Compromise."== It refers to any piece of evidence or observable behavior that suggests an information system has been compromised by an unauthorized or malicious actor. IoCs are used by cybersecurity professionals to identify, detect, and respond to security incidents.

Examples of IoCs include:

1. Unusual network traffic patterns, such as unexpected spikes in data transmission or communication with suspicious IP addresses.
2. Anomalous system behavior, such as unauthorized access attempts, privilege escalations, or unusual file modifications.
3. Indications of malware presence, such as the presence of suspicious files, registry changes, or unusual process activity.
4. Suspicious email attachments or URLs identified in phishing campaigns.
5. Alerts triggered by intrusion detection or prevention systems (IDS/IPS), antivirus software, or security information and event management (SIEM) systems.
6. Information obtained from threat intelligence feeds, including known malicious IP addresses, domains, file hashes, or other indicators.

By monitoring for and analyzing IoCs, cybersecurity teams can quickly identify and respond to security incidents, mitigate the impact of breaches, and prevent further compromise of systems and data.
##

 2) Which of the following terms refers to a US government initiative for real-time sharing of cyber threat indicators?

-    NVD (national vulnerability database)
-    ==AIS ( Missed)== automated indicator of sharing [source](https://www.cisa.gov/topics/cyber-threats-and-advisories/information-sharing/automated-indicator-sharing-ais)
-    TTP (tactic, techniques and procedures)
-    CVSS ( Your answer) X the grading system on cves

==Automated Indicator Sharing (AIS) is a service the Cybersecurity and Infrastructure Security Agency (CISA)==provides to enable real-time exchange of machine-readable cyber threat indicators and defensive measures between public and private-sector organizations. AIS helps to protect the participants of the service and ultimately reduce the prevalence of cyberattacks.

3) What is STIX?

-    Vulnerability database (NVD or other db)
-    ==Common language for describing cyber threat information ( Missed)
-    US government initiative for real-time sharing of cyber threat indicators (this is AIS )
-    Transport mechanism for cyber threat information ( Your answer) X (this is TAXII, or trusted automated eXchange of intelligence information)
## STIX
==STIX stands for "Structured Threat Information eXpression.== It is a standardized language and format for describing cyber threat intelligence (CTI) in a structured and machine-readable manner. STIX was developed by the MITRE Corporation as part of the OASIS (Organization for the Advancement of Structured Information Standards) international consortium.

STIX enables organizations to share, analyze, and communicate threat intelligence more effectively by providing a common framework for representing and exchanging information about cyber threats, indicators of compromise (IoCs), tactics, techniques, and procedures (TTPs), and other relevant contextual data.

Key components of STIX include:

1. **STIX Core**: The core data model of STIX defines standardized objects and properties for representing cyber threat intelligence, including indicators, observables, threat actors, intrusion sets, malware, tools, and vulnerabilities.

2. **STIX Patterning**: STIX includes a pattern expression language that allows analysts to create complex queries and expressions for describing and matching patterns of behavior, characteristics, or attributes associated with cyber threats.

3. **STIX Vocabulary**: STIX provides a standardized vocabulary for describing entities and relationships within the cyber threat landscape, ensuring consistency and interoperability across different threat intelligence sources and platforms.

4. **STIX Cyber Observables**: STIX defines a set of cyber observables for representing technical indicators, artifacts, and characteristics associated with cyber threats, such as IP addresses, domain names, file hashes, network traffic patterns, and malware behaviors.

5. **STIX JSON and XML Representations**: STIX data can be serialized and exchanged in both JSON (JavaScript Object Notation) and XML (eXtensible Markup Language) formats, making it compatible with a wide range of tools, platforms, and systems.

==STIX== is widely used by cybersecurity organizations, threat intelligence vendors, government agencies, and security researchers to improve collaboration, information sharing, and situational awareness in the fight against cyber threats. It is often used in conjunction with other standards such as ==TAXII (Trusted Automated eXchange of Indicator Information)== for exchanging threat intelligence data between different organizations and platforms.
##


 4) A type of formal document that describes the specifications for a particular technology is known as:

-    RFQ ( Your answer) X  (request for quota?) document that gathers comprehensive pricing for specific good or service?
-    ==RFC ( Missed)== RFC Request for Comments
-    RFI (remote file inclusion) an attack on vulnerabilities in web application that dynamically reference external scripts
-    RFP (request of proposal) is tied with managed security service provider(MSSP)


## What is a Request for Comments (RFC)?

==A Request for Comments (RFC) is a formal document developed by a committee of the Internet Engineering Task Force (IETF) and subsequently reviewed by interested parties.== Memos in the RFC document series contain technical and organizational notes about the Internet. They cover many aspects of computer networking and email, including protocols, procedures, programs, and concepts.

The term ==Tactics, Techniques and Procedures (TTP)== describes the behavior of a [threat actor](https://www.splunk.com/en_us/blog/learn/threat-actors.html) and a structured framework for executing a cyberattack

Let’s define each part of the TTP triangle:

- ==**Tactics:**== The high-level description of the behavior and strategy of a threat actor. The tactic includes a set of behaviors and actions employed by the adversary to achieve a specific objective.
- ==**Techniques:**== These are the non-specific guidelines and intermediate methods that describe how a tactic action can be realized.
- ==**Procedures:**== These refer to the sequence of actions performed using a technique to execute on an attack tactic. The procedure involves detailed descriptions on the tailored activities that enable a threat actor to successfully achieve their targets.
##


 5) Vulnerability scanning: (Select all that apply)

-    ==Identifies lack of security controls ( Your answer)
-    Actively tests security controls ( Your answer) X the scan is passive and not intrusive 
-    ==Identifies common misconfigurations ( Your answer)
-    Exploits vulnerabilities
-    ==Passively tests security controls ( Your answer)

 
* ***in a "Vulnerability scan" you passively test security controls
* ***in a penetration test you actively test security controls 
thats the only different between the 2.

 6) Which type of server is used for collecting diagnostic and monitoring data from networked devices?

-    Proxy server ( Your answer) X forward and can monitor 
-    UC server
-   ==Syslog server ( Missed)== syslog is primarly used to collect diagnostic and monitor 
-    ICS server


 A security solution designed to detect anomalies in the log and event data collected from multiple network devices is called:  

Correct answer
	SIEM ( Your answer) Security information and event management

 Which of the following tools enables automated response to security incidents?
   
	SOAR ( Your answer) **security orchestration, automation, and response**

 7) Penetration testing: (Select all that apply)

-    Bypasses security controls ( Your answer)
-    Only identifies lack of security controls
-    Actively tests security controls ( Your answer)
-    Exploits vulnerabilities ( Your answer)
-    Passively tests security controls ( Your answer) X

"in penetration testing" you don't passively test. 