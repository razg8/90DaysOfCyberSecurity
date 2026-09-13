## Networking 1
### OSI
- Layer 7 Application : Your eyes
- Layer 6 Presentation : Application Encryption (SSL / TLS)
- Layer 5 Session : Control protocols, tunneling protocols
- Layer 4 Transport : TCP segment, UDP segment
- Layer 3 Network : IP address, Router, Packet
- Layer 2 Data link: Frame, MAC address, Extended Unique Identifiers, switch
- Layer 1 Physical : Cables, fiber, and the signal itself

### Networking Devices
- Router : Routes traffic between IP subnets
- Switch : Bridging done in hardware
- Firewalls : Filter traffic by port number or application
- IDS and IPS : Intrusion Detection System / Intrusion Prevention System
- Load Balancer : Distribute the load
- Proxies : Receives the user requests and sends the request on their behalf
- NAS vs SAN : Network Attached Storage / Storage Area Network
- Access point (AP) : A bridge that extends the wired network onto the wireless network

### Networking Functions 
- Content Delivery Network (CDN) : Geographically distributted; speeds up time to get data from one place to another
- Virtual Private Network (VPN) : Secure private data traversing a public network
- Quality of Service (QoS) : Control by bandwidth usage or data rates; important applications have higher priorities than other
- Time to live (TTL) : Create a timer, wait until traversing a number of hops or until a certain amount of times lapses, then stop.
- Routing loops : Router A thinks the net hop is to Router B, Router B thinks the next hop is Router A
- IP (Internet Protocol) : Default TTL for macOS/Linux is 64 hops, Default TTL for Windows is 128 hops.

### Designing the cloud
- On-demand, elasticity, scale, multitenancy
- Network function virtualization (NFV): Replace physical network devices with virtual versions; manage from the hypervisor
- Virtual Private Cloud (VPC) : A pool of resources (virtual servers, virtual routers/switches, virtual loadbalancers, etc.) created in a public cloud
- Transit Gateway : Connects multiple VPCs
- VPC Gateway/ Internet gateway: Access to anyone in the world to the VPC
- VPC NAT gateway: Allow devices in the VPC to communicate to external resources, *doesn't mean external resources can communicate to internal devices*
- VPC Endpoint: Direct connection between 2 different VPCs between two different cloud providers
- Security groups and lists: Effectively a firewall for the cloud; controls inbound and outbound traffic flow
- Security lists applies to all cloud networks
- Security groups applies to specific virtual NIC (VNIC)

### Cloud deployment models
- Public : Available to everyone over the Internet
- Private : Your own virtualized local data center
- Hybrid : Mix of Public and Private
- Software as a Service (SaaS) : On-demand software, no install, no management or upgrade software, just log in and use; allows managemt of data and applications, e.g Google Mail
- Infrastructure as a Service (IaaS) : (Hardware as a Service) installing your own software, managing your own software, eg Web server providers
- Platform as a Service (PaaS) : You manage everything, someone else handles the platform, you handle the development, develop your app from what's available on the platform, eg salesforce.com

<img width="1281" height="745" alt="image" src="https://github.com/user-attachments/assets/651ecb2f-b5fe-4718-893b-bd3d52d3d851" />

### TCP - Transmission Control Protocol
- Connection-oriented : A formal connection setup and close
- "Reliable" delivery: always result in an acknowledgemnt if that device has received the data
- Flow control: receiver can amange how much data is sent (speed up or slow down)

### UDP - User Datagram Protocol
- Connectionless: No formal open or close to the connection
- "Unreliable" delivery: no acknowledgements received when using UDP, can't guarantee if information has been delivered
- No error recovery
- No flow control

### Port numbers
- The IP gets delivered from one IP address to another IP address
- Each IP address has multiple rooms (TCP/UDP ports)
- Deliver to appropriate application running on that server
- Port number are for communication, not security

### IPv4 sockets
- Server IP address, protocol, server application port number
- Client IP address, protocol, client port number
- Non-ephemeral ports - permanent port numbers: ports 0 through 1,023 for server side
- When connecting to a server almost always using port 80 or 443
- Ephemeral ports - temporary port numbers: ports 1,024 through 65,535 for client side
- Reality is: *any device can use any port number that it wants to*

### <u>Protocols</u>
### FTP - File Transfer Protocol
- Transfers files between systems
- Generic file transferm method for all operating systems
- tcp/20 (active mode data): file transfer process
- tcp/21 (control): send control information
- You can also: list information in a particular directory, add different files, delete,  rename, and perform other types of file maintanence

### SSH - Secure Shell
- Text-based console communication to remote device, able to configure and manage the device over cli
- All communication is all sent in encrypted form
- tcp/22

### SFTP - Secure FTP
- Generic file transfer with security, encrypted by default
- Uses the SSH file transfer protocol (tcp/22)

### Telnet - Telecommunication Network
- Non-encrypted form of terminal communication
- tcp/23 

### SMTP - Simple Mail Transfer Protocol
- Server to server email transfer
- tcp/25 (plaintext)
- tcp/587 (TLS encryption)
- Also used to send mail from a device to a mail server
- Other protocols are used for clients to received emails - IMAP, POP3

### DNS - Domain Name System
- Converts names to IP addresses- udp/53
- www.professormesser.com = 162.159.246.164
- Large transfers may use tcp/53

### DHCP - Dynamic Host Configuration Protocl
- Automated configuration of IP address, subnet mask and other options
- udp/67, udp/68
- Requires a DHCP server
- Dynamic / pooled: Assigned in real-time from a pool, each system is given al ease, must renew at set intervals
- DHCP reservation: addresses are assigned by MAC address in the DHCP server

### TFTP - Trivial File Transfer Protocol
- udp/69
- Very simple file transfer application

### HTTP and HTTPS
- Hypertext Transfer Protocol
- Communication in the browser
- tcp/80 - in plaintext (HTTP)
- tcp/443 - encrypted over SSL or TLS (HTTPS)   

### NTP - Network Time Protocol
- Switches, routers, firewalls, servers, workstations
- Every device has its own clock
- udp/123
 
### SNMP - Simple Network Management Protocol
- Gather statistics from network devices
- udp/161
- v1- the original: structured tables, in the clear
- v2: data type enhancemenets, bulk transfers, in the clear
- v3: message integrity, authentication, encryption
- SNMP traps: alerts and notifications from the network devices (udp/162)
