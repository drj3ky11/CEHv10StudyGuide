After Footprinting phase, you may have enough information about the target. Now Scanning network phase requires some of this information to proceed further.

## 3.1 Overview of Network Scanning

The main objective of Network Scanning is to identify, using highly complex and aggressive reconnaissance techniques:
- live hosts on a network, open ports and IP address
- open & closed ports
- operating system information and system architecture
- services and processes running on a network
- Indentify specific applications or versions of a particular service
- vulnerabilities.

**Types of Scanning**
1. Port Scanning
2. Network Scanning
2. Vulnerability Scanning

**Scanning Methodology**

1. **Checking for live systems** - ping or other type of way to determine live hosts
2. **Discovering open ports** - once you know live host IPs, scan them for listening ports
3. **Scanning beyond IDS** - if needed, use methods to scan  beyond the detection systems
4. **Banner grabbing** - grab from servers as well as perform OS fingerprinting
5. **Scanning Vulnerabilities** - use tools to look at the vulnerabilities of open systems
6. **Network Diagram**  - shows logical and physical pathways into networks
7. **Proxies** - obscures efforts to keep you hidden


### <u>The OSI Reference Model and TCP/IP Model</u>

| Layer | OSI          | Technologies    | Data Unit | Layer | TCP/IP         | OSI Layer Equivalent |
| ----- | ------------ | --------------- | --------- | ----- | -------------- | -------------------- |
| 1     | Physical     | USB, Bluetooth  | Bit       | 1     | Network Access | 1, 2                 |
| 2     | Data Link    | ARP, PPP        | Frame     |       |                |                      |
| 3     | Network      | IP              | Packet    | 2     | Internet       | 3                    |
| 4     | Transport    | TCP             | Segment   | 3     | Transport      | 4                    | 
| 5     | Session      | X255, SCP       | Data      |       |                | 5-7                  |
| 6     | Presentation | AFP, MIME       | Data      | 4     | Application    | 5-7                  |
| 7     | Application  | FTP, HTTP, SMTP | Data      |       |                | 5-7                  |



There are two types of Internet Protocol (IP) traffic. They are **TCP** (Transmission Control Protocol) and **UDP** (User Datagram Protocol). TCP is connection oriented. UDP is a simpler, connectionless Internet protocol. Multiple messages are sent as packets in chunks using UDP. Unlike the TCP, UDP adds no reliability, flow-control, or error-recovery functions to IP packets. Because of UDP’s simplicity, UDP headers contain fewer bytes and consume less network overhead than TCP.

### <u>Subnetting</u>

- **IPv4 Main Address Types**
  - **Unicast** - acted on by a single recipient
  - **Multicast** - acted on by members of a specific group
  - **Broadcast** - acted on by everyone on the network
    - **Limited** - delivered to every system in the domain (255.255.255.255)
    - **Directed** - delivered to all devices on a subnet and use that broadcast address
- **Subnet mask** - determines how many address available on a specific subnet
  - Represented by three methods
    - **Decimal** - 255.240.0.0
    - **Binary** - 11111111.11110000.00000000.00000000
    - **CIDR** - x.x.x.x/12   (where x.x.x.x is an ip address on that range)
  - If all the bits in the host field are 1s, the address is the broadcast
  - If they are all 0s, it's the network address
  - Any other combination indicates an address in the range
  - ![img](https://s3.amazonaws.com/prealliance-thumbnails.oneclass.com/thumbnails/001/751/775/original/stringio.txt?1513221790)
  - If it begins by 0 it is class **A**, 10 class **B**, 110 class **C** and 1110 class **D**

**Network address translation (NAT)** is a method of remapping an IP to private networks (there are not enough IPv4 for all)


| CIDR block | Address range | Classful description |
| ---------- | -------------------------- | ----------------------------------- 
| 10.0.0.0/8 | 10.0.0.0 – 10.255.255.255 | Single Class A |
| 172.16.0.0/12 | 172.16.0.0 – 172.31.255.255 | Contiguous range of 16 Class B blocks |
| 192.168.0.0/16 | 192.168.0.0 – 192.168.255.255 |Contiguous range of 256 Class C blocks|

### <u>Creating custom packet using TCP flags</u>

Packet crafting tools are user to generate and analyze network traffic.
- [Colasoft Packet Builder](https://www.colasoft.com/packet_builder/)
- [NetScan Tools Pro](https://www.netscantools.com)
- [WAN Killer](https://www.solarwinds.com/es/engineers-toolset/use-cases/traffic-generator-wan-killer)

### <u>Scanning in IPv6 Networks</u>

IPv6 increases the size from 32bits to 128bits. It is more complex the network scanning due to the big amount of addresses.

## 3.2 Scanning Tools

### <u>**Nmap**</u>

| Switch          | Description                                                  |
| --------------- | ------------------------------------------------------------ |
| -sA             | ACK scan                                                     |
| -sF             | FIN scan                                                     |
| -sI             | IDLE scan                                                    |
| -sL             | DNS scan (list scan)                                         |
| -sN             | NULL scan                                                    |
| -sO             | Protocol scan (tests which IP protocols respond)             |
| -sP             | Ping scan                                                    |
| -sR             | RPC scan                                                     |
| -sS             | SYN scan                                                     |
| -sT             | TCP connect scan                                             |
| -sW             | Window scan                                                  |
| -sX             | XMAS scan                                                    |
| -A              | OS detection, version detection, script scanning and traceroute |
| -PI             | ICMP ping                                                    |
| -Po             | No ping                                                      |
| -PS             | SYN ping                                                     |
| -PT             | TCP ping                                                     |
| -oN             | Normal output                                                |
| -oX             | XML output                                                   |
| -T0 through -T2 | Serial scans.  T0 is slowest                                 |
| -T3 through -T5 | Parallel scans.  T3 is slowest                               |


### <u>**Hping2 & Hping3**</u>

TCP/IP packet assembler and analyzer tool that is used to send customized TCP/IP packets and display the target reply as ping command display the ICMP. Using [Hping](http://www.hping.org), the following parameters can be performed: 
- Test firewall rules.
- Advanced port scanning.
- Testing net performance.
- Path MTU discovery.
- Transferring files between even fascist firewall rules.
- Traceroute-like under different protocols.
- Remote OS fingerprinting & others.

| Switch  | Description                                                  |
| ------- | ------------------------------------------------------------ |
| -1      | Sets ICMP mode                                               |
| -2      | Sets UDP mode                                                |
| -8      | Sets scan mode.  Expects port range without -p flag          |
| -9      | Listen mode.  Expects signature (e.g. HTTP) and interface (-I eth0) |
| --flood | Sends packets as fast as possible without showing incoming replies |
| -Q      | Collects sequence numbers generated by the host              |
| -p      | Sets port number                                             |
| -F      | Sets the FIN flag                                            |
| -S      | Sets the SYN flag                                            |
| -R      | Sets the RST flag                                            |
| -P      | Sets the PSH flag                                            |
| -A      | Sets the ACK flag                                            |
| -U      | Sets the URG flag                                            |
| -X      | Sets the XMAS scan flags                                     |

**ICMP Scanning** sending an ICMP Echo Request to the network IP address

**ACK Scanning on Port 80** to probe for the existence of a firewall and its rule sets.

### <u>NetScanTools Pro</u>

[NetScan Tools Pro](https://www.netscantools.com) is an investigation tool that allows you to troubleshoot, monitor, discover and detect devices on your network. It offers:
- Active Discovery and Diagnostic Tools
- Passive Discovery Tools
- DNS Tools
- Local Computer and General Information Tools

### <u>Scanning Tools fot Mobile</u>

- [IP Scanner](https://10base-t.com)
- [Fing](https://www.fing.com)

## 3.3 Scanning Techniques 

### <u>Check for Open Ports</u>

**SSDP Scanning**
Simple Service Discovery Protocol (SSDP) is a protocol used for discovery of network services without the assistance of server-based configuration (DHCP & DNS)

### <u>Port Numbers</u>

- **Internet Assigned Numbers Authority** (IANA) - maintains Service Name and Transport Protocol Port Number Registry which lists all port number reservations

- Ranges

  - **Well-known ports** - 0 - 1023

  - **Registered ports** - 1024 - 49,151

  - **Dynamic ports** - 49,152 - 65,535

    | Port Number | Protocol | Transport Protocol |
    | ----------- | -------- | ------------------ |
    | 20/21       | FTP      | TCP                |
    | 22          | SSH      | TCP                |
    | 23          | Telnet   | TCP                |
    | 25          | SMTP     | TCP                |
    | 53          | DNS      | TCP/UDP            |
    | 67          | DHCP     | UDP                |
    | 69          | TFTP     | UDP                |
    | 80          | HTTP     | TCP                |
    | 110         | POP3     | TCP                |
    | 135         | RPC      | TCP                |
    | 137-139     | NetBIOS  | TCP/UDP            |
    | 143         | IMAP     | TCP                |
    | 161/162     | SNMP     | UDP                |
    | 389         | LDAP     | TCP/UDP            |
    | 443         | HTTPS    | TCP                |
    | 445         | SMB      | TCP                |
    | 514         | SYSLOG   | UDP                |

### <u>Ping Sweep-Checking for Live Systems</u>

It is done by ICMP Echo pakets (Internet Control Message Protocol)

 **Message Types and Returns**

  | ICMP Message Type           | Description and Codes                                        |
  | --------------------------- | ------------------------------------------------------------ |
  | 0:  Echo Reply              | Answer to a Type 8 Echo Request                              |
  | 3:  Destination Unreachable | Error message followed by these codes:<br />0 - Destination network unreachable<br />1 - Destination host unreachable<br />6 - Network unknown<br />7 - Host unknown<br />9 - Network administratively prohibited<br />10 - Host administratively prohibited<br />13 - Communication administratively prohibited |
  | 4: Source Quench            | A congestion control message                                 |
  | 5: Redirect                 | Sent when there are two or more gateways available for the sender to use.  Followed by these codes:<br />0 - Redirect datagram for the network<br />1 - Redirect datagram for the host |
  | 8:  Echo Request            | A ping message, requesting an echo reply                     |
  | 11:  Time Exceeded          | Packet took too long to be routed (code 0 is TTL expired)    |

  - Payload of an ICMP message can be anything; RFC never set what it was supposed to be.  Allows for covert channels
  - **Ping sweep** - easiest method to identify hosts. ICMP Echo Request packets to a range of IP addresses
  - **ICMP Echo scanning** - sending an ICMP Echo Request to the network IP address
  - An ICMP return of type 3 with a code of 13 indicates a poorly configured firewall
  - **Ping scanning tools**
    - Nmap
    - Angry IP Scanner
    - Solar-Winds Engineer Toolkit
    - Advanced IP Scanner
    - Pinkie
    - Nmap virtually always does a ping sweep with scans unless you turn it off

### <u>TCP connect/ Full open Scan</u>
  
**TCP Flags**

| Flag | Name           | Function                                                     |
| ---- | -------------- | ------------------------------------------------------------ |
| SYN  | Synchronize    | Set during initial communication.  Negotiating of parameters and sequence numbers |
| ACK  | Acknowledgment | Set as an acknowledgement to the SYN flag.  Always set after initial SYN |
| RST  | Reset          | Forces the termination of a connection (in both directions)  |
| FIN  | Finish         | Ordered close to communications                              |
| PSH  | Push           | Forces the delivery of data without concern for buffering    |
| URG  | Urgent         | Data inside is being sent out of band.  Example is cancelling a message |

**TCP Handshake**

SYN -> SYN-ACK -> ACK
Then Seq grows and ack (it will be the seq waited in the other side.) During the establishment of the connection also they send the maximum window.
You can learn more (as always) in [Wikipedia](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)
  
  
TCP connect scan establishes a full connection ant tears it down by sending a RST.
    nmap -sT

### <u>Inverse TCP flag</u>
  
  - uses FIN, URG or PSH or no flag(NULL scan).  Open gives no response.  Closed gives RST/ACK
  - nmap -sN (Null scan)
  - nmap -sF (FIN scan)
  
### <u>Xmas</u>

  - so named because all flags are turned on so it's "lit up" like a Christmas tree
  - Responses are same as Inverse TCP scan
  - Do not work against Windows machines
  - nmap -sX
  
### <u>IDLE/IPID Header Scan</u>

It uses a third party to check if a port is open. Every IP packet has Fragment Identification Number (IPID).OS increments IPID for each packet.
  - Looks at the IPID to see if there is a response
  - Only works if third party isn't transmitting data
  - Sends a request to the third party to check IPID id; then sends a spoofed packet to the target with a return of the third party; sends a request to the third party again to check if IPID increased.
    - IPID increase of 1 indicates port closed
    - IPID increase of 2 indicates port open
    - IPID increase of anything greater indicates the third party was not idle
  - nmap -sI <zombie host>

### <u>Stealth (Half-open Scan)</u>

Half-open scan or SYN scan - only SYN packets sent.  Responses same as full.
  - Useful for hiding efforts and evading firewalls
  - nmap -sS

### <u>ACK flag probe</u>

- multiple methods
  - TTL version - if TTL of RST packet < 64, port is open
  - Window version - if the Window on the RST packet is anything other than 0, port open
  - Can be used to check filtering.  If ACK is sent and no response, stateful firewall present.
  - nmap -sA (ACK scan)
  - nmap -sW (Window scan) 
  
 ### <u>Por Scaning Countermeasures</u>
 
  + Configure firewall and IDS rules to detect and block probes.
  + Check running port scanning tools if the firewall is properly configurated.
  + Ensure that the mechanism used for routing and filtering at the routers and firewalls respectively cannot be bypassed.
  + Ensure that the router, IDS and firewall have the firmware update.
  + Use custon rules to lock down the network and block unwnanted ports at the firewall.
  + Filter all ICMP messages at the firewall and the routers.
  + Check the network configuration and its available ports performing TCP and UDP scanning along with ICMP probes.

## 3.4 Scanning beyond IDS

The attacker uses Fragmentation and Small packets to evade Security devices such as Firewalls, IDS (Intrusion Detection System), and IPS (Intrusion Prevention System). The idea is split the payload into the smaller packet. The well known evasion techniques are:

- **Packet Fragmentation**: sending fragmented probe packets.
- **Source Routing**: specifying the routing path for the malformed packet to reach the intended server.
- **IP Address Decoy**: generating or manually specifying IP address of the decoys so that the IDS/Firewall cannot determinate the actual IP address.

    nmap -D RND:|target|
    
- **IP Address Spoofing**: changing source IP address so that the packet appears to be from someone else.

    Hping3 target -a ipaddress
    
To detect a IP Spoofing scan, it must be sent a probe to the host of suspect traffic that triggers reply and compare the IP ID; if IP ID are not close un value to the packet being checked, suspect traftic is spoofed.
Some IP spoofing countermeasures are:
    - Encrypt all the network traffic.
    - Use multiple firewalls.
    - Do not rely IP-bases authentication.
    - Use random initial SEQ number.
    - Ingress filtering, use routers and firewalls at your network perimeter to filter incoming packets that appear to come from an internal IP address.
    - Egress filtering.
    
- **Proxy Server**: using chain of proxy servers to hide the actual source of a scan and evade certain IDS/firewall restrictions. A proxy server is used as a firewall, as an IP address multiplexer (NAT/PAT), to anonnymize web surfing, to extract unwanted content, to provide some protection and to save bandwidth.

The proxy server mediates between you and the actual server to transmit and respond to the request. Some proxy tools are:

    - [Proxy Switcher](https://www.proxyswitcher.com)
    - Proxy Workbench
    - [CyberGhost](https://www.cyberghostvpn.com)

- **Anonnymizers** It removes all the identifying info from the user's computer.

- **Censorship Cicumbention Tools**
    - [Alkasir](https://github.com/alkasir/alkasir)Alkasir is a cross-platform, open-source and robust website censorship circumvention tool that also maps censorship patterns around the world.
    - [Tails](https://tails.boum.org) is a portable operating system that protects against surveillance and censorship. It leave no trace on the computer.

## 3.5 Banner Grabbing/OS Fingerprinting

Two types, *active* or *pasive*. Banner grabbing is determining the OS and services that are running on the target machine. Typically, Telnet is used to retrieve information of banner.
Passive OS Fingerprinting requires detail assessment of traffic. Analyzing network traffic along with special inspection of Time to Live (TTL) value and Window Size. Some of the common values for operating systems are:

  | OS | TTL | TCP Window Size |
  |-- | ----- | ----------------- |
  | Linux | 64 | 5840 |
  | Google customized Linux | 64 | 5720 |
  | FreeBSD | 64 | 65535 |
  | Windows XP | 128 | 65535 |
  | Windows Vista, 7 and Server 2008 | 128 | 8192 |
  | Cisco Router (iOS 12.4) 64 | 255 | 4128 |

Some useful tools are: ID Server, Netcraft, Netcat, Telnet, Xprobe, pof and Maltego.

There are some banner grabbing countermeasures:

- Disabling or changing banner. Displaying folase banners, turn off unnecesary services, use ServerMask tools...
- Hiding file extension from Web Pages (better if not used at all)

##c

**Network Discovery Tool** 
List of some popular tools are: -
1. Network Topology Mapper
2. OpManager
3. Network View
4. LANState Pro

**Drawing Network Diagrams**
Solar Wind Network Topology Mapper can discover network & create a comprehensive network topology diagram.

## 3.7 Scanning Pen Testing

There are tree important steps:

1. **Perform host discovery**
2. **Perform port scanning**
3. **Scan beyond IDS and firewall**
