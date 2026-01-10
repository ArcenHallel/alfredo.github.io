---
{}
---
https://www.examcompass.com/comptia-security-plus-practice-test-16-exam-sy0-601

https://getcertified.ecpi.edu/wp-content/uploads/2021/06/CompTIA-SecurityPlus601-Acronyms.pdf

https://getcertified.ecpi.edu/wp-content/uploads/2018/02/CompTIA-SecurityPlus-Acronyms.pdf

https://quizlet.com/348921712/sec-certification-14-flash-cards/


#### Your Final Report

|   |   |
|---|---|
|Total marks|30|
|Total Questions|25|
|Questions correctly answered|16|
|Success ratio|64%|
|Marks secured|20|
|Percentage secured|66.67%|

1)  Which of the following encryption schemes is used in WiFi Protected Access 2 (WPA2)?

-    RC4
-    ==AES-CCMP ( Missed)
-    TKIP with RC4 ( Your answer) X
-    AES-GCMP

AES-CCMP is used primarily for securing wireless communications in Wi-Fi networks. It is the encryption protocol employed by WPA2 (Wi-Fi Protected Access 2) and WPA3 (Wi-Fi Protected Access 3) to provide strong data protection and integrity for wireless transmissions.

### Key Features of AES-CCMP

1. **AES (Advanced Encryption Standard)**:
   - **Encryption**: AES is a symmetric encryption algorithm that provides strong encryption using key lengths of 128, 192, or 256 bits. For WPA2 and WPA3, AES-128 is commonly used.
   
2. **CCMP (Counter Mode with Cipher Block Chaining Message Authentication Code Protocol)**:
   - **Counter Mode**: This mode of operation ensures data confidentiality by combining plaintext blocks with a unique counter value using AES encryption.
   - **CBC-MAC (Cipher Block Chaining Message Authentication Code)**: Ensures data integrity and authenticity by producing a MAC (Message Authentication Code) that is checked to verify that data has not been tampered with.

### How AES-CCMP Works in Wi-Fi Networks

1. **Data Encryption**:
   - When data is transmitted over a Wi-Fi network, AES-CCMP encrypts the data frame by frame. Each frame is processed by the AES algorithm in Counter Mode to provide confidentiality.

2. **Data Integrity and Authenticity**:
   - The CBC-MAC mechanism of CCMP generates a MAC for each frame, which is included with the encrypted data. This MAC is used to verify the integrity and authenticity of the data upon receipt, ensuring it has not been altered during transmission.

3. **Key Management**:
   - WPA2 and WPA3 use robust key management protocols, such as the 4-Way Handshake in WPA2 or the Simultaneous Authentication of Equals (SAE) in WPA3, to securely exchange and manage encryption keys used by AES-CCMP.

### Benefits of AES-CCMP

1. **Strong Security**:
   - AES-CCMP provides a high level of security by combining strong encryption (AES) with robust data integrity and authenticity checks (CCMP).

2. **Resistance to Attacks**:
   - The use of AES in Counter Mode and CBC-MAC makes it resistant to many common attacks, including replay attacks and tampering.

3. **Standard Compliance**:
   - AES-CCMP is a standard requirement for WPA2 and WPA3, ensuring wide compatibility and adherence to security best practices in Wi-Fi networks.

### Usage in WPA2 and WPA3

- **WPA2**:
  - AES-CCMP is the default encryption protocol for WPA2, providing the necessary security improvements over the previous WEP (Wired Equivalent Privacy) and TKIP (Temporal Key Integrity Protocol) used in WPA (Wi-Fi Protected Access).

- **WPA3**:
  - AES-CCMP continues to be used in WPA3, along with additional enhancements and protections provided by WPA3, such as better key management and protection against brute-force attacks.

### Conclusion

AES-CCMP is a critical component of modern Wi-Fi security protocols, ensuring that data transmitted over wireless networks is both encrypted and authenticated. By providing strong encryption and robust data integrity mechanisms, AES-CCMP helps protect wireless communications from eavesdropping, tampering, and unauthorized access.

##

2)  For the purpose of encryption, WiFi Protected Access 3 (WPA3) takes advantage of: (Select 2 answers)
 
-   ==AES-GCMP ( Missed) 
-    PSK
-    TKIP with RC4 ( Your answer) X
-    RC4
-    ==AES-CCMP ( Missed)
-    SAE ( Your answer) X

AES-GCMP (Advanced Encryption Standard - Galois/Counter Mode Protocol) is a cryptographic protocol used for ensuring data confidentiality, integrity, and authenticity. It combines the AES encryption algorithm with the Galois/Counter Mode (GCM) of operation. This combination provides both encryption and message integrity in a single pass, making it efficient and secure.

### Key Features of AES-GCMP

1. **AES (Advanced Encryption Standard)**:
   - **Encryption**: AES is a symmetric key encryption algorithm that encrypts data in blocks of 128 bits using keys of 128, 192, or 256 bits. AES is widely recognized for its security and efficiency.

2. **GCM (Galois/Counter Mode)**:
   - **Counter Mode (CTR)**: GCM uses the Counter mode of operation for encryption, which turns AES into a stream cipher. This mode combines plaintext blocks with a counter value and encrypts them using AES.
   - **Galois Mode**: Provides a means to compute a Message Authentication Code (MAC) using the Galois field multiplication, ensuring data integrity and authenticity.

3. **Integrated Authentication**:
   - AES-GCMP provides both encryption and authentication in a single step. The Galois field multiplication creates an authentication tag that verifies the integrity and authenticity of the data.

### How AES-GCMP Works

1. **Data Encryption**:
   - The plaintext data is divided into blocks. Each block is XORed with an encrypted counter value generated by AES in counter mode. This process ensures confidentiality by transforming the plaintext into ciphertext.

2. **Authentication Tag Generation**:
   - As the data is encrypted, GCM also generates an authentication tag using Galois field multiplication. This tag is appended to the ciphertext and used to verify the integrity and authenticity of the data.

3. **Decryption and Verification**:
   - Upon receiving the encrypted data, the recipient decrypts the ciphertext using the same counter values and key. The recipient also verifies the authentication tag to ensure that the data has not been tampered with during transmission.

### Benefits of AES-GCMP

1. **Efficiency**:
   - AES-GCMP is highly efficient because it performs encryption and authentication in parallel, making it faster than other modes that require separate steps for encryption and integrity checks.

2. **Strong Security**:
   - Provides strong encryption (AES) and robust integrity/authentication (GCM), ensuring that data is protected against unauthorized access and tampering.

3. **Wide Adoption**:
   - AES-GCMP is widely adopted in various security protocols and standards, including IPsec, TLS (Transport Layer Security), and WPA3 (Wi-Fi Protected Access 3).

### Usage in Security Protocols

1. **WPA3**:
   - AES-GCMP is used in WPA3, the latest Wi-Fi security standard, providing enhanced security features over its predecessors, WPA2 and WPA. It ensures strong encryption and robust authentication for wireless communications.

2. **TLS (Transport Layer Security)**:
   - TLS 1.2 and TLS 1.3 can use AES-GCMP to secure communications over the internet, ensuring that data exchanged between clients and servers is encrypted and authenticated.

3. **IPsec (Internet Protocol Security)**:
   - AES-GCMP is also used in IPsec, providing secure communication for VPNs and other network security applications.

### Conclusion

AES-GCMP is a powerful and efficient cryptographic protocol that ensures both data confidentiality and integrity. By combining the strong encryption capabilities of AES with the robust authentication and integrity checks of GCM, AES-GCMP provides a high level of security for a wide range of applications, including Wi-Fi networks, secure internet communications, and VPNs. Its efficiency and strong security features make it a preferred choice for modern encryption needs.

##


3)  Which of the EAP methods listed below relies on client-side and server-side certificates for authentication?

-    ==EAP-TLS ( Missed)
-    PEAP
-    EAP-TTLS ( Your answer) X
-    EAP-FAST

EAP-TLS (Extensible Authentication Protocol - Transport Layer Security) is a widely used authentication protocol that leverages the TLS protocol to provide secure communication. It is one of the most secure EAP methods, commonly used in wireless networks and other environments requiring strong security measures.

### Key Features of EAP-TLS

1. **Mutual Authentication**:
   - **Client and Server Authentication**: EAP-TLS provides mutual authentication, where both the client and the server authenticate each other using digital certificates.
   
2. **Strong Security**:
   - **TLS Protocol**: Utilizes the well-established TLS protocol to create a secure tunnel for transmitting authentication credentials, ensuring confidentiality, integrity, and authenticity.
   - **Digital Certificates**: Employs X.509 digital certificates for authentication, which are considered highly secure.

3. **Encryption**:
   - **TLS Encryption**: Ensures that the data exchanged during the authentication process is encrypted, protecting it from eavesdropping and tampering.

4. **Widely Supported**:
   - **Standards Compliance**: EAP-TLS is supported by many network devices and operating systems, making it a popular choice for secure authentication.

### How EAP-TLS Works

1. **Initialization**:
   - The client requests access to the network, and the server responds by initiating the EAP-TLS authentication process.

2. **Certificate Exchange**:
   - **Client Certificate**: The client presents its digital certificate to the server.
   - **Server Certificate**: The server presents its digital certificate to the client.

3. **TLS Handshake**:
   - A TLS handshake is performed to establish a secure encrypted tunnel. During this handshake, the client and server verify each other's certificates, and session keys are generated for encryption.

4. **Mutual Authentication**:
   - Both parties validate the received certificates. If the certificates are trusted and valid, mutual authentication is successfully completed.

5. **Session Establishment**:
   - Upon successful authentication, a secure session is established, allowing the client to access network resources.

### Benefits of EAP-TLS

1. **High Security**:
   - EAP-TLS provides strong security through the use of digital certificates and the TLS protocol, ensuring robust authentication and encryption.

2. **Mutual Authentication**:
   - Both the client and server are authenticated, reducing the risk of man-in-the-middle attacks and ensuring that both parties are legitimate.

3. **Protection Against Various Attacks**:
   - EAP-TLS is resistant to dictionary attacks, replay attacks, and eavesdropping due to the use of strong encryption and mutual authentication.

4. **Standards-Based**:
   - As a standardized protocol, EAP-TLS ensures compatibility and interoperability across different devices and platforms.

### Challenges of EAP-TLS

1. **Certificate Management**:
   - Requires a Public Key Infrastructure (PKI) to issue and manage digital certificates, which can be complex and costly to implement and maintain.

2. **Initial Setup Complexity**:
   - Setting up EAP-TLS involves configuring certificates on both clients and servers, which can be time-consuming and requires a good understanding of PKI.

### Use Cases

1. **Enterprise Wi-Fi Security**:
   - EAP-TLS is commonly used in enterprise environments to secure Wi-Fi access, ensuring that only authenticated users and devices can connect to the network.

2. **VPN Authentication**:
   - Used for authenticating clients connecting to Virtual Private Networks (VPNs), providing secure remote access to network resources.

3. **802.1X Network Access Control**:
   - Employed in wired and wireless 802.1X environments to provide secure network access control, ensuring that only authenticated users can access the network.

### Conclusion

EAP-TLS is a highly secure authentication protocol that provides strong mutual authentication and encryption by leveraging the TLS protocol and digital certificates. Despite the complexities associated with certificate management, its robust security features make it a preferred choice for environments where security is a critical concern, such as enterprise Wi-Fi networks, VPNs, and 802.1X network access control systems.
##

4)  Which of the following answers refers to an IEEE standard that can be implemented in a situation where an Ethernet switch acts as an authenticator for devices that intend to connect to a network through one of its ports?

-    ==IEEE 802.1X ( Missed) 
-    IEEE 802.11ac
-    IEEE 802.1D
-    IEEE 802.11x ( Your answer) X

The IEEE standard that can be implemented in such a situation is **IEEE 802.1X**. This standard defines port-based Network Access Control (NAC), which is used to provide an authentication mechanism for devices attempting to connect to a network.

### Overview of IEEE 802.1X

1. **Role of Components**:
   - **Authenticator**: The Ethernet switch acts as the authenticator, controlling the physical access to the network based on the authentication status of the devices trying to connect.
   - **Supplicant**: The device (e.g., a computer, smartphone, or any network-capable device) trying to connect to the network.
   - **Authentication Server**: Typically a RADIUS (Remote Authentication Dial-In User Service) server that verifies the credentials of the supplicant.

2. **Authentication Process**:
   - **Initiation**: When a device connects to a network port, the switch (authenticator) blocks all traffic except for 802.1X authentication traffic.
   - **Request/Response**: The switch sends an EAP (Extensible Authentication Protocol) request to the device, which responds with its identity.
   - **Forwarding to Authentication Server**: The switch forwards the identity information to the authentication server.
   - **Challenge/Response**: The authentication server sends a challenge back to the device, typically involving credentials like a username and password or a digital certificate.
   - **Authentication Decision**: The device responds, and the authentication server verifies the credentials.
   - **Access Grant/Denial**: If the credentials are valid, the authentication server informs the switch to grant network access. If invalid, access is denied.

3. **Protocols Used**:
   - **EAP (Extensible Authentication Protocol)**: A framework for transporting authentication protocols.
   - **RADIUS (Remote Authentication Dial-In User Service)**: Commonly used to facilitate communication between the authenticator and the authentication server.

### Benefits of IEEE 802.1X

1. **Enhanced Security**:
   - Ensures that only authenticated and authorized devices can access the network.
   - Prevents unauthorized access and potential security breaches.

2. **Flexibility**:
   - Supports various authentication methods, such as passwords, digital certificates, and even biometric data.
   - Can be integrated with existing authentication systems like Active Directory.

3. **Scalability**:
   - Suitable for large networks with numerous devices and users.
   - Centralized authentication management simplifies network administration.

### Common Use Cases

1. **Enterprise Networks**:
   - Ensuring secure access to corporate networks by requiring devices to authenticate before gaining network access.

2. **Educational Institutions**:
   - Providing secure network access to students and faculty, ensuring only authorized users can connect.

3. **Public Wi-Fi Networks**:
   - Offering secure Wi-Fi access in public spaces while preventing unauthorized access.

### Conclusion

IEEE 802.1X is an essential standard for securing network access through authentication, particularly in environments where robust security and access control are necessary. By implementing 802.1X, network administrators can ensure that only authenticated devices are allowed to connect, thereby enhancing the overall security posture of the network.

##

5) Which of the following would be the best solution for securing a ==small== network that lacks an authentication server?

-    ==WPA3-SAE ( Missed)== WPA2 is not the newest, so it would of came down to WPA3 only and since this is a "small" network, WPA3-SAE would be the only choice.
-    WPA2-Enterprise
-    WPA2-PSK ( Your answer) X
-    WPA3-Enterprise

6)  What are the characteristic features of WPA2/WPA3 Enterprise mode? (Select 3 answers)

-    ==Suitable for large corporate networks ( Your answer)
-    IEEE 802.1D
-    Does not require an authentication server
-    ==IEEE 802.1X ( Missed) 
-    ==Suitable for all types of wireless LANs ( Your answer)
-    ==Requires RADIUS authentication server ( Your answer)

 *Enterprise are used manly for big corporations.

7)  A solution that simplifies configuration of new wireless networks by allowing non-technical users to easily configure network security settings and add new devices to an existing network is known as:

-    WPA ( Your answer) X
-    ==WPS ( Missed)
-    WEP
-    WAP



8)  Which of the wireless technologies listed below are deprecated and should not be used due to their known vulnerabilities? (Select 2 answers)

-    ==WPS ( Your answer)
-    WAP ( Your answer) X
-    WPA2
-    WAF
-    ==WEP ( Missed)

9)  Which wireless antenna type provides a 360-degree horizontal signal coverage?

-    Dish antenna ( Your answer) X
-    Unidirectional antenna
-    Yagi antenna
-    ==Omnidirectional antenna ( Missed)== omni is 360-degree

##

*  Which of the following acronyms refers to a client authentication method used in WPA3 Personal mode?  SAE ( Your answer) - simultaneous authentication of equals. new to 802.11

*  Which of the following acronyms refers to a client authentication method used in WPA2 Personal mode?   PSK ( Your answer) pre-shared key. think this is being phased out

*  Which of the following EAP methods offers the highest level of security? - EAP-TLS ( Your answer)

*  Which of the following answers refers to a security solution that allows administrators to block network access for users until they perform required action? Captive portal ( Your answer)
	a customized login page that users must address before connecting to a public (or free) Wi-Fi network*

##

