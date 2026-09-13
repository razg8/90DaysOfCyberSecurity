## Networking
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

