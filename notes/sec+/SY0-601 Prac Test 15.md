---
{}
---
#### Your Final Report

|   |   |
|---|---|
|Total marks|29|
|Total Questions|25|
|Questions correctly answered|20|
|Success ratio|80%|
|Marks secured|25|
|Percentage secured|86.21%|

1)  In computer security, a mechanism for safe execution of untested code or untrusted applications is referred to as:

-    Sideloading ( Your answer) X
-    Containerization
-    ==Sandboxing ( Missed) 
-    Stress testing
***read the questions!!
2)  In a weighted round-robin load balancing method, each consecutive request is handled in a rotational fashion, but servers with higher specs are designated to process more workload.

-    ==True ( Missed) 
-    False ( Your answer) X

3)  Which VPN type is used for connecting computers to a network? (Select all that apply)

-    ==Remote access ( Your answer)
-    Intranet-based
-    ==Client-to-site ( Your answer)
-    Site-to-site ( Your answer) X
-    Extranet-based

4)  Which of the following protocols provide protection against broadcast storms and switching loops? (Select 2 answers)

-    RTP
-    SRTP ( Your answer) X
-    RDP
-    ==STP ( Missed)==  Spanning Tree Protocol (STP)
-    ==RSTP ( Your answer)== Rapid Spanning Tree Protocol (RSTP: IEEE 802.1w) is a network protocol that is an advancement over Spanning Tree Protocol (STP: IEEE802.1D) that promotes high availability and “loop-free” topology within Ethernet networks.
[Differences](https://www.geeksforgeeks.org/difference-between-spanning-tree-protocol-stp-and-rapid-spanning-tree-protocol-rstp/)
---------------------------------------------------------------------

 * A logical grouping of computers that allow computer hosts to act as if they were attached to the same broadcast domain regardless of their physical location is known as: VLAN ( Your answer)
 
 *  Which of the following answers refers to network traffic within a data center, a.k.a. server-to-server traffic?  East-west ( Your answer)
 
 *  Which of the following answers refers to a deprecated method for implementing Virtual Private Networks (VPNs)?  PPTP ( Your answer) PPTP Point-to-Point Tunneling Protocol
 
	 * Point-to-Point Tunneling Protocol (PPTP) is a network protocol used to implement virtual private networks (VPNs). PPTP was developed by a consortium of vendors, including Microsoft, as an extension of the Point-to-Point Protocol (PPP), which is used to enable secure data transfer between two points over a network.

	### Key Features of PPTP
	
	1. **Tunneling**:
	   - PPTP creates a tunnel through which data packets can be securely transmitted. It encapsulates PPP packets within IP packets for transmission over the Internet or other IP-based networks.
	
	2. **Encryption**:
	   - PPTP uses the PPP protocol to establish a connection and can utilize Microsoft's Point-to-Point Encryption (MPPE) to encrypt the data within the tunnel. MPPE supports 40-bit, 56-bit, and 128-bit encryption strengths.
	
	3. **Authentication**:
	   - PPTP supports various authentication methods, including Password Authentication Protocol (PAP), Challenge Handshake Authentication Protocol (CHAP), and Microsoft CHAP (MS-CHAP) versions 1 and 2. MS-CHAPv2 provides stronger authentication by using a two-way handshake.
	
	4. **Ease of Use**:
	   - PPTP is relatively easy to set up and configure, especially on Windows platforms. It is built into many versions of Microsoft Windows, making it convenient for users to implement a VPN without additional software.
	
	### How PPTP Works
	
	1. **Establishing the Tunnel**:
	   - The client establishes a TCP connection to the PPTP server on port 1723. This connection is used to manage and control the PPTP session.
	
	2. **Authentication and Configuration**:
	   - The client and server authenticate each other using one of the supported authentication protocols. Once authenticated, the server assigns an IP address to the client for use within the VPN.
	
	3. **Encapsulation and Encryption**:
	   - Data packets are encapsulated within PPP frames, which are then encapsulated within GRE (Generic Routing Encapsulation) packets. These GRE packets are transmitted through the established tunnel. If MPPE is enabled, the data wi
	   - thin the PPP frames is encrypted.
	
	4. **Transmission**:
	   - The encapsulated packets are transmitted over the network to the PPTP server, which decapsulates them, decrypts the data if necessary, and forwards the original data to its intended destination.
	
	### Advantages of PPTP
	
	1. **Compatibility**:
	   - Widely supported across various operating systems, including older versions of Windows, Linux, and macOS.
	
	2. **Ease of Setup**:
	   - Simple to configure and use, especially on Windows platforms where it is built-in.
	
	3. **Low Overhead**:
	   - Relatively low computational overhead compared to some other VPN protocols, resulting in faster connection speeds.
	
	### Disadvantages of PPTP
	
	1. **Security Concerns**:
	   - PPTP is considered less secure compared to more modern VPN protocols. Vulnerabilities have been found in its encryption methods (MPPE) and the MS-CHAPv2 authentication protocol, making it susceptible to attacks such as dictionary attacks and man-in-the-middle attacks.
	
	2. **Obsolescence**:
	   - Due to its known security weaknesses, PPTP is largely deprecated in favor of more secure protocols such as L2TP/IPsec, OpenVPN, and IKEv2/IPsec.
	
	3. **Firewall and NAT Issues**:
	   - PPTP's use of GRE can cause problems with firewalls and Network Address Translation (NAT), which may require additional configuration to allow PPTP traffic.
	
	### Conclusion
	
	While PPTP was one of the early protocols used for VPNs and offered ease of setup and compatibility, its security weaknesses have led to a decline in its use. For secure VPN connections, it is generally recommended to use more modern protocols that provide stronger encryption and better security features.

*  An HTML5 VPN portal is an example of clientless VPN implementation where an HTML5-compliant web browser along with TLS encryption can be used instead of a dedicated VPN client software.  True ( Your answer)

*  Network Access Control (NAC) defines a set of rules enforced in a network that the clients attempting to access the network must comply with. With NAC, policies can be enforced before (pre-admission NAC) and/or after end-stations gain access to the network (post-admission NAC). NAC can be implemented with the use of agent software which can be installed on the client machine permanently (this type of software is referred to as permanent agent) or used only temporarily during checks (this type of software is known as dissolvable agent). Another implementation option is agentless NAC, where checks are performed remotely without the need for any client software agents. In agentless NAC, the client machine is checked by external security device with the use of either passive or active network discovery methods. True ( Your answer)