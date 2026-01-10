---
{}
---
#### Your Final Report

|                              |        |
| ---------------------------- | ------ |
| Total marks                  | 35     |
| Total Questions              | 25     |
| Questions correctly answered | 9      |
| Success ratio                | 36%    |
| Marks secured                | 18     |
| Percentage secured           | 51.43% |
 
 1) Which of the following enables the exchange of information between computer programs?

-    ==API ( Missed)== micro services that gets resources from other services
-    UI
-    Device drivers ( Your answer) X
-    SDK 

 Your answer to this question is incorrect or incomplete.

2)  A situation in which an application fails to properly release memory allocated to it or continually requests more memory than required is known as:

-    ==Memory leak ( Missed)==
-    Buffer overflow
-    Race condition ( Your answer) X
-    Integer overflow

 Your answer to this question is incorrect or incomplete.

3)  Which of the following alters the external behavior of an application and at the same time does not introduce any changes to the application's code?

-    ==Shimming ( Missed)== repurpose device
-    Refactoring ( Your answer) X 
-    API call
-    Sideloading

 Your answer to this question is incorrect or incomplete. 

"Shimming" refers to a technique used in the context of software or hardware to provide compatibility or support for older or different versions of an interface, protocol, or application programming interface (API). It involves inserting an additional layer of code or hardware between two components to bridge compatibility gaps.


4)  The practice of modifying an application's code without changing its external behavior is referred to as:

-    API call
-    ==Refactoring ( Missed)== repurpose application
-    Sideloading ( Your answer) X
-    Shimming

 Your answer to this question is incorrect or incomplete

 5) Which of the following terms refer to software/hardware driver manipulation techniques? (Select 2 answers)

-    Prepending ( Your answer) X
-    Fuzz testing
-    ==Refactoring ( Missed)==
-    ==Shimming ( Missed)==
-    Sideloading ( Your answer) X

 Your answer to this question is incorrect or incomplete.

6) Gaining unauthorized access to a Bluetooth device is referred to as:

-    Phishing
-    Bluejacking ( Your answer) X
-    Smishing
-   ==Bluesnarfing ( Missed)== access to device

 Your answer to this question is incorrect or incomplete.

 7) The practice of sending unsolicited messages over Bluetooth is known as:

-    SPIM
-    ==Bluejacking ( Missed)== sends unsolicited messages to bluetooth
-    Vishing
-   Bluesnarfing ( Your answer)

 Your answer to this question is incorrect or incomplete.

* ***I'm getting bluesnarfing and bluejackeing mixed up

8)  A wireless disassociation attack is a type of: (Select 2 answers)

-    Cryptographic attack
-    Downgrade attack ( Your answer) X
-    ==Deauthentication attack ( Your answer)== if deauthenticated, they have lose authentication to service, implying disassociation.
-    Brute-force attack
-    ==Denial-of-Service (DoS) attack ( Missed)== your are denying the service by disassociating the user from the wifi 

 Your answer to this question is incorrect or incomplete.

9)  A wireless jamming attack is a type of:

-    Cryptographic attack ( Your answer) X
-    ==Denial-of-Service (DoS) attack ( Missed== if you jam the wifi, no one can access it 
-    Brute-force attack
-    Downgrade attack

 Your answer to this question is incorrect or incomplete.

10)  A type of identification badge that can be held within a certain distance of a reader device to authenticate its holder is called:

-    Smart card ( Your answer) X
-    ID badge
-    Soft token
-    ==RFID badge ( Missed)== gate opener, door opener, hotel room opener, it doesnt have any information like smart cards, the data only allows authentication 

 Your answer to this question is incorrect or incomplete.

11)  RFID is vulnerable to:

-    Spoofing ( Your answer) X
-    Eavesdropping
-    Data interception
-    Replay attacks
-    Denial-of-Service (DoS) attacks
-    ==All of the above ( Missed)== 

 Your answer to this question is incorrect or incomplete.

 12) NFC is vulnerable to:

-    Data interception ( Your answer) X
-    Replay attacks
-    Denial-of-Service (DoS) attacks
-    ==All of the above ( Missed)

 Your answer to this question is incorrect or incomplete.

13) Which of the following provide randomization during encryption process? (Select 2 answers)

-    ==Salting ( Your answer)
-    Rainbow tables
-    Obfuscation ( Your answer) X is encryption but doesn't provide randomization
-    ==Initialization Vector (IV) ( Missed)== 
-    Shimming

 Your answer to this question is incorrect or incomplete.

An Initialization Vector (IV) is a crucial component in encryption algorithms, especially in block cipher modes of operation like Cipher Block Chaining (CBC) or Cipher Feedback (CFB). Its primary purpose is to introduce randomness and prevent patterns from emerging in encrypted data.

Here's what an Initialization Vector (IV) does:

1. **==Randomnes==s**: The IV adds randomness to the encryption process. Without an IV, encrypting the same plaintext with the same key would always result in the same ciphertext. This predictability could potentially lead to security vulnerabilities, especially when encrypting similar or repetitive data. By using a unique IV for each encryption operation, even if the same plaintext is encrypted multiple times with the same key, the resulting ciphertexts will be different.
    
2. **==Preventing Patterns==**: When encrypting data in blocks (e.g., 128 bits in AES), an IV ensures that identical blocks of plaintext do not encrypt to identical blocks of ciphertext. Without an IV or with a predictable IV, identical plaintext blocks would produce identical ciphertext blocks, which could reveal patterns in the data and weaken the encryption.
    
3. **Security**: IVs play a crucial role in ensuring the security of encrypted communication and data storage. By introducing randomness and preventing patterns, IVs help to thwart certain cryptographic attacks, such as known-plaintext attacks and chosen-plaintext attacks, which rely on detecting patterns in encrypted data.
    
4. **Size and Requirements**: The size of the IV depends on the encryption algorithm and the specific mode of operation. For example, in AES encryption with CBC mode, the IV size is typically the same as the block size (e.g., 128 bits for AES). It's essential that the IV be unique for each encryption operation but doesn't necessarily need to be secret. Often, IVs are generated randomly or derived from nonces (number used once) or other sources of randomness.
    

==In summary, an Initialization Vector (IV) enhances the security of encryption algorithms by adding randomness and preventing patterns in encrypted data. It ensures that even when encrypting similar or repetitive data with the same key, the resulting ciphertexts remain unique, thereby strengthening the confidentiality of the encrypted information.==


14)  Which of the following statements can be used to describe the characteristics of an on-path attack? (Select all that apply)

-    ==An on-path attack is also known as MITM attack ( Your answer)
-    ==In an on-path attack, attackers place themselves on the communication route between two devices== ( Missed)
-    ==In an on-path attack, attackers intercept or modify packets sent between two communicating devices ( Your answer)
-    In an on-path attack, attackers do not have access to packets exchanged during the communication between two devices
-    In an on-path attack, attackers generate forged packets and inject them in the network

 Your answer to this question is incorrect or incomplete.

15)  An attacker managed to associate his/her MAC address with the IP address of the default gateway. In result, a targeted host is sending network traffic to the attacker's IP address instead of the IP address of the default gateway. Based on the given info, which type of attack is taking place in this scenario?

-    ==ARP poisoning ( Missed)== address resolution protocol | assoicated with MAC
-    Replay attack
-    Cross-site request forgery
-    DNS poisoning ( Your answer) X domain name system | associated with domains

 Your answer to this question is incorrect or incomplete.

16) Which of the following fall(s) into the category of Layer 2 attacks? (Select all that apply)

-    ==MAC cloning ( Your answer)
-    ==ARP poisoning ( Missed)
-    ==MAC flooding ( Your answer)
-    DNS poisoning
-    ==MAC spoofing ( Your answer)==
Layer 2 is Data Link Layer 

 Your answer to this question is incorrect or incomplete.

ARP poisoning is indeed a layer 2 (data link layer) attack.

ARP (Address Resolution Protocol) operates at the data link layer (Layer 2) of the OSI model and is used to map IP addresses to MAC addresses on a local network. ARP poisoning, also known as ARP spoofing, is a type of attack where an attacker sends falsified ARP messages over a local area network. These messages associate the attacker's MAC address with the IP address of a legitimate network device, such as the default gateway or another host on the network.

By doing so, the attacker can intercept, modify, or redirect traffic intended for the legitimate device. ARP poisoning attacks can be used for various malicious purposes, such as eavesdropping on network communications, performing man-in-the-middle attacks, or conducting denial-of-service attacks.

Since ARP operates at Layer 2 of the OSI model, ARP poisoning attacks occur within the local network segment and do not typically traverse routers or cross subnet boundaries. This makes them particularly effective in local network environments where devices share the same broadcast domain.

To defend against ARP poisoning attacks, network administrators can implement various countermeasures, such as ARP spoofing detection tools, static ARP entries, or port security features on network switches. Additionally, using cryptographic protocols like HTTPS and VPNs can help protect sensitive data from being intercepted or manipulated by attackers leveraging ARP poisoning techniques.

