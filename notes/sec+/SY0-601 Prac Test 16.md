---
{}
---

#### Your Final Report

|   |   |
|---|---|
|Total marks|34|
|Total Questions|25|
|Questions correctly answered|10|
|Success ratio|40%|
|Marks secured|15|
|Percentage secured|44.12%|
need alot of work, maybe redo since its my lowest score so far


1)  Which of the following answers refers to an STP frame?

-    MTU
-    Jumbo frame ( Your answer) X
-    ==BPDU ( Missed)== BPDU Bridge Protocol Data Unit
-    Magic packet

In networking, a Spanning Tree Protocol (STP) frame is a type of frame used by the Spanning Tree Protocol to prevent loops in Ethernet networks. STP ensures a loop-free topology by creating a spanning tree that selectively disables certain redundant paths.

### Key Elements of an STP Frame

1. **Protocol Identifier**:
   - A two-byte field set to `0x0000` indicating the frame is an STP frame.

2. **Version**:
   - A one-byte field specifying the version of the protocol. For standard STP, this value is `0x00`.

3. **BPDU Type**:
   - A one-byte field indicating the type of Bridge Protocol Data Unit (BPDU). The most common types are:
     - **Configuration BPDU (0x00)**: Used for spanning tree computation.
     - **Topology Change Notification (TCN) BPDU (0x80)**: Used to signal topology changes.

4. **Flags**:
   - A one-byte field containing various flags used for specific control purposes, like indicating topology changes.

5. **Root Identifier**:
   - An eight-byte field that includes the priority and MAC address of the root bridge (the bridge with the lowest bridge ID).

6. **Root Path Cost**:
   - A four-byte field indicating the cost from the bridge sending the BPDU to the root bridge.

7. **Bridge Identifier**:
   - An eight-byte field containing the priority and MAC address of the bridge sending the BPDU.

8. **Port Identifier**:
   - A two-byte field specifying the port number through which the BPDU was sent.

9. **Message Age**:
   - A two-byte field indicating the age of the BPDU. It is incremented as the BPDU is propagated through the network.

10. **Max Age**:
   - A two-byte field that specifies the maximum time a BPDU should be considered valid before it is discarded.

11. **Hello Time**:
   - A two-byte field specifying the time interval between the transmission of configuration BPDUs by the root bridge. 

12. **Forward Delay**:
   - A two-byte field indicating the time spent in the listening and learning states before a port begins forwarding traffic.

### Purpose of STP Frames

1. **Electing the Root Bridge**:
   - STP frames are used to elect the root bridge, which is the central reference point in the spanning tree. All bridges exchange BPDUs to determine the bridge with the lowest bridge ID, which becomes the root bridge.

2. **Determining the Shortest Path**:
   - Bridges use STP frames to calculate the shortest path to the root bridge based on the path cost.

3. **Selecting Root Ports and Designated Ports**:
   - STP frames help in determining the root port (the port with the best path to the root bridge) and the designated port (the port that will forward frames for a specific network segment).

4. **Disabling Redundant Paths**:
   - By exchanging BPDUs, STP ensures that redundant paths are disabled, preventing network loops. Ports that are not part of the shortest path to the root bridge are put into a blocking state.

5. **Handling Topology Changes**:
   - When a topology change occurs, STP frames are used to notify all bridges, allowing them to update their configurations and re-establish a loop-free topology.

### Conclusion

STP frames are critical for the operation of the Spanning Tree Protocol, ensuring a loop-free and efficient network topology in Ethernet networks. They facilitate the election of the root bridge, calculation of the shortest path, and management of topology changes, thereby maintaining network stability and reliability.
###
_________________________

2)  The term "DHCP snooping" refers to an exploit that enables operation of a rogue DHCP network server.

-    True ( Your answer) X
-    ==False ( Missed)== 

==DHCP snooping is a security feature that helps protect a network from rogue DHCP servers==. Rogue DHCP servers are unauthorized DHCP servers that can distribute incorrect IP addresses or other network configurations, potentially leading to network disruption, traffic interception, or other security issues.

### How DHCP Snooping Works

1. **Trusted vs. Untrusted Ports**:
   - **Trusted Ports**: These are typically the ports connected to legitimate DHCP servers or the uplink ports to the network core. DHCP messages from these ports are allowed without restriction.
   - **Untrusted Ports**: These ports are connected to clients or areas where rogue DHCP servers might appear. DHCP messages from these ports are closely monitored and restricted.

2. **Packet Inspection**:
   - DHCP snooping inspects all DHCP messages passing through untrusted ports. It checks DHCP Offer and Acknowledgment messages to ensure they are coming from a legitimate DHCP server.

3. **Building a Binding Table**:
   - DHCP snooping maintains a DHCP binding table that records the IP address, MAC address, lease time, binding type, VLAN, and port number of each device that receives an IP address from a trusted DHCP server.

4. **Filtering Untrusted Messages**:
   - DHCP messages from untrusted ports that do not match the information in the binding table or those attempting to offer IP addresses (DHCP Offer messages) are dropped. This prevents rogue DHCP servers from distributing unauthorized IP configurations.

### Benefits of DHCP Snooping

1. **Protection Against Rogue DHCP Servers**:
   - By blocking unauthorized DHCP Offer messages, DHCP snooping prevents rogue DHCP servers from disrupting network operations.

2. **IP Address Tracking**:
   - The DHCP binding table helps track which IP addresses are assigned to which devices, improving network management and security.

3. **Preventing IP Spoofing**:
   - DHCP snooping can also help prevent IP spoofing by ensuring that only devices with valid DHCP leases can use specific IP addresses.

4. **Improved Network Security**:
   - By ensuring that only authorized DHCP servers can assign IP addresses, DHCP snooping enhances overall network security and stability.

### Configuration Steps

1. **Enable DHCP Snooping Globally**:
   ```plaintext
   Switch(config)# ip dhcp snooping
   ```

2. **Enable DHCP Snooping on Specific VLANs**:
   ```plaintext
   Switch(config)# ip dhcp snooping vlan <vlan-id>
   ```

3. **Configure Trusted Ports**:
   ```plaintext
   Switch(config-if)# interface <interface-id>
   Switch(config-if)# ip dhcp snooping trust
   ```

4. **Optional: Set Rate Limits on Untrusted Ports**:
   ```plaintext
   Switch(config-if)# ip dhcp snooping limit rate <rate>
   ```

### Conclusion

DHCP snooping is an essential feature for protecting networks from rogue DHCP servers and ensuring the integrity and security of IP address assignment. By inspecting DHCP messages and enforcing policies on trusted and untrusted ports, DHCP snooping helps maintain a secure and reliable network environment.

____________________

3)  What is the name of a network security access control method in which a 48-bit physical address assigned to each network card is used to determine access to the network?

-    ==MAC filtering ( Missed) 
-    Network Address Translation (NAT)
-    Static IP addressing
-    Network Access Control (NAC) ( Your answer) X

 Your answer to this question is incorrect or incomplete.

4)  Which of the following servers would be best suited to act as an intermediary between an intranet and a screened subnet?

-    UC server
-    Proxy server ( Your answer) X
-    C2 server
-    ==Jump server ( Missed) 

 Your answer to this question is incorrect or incomplete.

5)  In computer networking, a computer system or an application that acts as an intermediary between another computer and the Internet is commonly referred to as:

-    Bridge ( Your answer) X
-    Active hub
-    Server
-    ==Proxy ( Missed) 

Your answer to this question is incorrect or incomplete.

 6) Which of the following statements describe the function of a forward proxy? (Select 2 answers)

-    ==Acts on behalf of a client ( Missed)
-    ==Hides the identity of a client ( Missed)
-    Acts on behalf of a server
-    Hides the identity of a server ( Your answer X

 Your answer to this question is incorrect or incomplete.

7)  Which of the statements listed below describe the function of a reverse proxy? (Select 2 answers)

-    Acts on behalf of a client
-    ==Hides the identity of a server ( Missed)
-    ==Acts on behalf of a server ( Missed)
-    Hides the identity of a client ( Your answer)

 Your answer to this question is incorrect or incomplete.

8)  What are the characteristic features of a transparent proxy? (Select all that apply)

-    ==Doesn't require client-side configuration ( Missed)
-    Modifies client's requests and responses
-    ==Redirects client's requests and responses without modifying them ( Your answer)
-    ==Clients might be unaware of the proxy service ( Your answer)
-    Requires client-side configuration

 Your answer to this question is incorrect or incomplete.

9)  A NIDS/NIPS that detects intrusions by comparing network traffic against the previously established baseline can be classified as: (Select all that apply)

-    ==Heuristic ( Missed)
-    ==Anomaly-based ( Missed)
-    ==Behavioral ( Missed)
-    Signature-based ( Your answer) X

 Your answer to this question is incorrect or incomplete.

10)  A security administrator configured a NIDS to receive traffic from network switch via port mirroring. Which of the following terms can be used to describe the operation mode of the NIDS? (Select 2 answers)

-    In-band
-    ==Passive ( Your answer)
-    ==Inline ( Your answer)
-    Out-of-band ( Missed) X

 Your answer to this question is incorrect or incomplete.

11)  Which of the following answers refers to a piece of hardware and associated software/firmware designed to provide cryptographic functions?

-    EFS
-    ==HSM ( Missed)
-    SFC
-    TPM ( Your answer) X TPM is hardware only 

 Your answer to this question is incorrect or incomplete.

12)  Which of the acronyms listed below refers to a firewall controlling access to a web server?

-    WEP
-    WAP
-    WPS ( Your answer) X
-    ==WAF ( Missed)== WAF Web Application Firewall
 
 Your answer to this question is incorrect or incomplete.

13)  Which of the terms listed below refers to the dynamic packet filtering concept?

-    Port mirroring ( Your answer) X
-    ==Stateful inspection ( Missed)
-    Out-of-band management
-    Stateless inspection

 Your answer to this question is incorrect or incomplete.
 
14)  A solution that alleviates the problem of depleting IPv4 address space by allowing multiple hosts on the same private LAN to share a single public IP address is known as:

-    DNS
-    APIPA ( Your answer)
-    NAT ( Missed) NAT Network Address Translation
-    DHCP

 Your answer to this question is incorrect or incomplete.

Network Address Translation (NAT) is a technique used in networking to modify network address information in the IP header of packets while they are in transit across a traffic routing device. NAT has several important functions, primarily aimed at conserving public IP addresses and improving security.

### Key Functions of NAT

1. **IP Address Conservation**:
   - **Private to Public IP Mapping**: NAT allows multiple devices on a local network to share a single public IP address. By translating private IP addresses to a public IP address, NAT helps conserve the limited number of available IPv4 addresses.
   - **Private IP Range**: Devices within a private network use IP addresses from reserved private IP ranges (e.g., 192.168.0.0/16, 10.0.0.0/8). NAT translates these private addresses to a public address for communication with external networks.

2. **Network Security**:
   - **Hide Internal Network Structure**: NAT hides the internal IP addresses from external networks, making it difficult for external attackers to directly target individual devices within the internal network.
   - **Basic Firewall Functionality**: By default, NAT only allows outbound connections initiated by internal devices and blocks unsolicited inbound traffic, adding a layer of security.

3. **Load Balancing and Redundancy**:
   - **NAT Load Balancing**: NAT can be used to distribute traffic across multiple servers, balancing the load and providing redundancy. This is often referred to as NAT load balancing or server load balancing.

### Types of NAT

1. **Static NAT**:
   - **One-to-One Mapping**: Maps a single private IP address to a single public IP address. This is useful for devices that need to be accessible from the outside, such as web servers.

2. **Dynamic NAT**:
   - **Many-to-Many Mapping**: Maps a private IP address to a pool of public IP addresses. The mapping is dynamic and changes over time based on available public IPs.

3. **PAT (Port Address Translation)**, also known as **NAT Overload**:
   - **Many-to-One Mapping**: Allows multiple devices on a local network to be mapped to a single public IP address using different ports. This is the most common form of NAT used in home and small office networks.

### How NAT Works

1. **Outbound Traffic**:
   - When an internal device (with a private IP address) sends a packet to an external network, the NAT device (usually a router) translates the private IP address to a public IP address and assigns a unique port number. The NAT device keeps a translation table to track these mappings.

2. **Inbound Traffic**:
   - When a response packet comes back from the external network, the NAT device looks up the translation table to find the original private IP address and port number that corresponds to the public IP address and port number. The packet is then translated back and forwarded to the appropriate internal device.

### Example of NAT Process

- **Internal Device**: 192.168.1.2 wants to communicate with a web server on the internet.
- **Translation**: The NAT device translates the source IP 192.168.1.2 to the public IP 203.0.113.5 with a unique source port, e.g., 203.0.113.5:4567.
- **Response**: The web server responds to 203.0.113.5:4567.
- **Translation Back**: The NAT device receives the response, translates it back to 192.168.1.2, and forwards it to the internal device.

### Advantages of NAT

- **IP Address Conservation**: Reduces the need for multiple public IP addresses.
- **Improved Security**: Hides internal network details from the external network.
- **Simplified Network Configuration**: Allows devices to use private IP addresses that are easier to manage.

### Disadvantages of NAT

- **Complexity in Protocols**: Some protocols and applications that embed IP address information in the payload can be disrupted by NAT.
- **Performance Overhead**: NAT requires processing power to translate addresses, which can introduce latency.
- **End-to-End Connectivity Issues**: NAT can complicate direct peer-to-peer communications and can affect some applications and services.

### Conclusion

Network Address Translation (NAT) is a critical function in modern networking that helps conserve IP addresses, enhance security, and simplify network configuration. By translating private IP addresses to public IP addresses, NAT enables multiple devices to share a single public IP address, provides a basic firewall function, and supports various networking applications and scenarios.
### 
---------------------
 15)  Which of the following solutions is used for controlling network resources and assigning priority to different types of traffic?

-    Measured service ( Your answer) X
-    Acceptable Use Policy (AUP)
-    Fair access policy
-    ==Quality of Service (QoS) ( Missed)

 * A nontransparent proxy: (Select 2 answers)  Modifies client's requests and responses  ( Your answer) | Requires client-side configuration ( Your answer)