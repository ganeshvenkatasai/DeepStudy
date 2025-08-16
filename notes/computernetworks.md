# Computer Networks

## Networking Fundamentals
### Basic Concepts
- `Network` → Interconnected devices sharing resources  
- `Node` → Any network-connected device (computer, router, etc.)  
- `Link` → Physical/Logical connection between nodes  
- `Protocol` → Rules for communication between devices  

### Network Types
- `LAN` → Local Area Network (small geographical area)  
- `WAN` → Wide Area Network (large geographical area)  
- `MAN` → Metropolitan Area Network (city-wide)  
- `PAN` → Personal Area Network (devices around a person)  

## OSI Model
- `Layer 7: Application` → HTTP, FTP, SMTP protocols  
- `Layer 6: Presentation` → Data translation/encryption  
- `Layer 5: Session` → Manages connections between apps  
- `Layer 4: Transport` → TCP/UDP (end-to-end communication)  
- `Layer 3: Network` → IP addressing/routing  
- `Layer 2: Data Link` → MAC addressing/frame handling  
- `Layer 1: Physical` → Cables/wireless signals  

## TCP/IP Model
- `Application` → Combines OSI's App/Presentation/Session  
- `Transport` → Same as OSI Layer 4  
- `Internet` → Same as OSI Network layer  
- `Network Access` → Combines OSI Data Link/Physical  

## Protocols
### Transport Layer
- `TCP` → Connection-oriented, reliable delivery  
- `UDP` → Connectionless, faster but unreliable  
- `Ports` → Logical endpoints (HTTP=80, HTTPS=443)  

### Application Layer
- `HTTP/HTTPS` → Web communication  
- `FTP/SFTP` → File transfer protocols  
- `SMTP/POP3/IMAP` → Email protocols  
- `DNS` → Domain name to IP resolution  

## IP Addressing
- `IPv4` → 32-bit address (4 octets)  
- `IPv6` → 128-bit address (hexadecimal)  
- `Subnetting` → Dividing networks logically  
- `CIDR` → Classless Inter-Domain Routing notation  
- `NAT` → Translates private IPs to public  

## Routing
- `Static Routing` → Manual route configuration  
- `Dynamic Routing` → Automatic (OSPF, BGP, RIP)  
- `Routing Tables` → Path determination rules  
- `Default Gateway` → Exit point for unknown destinations  

## Switching
- `MAC Address` → Unique hardware identifier  
- `ARP` → Maps IP to MAC addresses  
- `Switching Tables` → MAC-to-port mappings  
- `VLANs` → Virtual LAN segmentation  

## Network Devices
- `Hub` → Dumb repeater (Layer 1)  
- `Switch` → Intelligent MAC-based forwarding (Layer 2)  
- `Router` → IP-based path selection (Layer 3)  
- `Gateway` → Interface between different networks  

## Wireless Networking
- `Wi-Fi Standards` → 802.11a/b/g/n/ac/ax  
- `SSID` → Network identifier name  
- `Encryption` → WEP/WPA/WPA2/WPA3  
- `Channels` → Frequency bands for communication  

## Network Security
- `Firewall` → Filters incoming/outgoing traffic  
- `VPN` → Secure remote network access  
- `IDS/IPS` → Intrusion Detection/Prevention Systems  
- `DDoS` → Distributed Denial of Service attack  

## Performance Concepts
- `Bandwidth` → Maximum data transfer rate  
- `Throughput` → Actual data transfer rate  
- `Latency` → Time for data to reach destination  
- `Jitter` → Variation in packet arrival times  

## Troubleshooting
- `Ping` → Tests reachability (ICMP)  
- `Traceroute` → Maps path to destination  
- `Netstat` → Displays network connections  
- `Packet Sniffers` → Wireshark/tcpdump analysis  

## Advanced Topics
- `SDN` → Software Defined Networking  
- `Load Balancing` → Distributes network traffic  
- `CDN` → Content Delivery Networks  
- `QoS` → Quality of Service prioritization  

## Cloud Networking
- `VPC` → Virtual Private Cloud isolation  
- `Direct Connect` → Dedicated cloud network link  
- `Peering` → Direct connection between networks  
- `NSG` → Network Security Group rules  
