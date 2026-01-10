---
{}
---
#### Your Final Report

|   |   |
|---|---|
|Total marks|31|
|Total Questions|25|
|Questions correctly answered|16|
|Success ratio|64%|
|Marks secured|22|
|Percentage secured|70.97%|

1)  A security feature of a network switch that provides countermeasures against rogue DHCP servers is called:

-    DHCP scope
-    DHCP reservation ( Your answer) X
-    ==DHCP snooping ( Missed)
-    DHCP relay agent

DHCP snooping is a collection of techniques used to improve the security of a DHCP infrastructure in computer networking. It can be configured on LAN switches to block rogue DHCP servers and remove malicious or malformed DHCP traffic. DHCP snooping acts as a firewall between untrusted hosts and trusted DHCP servers by performing the following activities:

2)  Which of the following answers refers to a firewall type that improves upon first- and second-generation firewalls by offering additional features, such as more in-depth inspection of network traffic and application-level inspection?

-    IDS
-    Packet filter
-    ==NGFW ( Missed)== new generation filewall
-    Stateful firewall ( Your answer) X

3)  Which of the following is a common firewall type used for protecting a single computer? (Select 2 answers)

-    Host-based firewall ( Your answer) X
-    ==Software firewall ( Missed)== one license, for one device 
-    Network-based firewall
-    Hardware firewall

4)  Which firewall would provide the best protection for an ingress/egress point of a corporate network? (Select 2 answers)

-    ==Hardware firewall ( Missed) 
-    ==Network-based firewall ( Your answer)
-    Software firewall ( one license for one device )
-    Host-based firewall (we are talking about corporate networks; this does not provide the best for that )

5)  The term "Static code analysis" refers to the process of discovering application run-time errors.

-    True ( Your answer) X
-    ==False ( Missed)== static means it does not run so we cant find run time errors

Static code analysis, also known as source code analysis or static application security testing (SAST), is a software verification technique that examines source code for quality, reliability, and security without executing it. It analyzes the code's structure, syntax, and dependencies to identify issues, potential problems, code smells, and violations of coding standards

6)  A dynamic code analysis allows for detecting application flaws without the need for actual execution of the application code.

-    True ( Your answer) X 
-    ==False ( Missed)== you have to run the code in dynamic code analysis 

dynamic code executes the command. the statement above is stating that it does not have to run to be tested, which is false.

7)  Which of the following terms refers to an automated or manual code review process aimed at discovering logic and syntax errors in the application's source code?

-    Input validation
-    Dynamic code analysis ( Your answer) X 
-    Fuzzing
-    ==Static code analysis ( Missed)== the question is not stating the code has to be executed, meaning the code review is static. it even says automated or manual code review 

8)  Which of the following answers refers to a data storage device equipped with hardware-level encryption functionality?

-    SSP
-    SEH
-    SDN ( Your answer) X Storage defined network
-    ==SED ( Missed)== SED Self-Encrypting Drives
## Overview of Self-Encrypting Drives (SEDs)

1. **Hardware-Based Encryption**:
   - **Built-In Encryption Engine**: SEDs have a built-in encryption engine that performs real-time encryption and decryption of data as it is written to or read from the disk. This encryption is transparent to the user and operating system.
   - **AES Encryption**: Most SEDs use the Advanced Encryption Standard (AES) for encrypting data, typically with 256-bit keys, ensuring strong encryption.

2. **Key Management**:
   - **Embedded Encryption Keys**: The encryption keys are generated and stored within the drive itself, which prevents the keys from being exposed to the host system or external software.
   - **Key Management**: SEDs often support secure key management protocols, allowing for secure key generation, storage, and deletion.

3. **Performance**:
   - **Minimal Performance Overhead**: Since encryption and decryption are handled by the drive's hardware, there is minimal impact on the drive's performance. This allows SEDs to maintain high data transfer rates.

4. **Security Features**:
   - **Automatic Encryption**: All data written to the drive is automatically encrypted without user intervention.
   - **Instant Secure Erase**: SEDs can perform an instant secure erase by deleting the encryption keys, rendering all data on the drive unreadable without having to overwrite the entire disk.
   - **Tamper Resistance**: SEDs are designed to resist tampering and unauthorized access to encryption keys.

5. **Ease of Use**:
   - **Transparent Operation**: SEDs operate transparently, meaning users do not need to manage encryption processes manually. The encryption is always on, providing seamless security.

6. **Compliance and Standards**:
   - **Industry Standards**: SEDs often comply with industry standards such as the Trusted Computing Group's (TCG) Opal Storage Specification, ensuring interoperability and security best practices.

## Applications and Use Cases

- **Enterprise Data Protection**: SEDs are widely used in enterprises to protect sensitive data on laptops, desktops, and servers, helping to comply with data protection regulations and prevent data breaches.
- **Mobile Devices**: For laptops and mobile devices that are frequently transported, SEDs provide robust security against data theft in case the device is lost or stolen.
- **Data Centers**: In data centers, SEDs help protect data at rest, ensuring that data on decommissioned drives cannot be recovered by unauthorized parties.
- **Regulatory Compliance**: Organizations subject to regulations such as GDPR, HIPAA, and PCI-DSS use SEDs to ensure that sensitive data is encrypted and protected in compliance with legal requirements.

## Conclusion

==Self-Encrypting Drives (SEDs) provide a hardware-based solution for full-disk encryption, offering robust security, minimal performance impact, and ease of use.== By integrating encryption directly into the drive hardware, SEDs ensure that all data is securely encrypted, protecting against unauthorized access and simplifying data protection for users and organizations.
##

9)  A software technology designed to provide confidentiality for an entire data storage device is known as:

-    AES this is algorithm encryption
-    ==FDE ( Missed)== FDE Full Disk Encryption
-    EFS another encryption Encrypted file system
-    HSM ( Your answer) X *hardware* security moduel 
 
Full Disk Encryption (FDE) can be implemented using both software-based and hardware-based approaches. 
## Software-Based Full Disk Encryption

1. **Definition**:
   - Software-based FDE uses encryption software to encrypt the entire contents of a disk, including the operating system, applications, and user data. 

2. **Examples**:
   - **BitLocker**: Available in certain editions of Microsoft Windows, BitLocker encrypts the entire disk and provides features such as Trusted Platform Module (TPM) integration for secure key storage.
   - **FileVault**: Apple's FileVault provides FDE for macOS, encrypting the entire disk using XTS-AES-128 encryption with a 256-bit key.
   - **VeraCrypt**: An open-source encryption software that can perform FDE on Windows, macOS, and Linux systems.

3. **How It Works**:
   - **Installation**: Encryption software is installed on the device.
   - **Encryption Process**: The software encrypts all data on the disk sector by sector.
   - **Key Management**: Encryption keys are typically stored on the disk or in secure hardware like TPM or USB tokens, and they are protected by a user password or passphrase.
   - **Boot Process**: During the boot process, users may need to enter a password or provide a hardware token to decrypt the disk and boot the operating system.

4. **Advantages**:
   - **Flexibility**: Can be used on a wide range of hardware and does not require specialized hardware.
   - **Compatibility**: Works with existing systems without the need for hardware upgrades.

5. **Disadvantages**:
   - **Performance Overhead**: Software-based encryption can introduce some performance overhead, as the CPU must handle encryption and decryption processes.
   - **Dependency on OS**: The encryption process may be dependent on the operating system, and certain features may not be available across different platforms.

## Hardware-Based Full Disk Encryption

1. **Definition**:
   - Hardware-based FDE, such as Self-Encrypting Drives (SEDs), integrates encryption directly into the disk hardware, providing automatic encryption of all data written to the disk.

2. **How It Works**:
   - **Built-In Encryption Engine**: The drive contains a dedicated encryption engine that handles all encryption and decryption operations in real time.
   - **Key Storage**: Encryption keys are stored within the hardware of the drive and are never exposed to the operating system.
   - **Authentication**: Users authenticate themselves (e.g., by entering a password) before the drive will decrypt data, typically during the boot process.

3. **Advantages**:
   - **Performance**: Minimal performance impact since encryption is handled by dedicated hardware.
   - **Security**: Keys are stored securely within the drive, reducing the risk of key exposure.
   - **Ease of Use**: Transparent to users, with no need for additional software installation or management.

4. **Disadvantages**:
   - **Cost**: SEDs can be more expensive than standard drives.
   - **Hardware Dependency**: Requires purchasing specific hardware, which may not be compatible with all systems.

## Conclusion

Full Disk Encryption (FDE) can be implemented using either software-based or hardware-based solutions. Software-based FDE provides flexibility and compatibility across different hardware and operating systems but may introduce performance overhead. Hardware-based FDE, such as Self-Encrypting Drives (SEDs), offers better performance and security by integrating encryption into the drive hardware but requires compatible hardware and may be more expensive. The choice between software-based and hardware-based FDE depends on specific use cases, budget, and security requirements.
##



*  Which of the following answers refers to an endpoint security solution that provides the capability for detection, analysis, response, and real-time monitoring of cyber threats?  Which of the following answers refers to an endpoint security solution that provides the capability for detection, analysis, response, and real-time monitoring of cyber threats? EDR Endpoint Detection and Response

*  The term "Measured Boot" refers to a security mechanism first introduced by Microsoft in Windows 8. Measured Boot checks system startup components and stores the resulting boot configuration log in the Trusted Platform Module (TPM). The log is then sent for remote attestation to a trusted server on the network to verify the integrity of the Windows startup process. Measured Boot allows for neutralization of hard-to-detect malware and rootkits which are run before the OS.  True ( Your answer)
*  Which of the following answers refers to a specification for SEDs?  Opal ( Your answer)

*many Self-Encrypting Drives (SEDs) use the Opal specification developed by the Trusted Computing Group (TCG). The Opal specification is a set of standards for implementing hardware-based encryption in storage devices, ensuring interoperability and consistent security features across different manufacturers.