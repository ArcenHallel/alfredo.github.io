---
{}
---
#### Your Final Report

|   |   |
|---|---|
|Total marks|32|
|Total Questions|25|
|Questions correctly answered|12|
|Success ratio|48%|
|Marks secured|20|
|Percentage secured|62.5%|

1) The lack of entropy in the process of generating cryptographic keys improves the security of cryptographic algorithms.

-    True ( Your answer) X
-    ==False ( Missed)

2)  Which of the following answers refers to a non-proprietary cryptographic network protocol for secure data communication, remote command-line login, remote command execution, and other secure network services?

-    RDP
-    Telnet ( Your answer) X
-    ==SSH ( Missed)
-    RAS

3)  Which of the following protocols allow(s) for secure file transfer? (Select all that apply)

-    ==FTPS ( Your answer)
-    TFTP ( Your answer) X
-    FTP
-    ==SFTP ( Your answer)

4) Secure File Transfer Protocol (SFTP) is an extension to the FTP protocol that adds support for the Transport Layer Security (TLS) and the Secure Sockets Layer (SSL) cryptographic protocols.

-    True ( Your answer) X TLS and SSL is HTTPS based | SFTP is SSH 
-    ==False ( Missed)


5)  FTPS is an extension to the Secure Shell (SSH) protocol and runs by default on port number 22.

*    True ( Your answer) X 
-    ==False ( Missed)


we know that SFTP uses SSH port 22, but FTPS uses TLS 
[Source/](https://www.spiceworks.com/tech/networking/articles/sftp-vs-ftps/)

FTPS: port 990 for control connections and port 989 for data connection 


|                                    | **  <br>Secure shell file transfer protocol (SFTP)**                                                           | **File transfer protocol secure (FTPS)**                                                                      |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Network communication approach** | SFTP builds on secure shell protocol (SSH) and adds on file transfer capabilities.                             | FTPS builds on file transfer protocol (FTP) and adds on a security and encryption layer.                      |
| **Firewall support**               | It uses a single connection through only one port, making it easier to install firewall solutions.             | It needs a secondary data connection, and its use of multiple ports makes it difficult for firewalls to work. |
| **Transfer speeds**                | It involves a high resource overhead and slows down file delivery.                                             | It is simple, straightforward, and lean, making it several times faster.                                      |
| **Binary and ASCII**               | It supports only binary transmission, and users cannot choose between different modes.                         | It supports both binary and ASCII transmissions, making it easier to maintain logs.                           |
| **.NET compatibility**             | Developers cannot build .NET programs with SFTP functionalities, as compatibility is missing.                  | .NET includes a number of commands to support file uploads in FTPS modes.                                     |
| **Authentication mechanism**       | It uses out-of-band authentication and does not need signed certificates, as the data is inherently encrypted. | The FTP server must mandatorily provide a public-key certificate to sign off on the authentication.           |
| **Usage commands**                 | It supports a long list of commands with granular controls, such as defining file permissions.                 | It supports a relatively limited list of commands, with less control over remote files and directories.       |
| **Adoption**                       | It is widely adopted, and most servers and cloud storage solutions support SFTP.                               | It is built on FTP, which is gradually being phased out for HTTPS and other protocols.                        |



6)  Which version(s) of the SNMP protocol offer(s) authentication based on community strings sent in an unencrypted form? (Select all that apply)

-    ==SNMPv1 ( Your answer)
-    ==SNMPv2 ( Your answer)
-    SNMPv3 ( Your answer) X
-    SNMPv4

7)  Which of the protocols listed below enables remote access to another computer on the network via web browser?

-    RDP
-    ==HTTPS ( Missed)
-    SSH
-    VNC ( Your answer) X

8)  Which part of the IPsec protocol suite provides authentication and integrity?

-    CRC
-    ==AH ( Missed)== AH Authentication Header
-    SIEM
-    AES ( Your answer) X

9)  Which of the following answers refer to IMAP? (Select 2 answers)

-    ==Offers improved functionality in comparison to POP3 ( Missed)
-    ==Serves the same function as POP3 ( Missed)
-    Enables sending email messages from client devices ( Your answer) X
-    Offers less functions than POP3
-    Enables email exchange between mail servers ( Your answer) X

10) Which of the answers listed below refers to a deprecated TLS-based method for securing SMTP?

-    IMAPS
-    STARTTLS ( Your answer) X 
-    POP3S
-    ==SMTPS ( Missed== this was replaced with STARTTLS

11) Which of the following answers refer(s) to POP3S encrypted communication? (Select all that apply)

-    TCP port 993
-    ==Secure Sockets Layer (SSL) ( Missed)
-    ==TCP port 995 ( Your answer)
-    ==Transport Layer Security (TLS) ( Your answer)
-    TCP port 110

12)  What are the characteristic features of the secure version of IMAP? (Select all that apply)

-    TCP port 143
-    ==Secure Sockets Layer (SSL) ( Missed)
-    ==TCP port 993 ( Your answer)
-    ==Transport Layer Security (TLS) ( Your answer)
-    TCP port 995

13)  Which of the following is a secure implementation of a protocol used for synchronizing clocks over a computer network?

-    ==NTPsec ( Missed)
-    SNMPv3
-    SRTP
-    IPsec ( Your answer) X

## NTPsec
NTPsec (Network Time Protocol Secure) is a secure, hardened, and improved implementation of the Network Time Protocol (NTP). NTP is used to synchronize the clocks of computers over a network, ensuring accurate timekeeping across systems. NTPsec was developed to address security vulnerabilities and performance issues in the original NTP implementation.

### Key Features and Enhancements of NTPsec

1. **Security Improvements**:
   - **Code Audit and Cleanup**: NTPsec underwent a comprehensive code audit and cleanup, removing legacy code and reducing the overall code base by more than 75%. This reduction helps minimize the attack surface and potential security vulnerabilities.
   - **Mitigations for Known Vulnerabilities**: NTPsec addresses many security issues found in the original NTP, including buffer overflows, integer overflows, and other vulnerabilities that could be exploited by attackers.
   - **Modern Cryptographic Practices**: NTPsec incorporates modern cryptographic practices and libraries, improving the security of time synchronization.

2. **Performance Enhancements**:
   - **Efficiency Improvements**: The streamlined code base and optimized algorithms in NTPsec result in better performance and lower resource consumption compared to the original NTP implementation.
   - **Improved Responsiveness**: NTPsec enhances the responsiveness of time synchronization, making it more suitable for environments requiring precise timekeeping.

3. **Simplified Configuration and Management**:
   - **Easier Configuration**: NTPsec simplifies the configuration process, making it more user-friendly and reducing the likelihood of configuration errors.
   - **Better Documentation**: The project provides comprehensive documentation to help users understand and deploy NTPsec effectively.

4. **Protocol and Compatibility**:
   - **Backward Compatibility**: NTPsec maintains compatibility with the NTP protocol, allowing it to work with existing NTP clients and servers.
   - **Support for NTS (Network Time Security)**: NTPsec supports NTS, an extension to NTP that provides cryptographic authentication and encryption for time synchronization, enhancing security in environments where secure time synchronization is critical.

### Applications and Use Cases

NTPsec is used in various applications where accurate and secure time synchronization is essential, including:

- **Data Centers and Cloud Services**: Ensuring synchronized time across servers to support logging, monitoring, and coordination of distributed systems.
- **Financial Services**: Providing precise timekeeping for transactions and compliance with regulations requiring accurate timestamps.
- **Telecommunications**: Synchronizing time across network devices to ensure proper functioning of communication protocols and services.
- **Industrial Control Systems**: Maintaining accurate time in critical infrastructure and industrial control systems to ensure coordinated operations and event logging.

### Conclusion

NTPsec represents a significant improvement over the original NTP implementation by focusing on security, performance, and ease of use. Its enhancements make it a suitable choice for environments where secure and accurate time synchronization is paramount. By addressing the vulnerabilities and inefficiencies of its predecessor, NTPsec helps ensure the reliability and security of time synchronization in modern networks.
##


 * Which protocol enables secure, real-time delivery of audio and video over an IP network? SRTP Secure Real-time Transport Protocol

 * Of the three existing versions of the Simple Network Management Protocol (SNMP), versions 1 and 2 (SNMPv1 and SNMPv2) offer authentication based on community strings sent in an unencrypted form (in cleartext). SNMPv3 provides packet encryption, authentication, and hashing mechanisms that allow for checking whether data has changed in transit (i.e. validation of data integrity).    True ( Your answer)

 * Which part of IPsec provides authentication, integrity, and confidentiality?  ESP ( Your answer) ESP Encapsulating Security Payload