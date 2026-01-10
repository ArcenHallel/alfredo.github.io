---
{}
---
where i left off
https://getcertified.ecpi.edu/wp-content/uploads/2018/02/CompTIA-SecurityPlus-Acronyms.pdf
https://getcertified.ecpi.edu/wp-content/uploads/2021/06/CompTIA-SecurityPlus601-Acronyms.pdf
https://www.examcompass.com/comptia-security-plus-practice-test-12-exam-sy0-601

#### Your Final Report

|                              |        |
| ---------------------------- | ------ |
| Total marks                  | 32     |
| Total Questions              | 25     |
| Questions correctly answered | 15     |
| Success ratio                | 60%    |
| Marks secured                | 22     |
| Percentage secured           | 68.75% |

1)  What are the characteristic features of Elliptic Curve Cryptography (ECC)? (Select 3 answers)

-    ==Asymmetric encryption ( Your answer)
-    ==Low processing power requirements ( Missed)
-    ==Suitable for small wireless devices ( Your answer)
-    High processing power requirements ( Your answer) x
-    Symmetric encryption
-    Not suitable for small wireless devices

  Which of the following answers refers to a solution designed to strengthen the security of session keys?

-    ECB
-    ==PFS ( Your answer)== PFS Perfect Forward Secrecy
Perfect forward secrecy (PFS) is a type of encryption that frequently and automatically changes the keys used to encrypt and decrypt information.
-    EFS
-    PFX

 ***got it right but dont remember what PFS stands for 

2)  According to predictions, the most future-proof cryptographic solution should be:

-    Quantum cryptography ( Your answer) X this is now but after post-quantum will be better
-    Symmetric-key cryptography
-    ==Post-quantum cryptography ( Missed)==
-    Asymmetric-key cryptography
-    Public-key cryptography

3)  What are the characteristic features of a session key? (Select 2 answers)

-    ==Used during a single session ( Missed) 
-    Asymmetric key
-    Reused during multiple sessions ( Your answer) X
-    ==Symmetric key ( Your answer)==

A session key is a single-use symmetric key used for encrypting all messages in one communication session.

 Your answer to this question is incorrect or incomplete.

4)  Which of the following block cipher modes is the simplest/weakest and therefore not recommended for use?

-    CBC ( Your answer) X
-    GCM
-    ==ECB ( Missed)== 
-    CTR

## ECB
ECB (Electronic Codebook) is a block cipher mode of operation used in symmetric-key encryption algorithms. In ECB mode, each block of plaintext is encrypted independently using the same encryption key.

Here's how ECB mode works:

1. **Dividing into Blocks**: The plaintext is divided into fixed-size blocks (e.g., 64 or 128 bits) to be processed by the encryption algorithm.
    
2. **Encryption**: Each plaintext block is encrypted separately using the encryption algorithm and the shared secret key. The same key is used for encrypting all blocks.
    
3. **Output**: The resulting ciphertext blocks are concatenated to form the complete ciphertext.
    

While ECB mode is simple and easy to implement, it has several notable weaknesses:

1. **Deterministic Encryption**: Because each plaintext block is encrypted independently with the same key, identical plaintext blocks will produce identical ciphertext blocks. This means that patterns in the plaintext may be preserved in the ciphertext, which can leak information and is vulnerable to certain attacks, such as frequency analysis.
    
2. **Lack of Security**: ECB mode does not provide semantic security, meaning that an attacker can potentially infer information about the plaintext by analyzing patterns in the ciphertext. This makes it unsuitable for many security-critical applications.
    
3. **No Integrity Protection**: ECB mode does not provide integrity protection for the encrypted data. An attacker can modify the ciphertext blocks without detection, leading to potential data integrity violations.
    

==Due to these weaknesses, ECB mode is generally not recommended for use in cryptographic applications where confidentiality and security are paramount== Instead, more secure modes of operation, such as CBC (Cipher Block Chaining), CTR (Counter), or GCM (Galois/Counter Mode), are preferred. These modes provide better security properties, such as diffusion, confusion, and integrity protection, making them more suitable for secure encryption. 
##

5)   Which of the block cipher modes listed below provides both data integrity and confidentiality?

-    CBC
-    ==GCM ( Missed) 
-    ECB ( Your answer) X
-    CTR

## GCM
Galois/Counter Mode (GCM) is a block cipher mode of operation that provides authenticated encryption with associated data (AEAD). It combines the Counter (CTR) mode of encryption with a universal hash function based on Galois field multiplication (GHASH) to achieve both confidentiality and integrity protection for encrypted data.

Here's how GCM works:

1. **Counter Mode (CTR)**: GCM uses the Counter (CTR) mode of encryption to provide confidentiality. In CTR mode, a counter is used to generate a unique keystream for encrypting each plaintext block. The counter value is incremented for each block encrypted.
    
2. **Galois Hash (GHASH)**: GCM uses the GHASH function, which is based on Galois field multiplication, to provide integrity protection. GHASH takes the plaintext, ciphertext, and additional authenticated data (AAD) as input and produces a fixed-size authentication tag. The authentication tag is appended to the ciphertext to provide integrity verification.
    
3. **Encryption and Authentication**: GCM combines the encryption process (CTR mode) and authentication process (GHASH) to provide authenticated encryption. Each plaintext block is encrypted using the encryption algorithm (e.g., AES) in CTR mode, and the resulting ciphertext is fed into the GHASH function along with the plaintext and AAD to compute the authentication tag.
    
4. **Decryption and Verification**: To decrypt and verify the integrity of the ciphertext, the recipient computes the authentication tag using the received ciphertext, plaintext, and AAD. If the computed authentication tag matches the one received with the ciphertext, the ciphertext is considered authentic, and the plaintext can be decrypted.
    

==GCM is widely used in cryptographic protocols and applications that require both confidentiality and integrity protection, such as secure communication protocols (e.g., TLS), disk encryption, and VPNs==. It provides strong security guarantees, including confidentiality, integrity, and authenticity, with relatively low computational overhead compared to separate encryption and authentication schemes. However, it's important to use GCM correctly, including ensuring the uniqueness of nonces (IVs) and avoiding nonce reuse, to maintain its security properties.
##

 7) Examples of techniques used for encrypting information include symmetric encryption (also called public-key encryption) and asymmetric encryption (also called secret-key encryption, or session-key encryption.)
 
symmetric encryption: this is known as session key or secret key
asymmetric encryption: this is known as public key encryption
the question has them flipped so this is false

-    True ( Your answer) X
-    ==False ( Missed)
 
***I thought i marked this as false


8)  Which of the algorithms listed below ==does not== belong to the category of symmetric ciphers?

-    RC4 ( Your answer) X
-    DES
-    ==RSA ( Missed)== asymmetric
-    AES
-    Blowfish
-    3DES
-    Twofish
## RSA
RSA (Rivest-Shamir-Adleman) is not a symmetric cipher; ==it is an asymmetric cryptographic algorithm.

In symmetric cryptography, the same key is used for both encryption and decryption, and both parties must share this secret key. Examples of symmetric ciphers include AES (Advanced Encryption Standard), DES (Data Encryption Standard), and 3DES (Triple DES).

In contrast, RSA is an asymmetric algorithm, meaning it uses a pair of keys: a public key and a private key. The public key is used for encryption, while the private key is used for decryption. This allows for secure communication between parties without the need to share a secret key.

Here's how RSA works:

- The sender encrypts the plaintext using the recipient's public key.
- The recipient decrypts the ciphertext using their private key.
- The private key is kept secret and is known only to the recipient, while the public key can be freely distributed.

RSA is commonly used for key exchange, digital signatures, and secure communication over insecure channels, such as the internet. It provides a way for parties to establish secure communication without needing to exchange secret keys beforehand.
##
9)  Which of the algorithms listed below ==does not== fall into the category of asymmetric encryption?

-    RSA
-    GPG ( Your answer) X
-    DSA
-    ==AES ( Missed)== symmetric
-    DHE
-    ECDHE
-    PGP
## AES
==AES (Advanced Encryption Standard) is a symmetric-key encryption algorithm.== In symmetric cryptography, the same key is used for both encryption and decryption. AES uses a symmetric key to encrypt and decrypt data.

Here's how AES works:

1. **Key Expansion**: AES requires a key of a fixed length (128, 192, or 256 bits). Before encryption or decryption begins, the key is expanded into a set of round keys using a key schedule algorithm.

2. **Encryption**: In the encryption process, AES operates on blocks of plaintext (typically 128 bits in length). The plaintext is divided into blocks, and each block undergoes a series of transformations (substitution, permutation, and mixing operations) using the round keys generated from the key schedule. This process is repeated for multiple rounds (10, 12, or 14 rounds depending on the key size), with each round applying a different set of transformations to the data.

3. **Decryption**: Decryption in AES is essentially the reverse process of encryption. The ciphertext undergoes the same series of transformations as in encryption, but in reverse order and using the decryption round keys derived from the same key schedule. This process effectively reverses the encryption and recovers the original plaintext.

4. **Security**: AES is widely regarded as a highly secure encryption algorithm. It has withstood extensive cryptanalysis and is approved by government agencies for protecting classified information. AES provides strong security guarantees, including resistance to known cryptographic attacks, when used with sufficiently long and random keys.

Due to its efficiency, security, and widespread adoption, AES is the most commonly used symmetric-key encryption algorithm in practice. It is used in a wide range of applications and protocols, including secure communication (e.g., TLS/SSL), disk encryption, file encryption, and VPNs.
##
11)  Which of the following terms illustrate the security through obscurity concept? (Select all that apply)

-    ==Code obfuscation ( Your answer)
-    ==Steganography ( Your answer)
-    ==SSID broadcast suppression ( Missed)
-    Encryption
## SSID
SSID broadcast suppression is not an obscurity concept; rather, it is a security feature commonly used in Wi-Fi networks to enhance security by reducing the visibility of the network's Service Set Identifier (SSID).

The SSID is the name of the Wi-Fi network that clients use to identify and connect to the network. By default, Wi-Fi access points broadcast their SSID periodically to announce their presence to nearby devices. However, this broadcast can be exploited by attackers to gather information about the network and launch various attacks, such as rogue access point attacks or Wi-Fi phishing attacks.

SSID broadcast suppression, also known as SSID hiding or SSID cloaking, is a technique used to prevent access points from broadcasting their SSID. Instead of broadcasting the SSID in beacon frames, the access point suppresses the broadcast, making the network's SSID invisible to devices scanning for available networks.

While SSID broadcast suppression can provide some level of security by making the network less visible to casual attackers, it is not a foolproof security measure. Knowledgeable attackers can still discover hidden SSIDs using techniques such as Wi-Fi sniffing or deauthentication attacks. Additionally, SSID broadcast suppression can introduce usability issues, as clients may have difficulty connecting to hidden networks, and legitimate users may experience connectivity problems.

In summary, SSID broadcast suppression is a security measure aimed at reducing the visibility of Wi-Fi networks to potential attackers. However, it should be considered as just one layer of a comprehensive Wi-Fi security strategy and not relied upon as the sole means of protecting a network. Other security measures, such as strong encryption, authentication mechanisms, and access control policies, should also be implemented to secure Wi-Fi networks effectively.
##

12)  Which of the following enables processing data in an encrypted form?

-    Diffusion ( Your answer) X
-    ==Homomorphic encryption ( Missed)
-    Obfuscation
-    Hashing

## Homomorphic encryption
==Homomorphic encryption is a cryptographic technique that allows computations to be performed on encrypted data without decrypting it first.== In other words, it enables operations to be carried out on ciphertexts, producing encrypted results that, when decrypted, yield the same result as if the operations had been performed on the plaintext.

Homomorphic encryption has several applications:

1. **Secure Computation**: Homomorphic encryption enables secure outsourcing of computations to untrusted servers. A client can encrypt its data, send it to a server for processing, and receive the encrypted results. Since the data remains encrypted throughout the computation, the server never sees the plaintext data, ensuring privacy and confidentiality.

2. **Privacy-Preserving Data Analysis**: Homomorphic encryption allows for privacy-preserving data analysis and collaborative computations. Multiple parties can encrypt their data and share it with a third party or a centralized server for analysis. The server can perform computations on the encrypted data without knowing the plaintext, preserving the privacy of the individual data contributors.

3. **Secure Cloud Computing**: Homomorphic encryption can enhance the security of cloud computing by enabling computations to be performed on encrypted data stored in the cloud. This allows organizations to take advantage of the scalability and cost-effectiveness of cloud services while maintaining control over their sensitive data.

4. **Privacy-Preserving Machine Learning**: Homomorphic encryption can be used to perform privacy-preserving machine learning on encrypted data. Machine learning models can be trained on encrypted data without exposing the raw data to the model trainer, preserving the privacy of sensitive information.

5. **Secure Outsourcing of Data Processing**: Homomorphic encryption enables secure outsourcing of data processing tasks to third-party service providers while protecting the privacy and confidentiality of the data. Organizations can delegate data processing tasks, such as data analysis or query processing, to external parties without revealing the underlying data.

Overall, homomorphic encryption offers a powerful tool for performing computations on sensitive data while preserving privacy and confidentiality. It has the potential to enable a wide range of applications in areas such as healthcare, finance, telecommunications, and government, where data privacy and security are paramount. However, it is important to note that homomorphic encryption is computationally intensive and may not be suitable for all use cases.
##

* Which cryptographic solution would be best suited for low-power devices? ECC ( Your answer) ECC Elliptic Curve Cryptography
 
*  An asymmetric encryption key designed to be used only for a single session or transaction is known as:  Ephemeral key ( Your answer)