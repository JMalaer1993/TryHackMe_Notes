# Network Fundamentals
## Basic Concepts
 * Network - A network is just devices that are connected.
 * Internet - The internet is just a giant network made up of many tiny networks. The aim of the internet is 
    + Private Networks - These tiny networks are called private networks.
    + Public Networks - The private networks are connected through public networks.
 * WWW - World Wide Web. Invented by Tim Berners-Lee in 1989.
 * IP (Internet Protocol) Address - A temporary address assigned to a device on a network. Private IP addresses are assigned to devices within a private network while public IP adresses assigned to devices on the internet. There cannot be the same private IP address assigned to different devices simultaneiously on the same private network. However, two devices that share a private network could share the same public IP address.
   + IPv4 - Consists of 4 octets. Each octet contains 8 bits, so 32 bits total.
   + IPv6 - Allows for WAY more devices on the internet.
 * NAT - Network Address Translation converts private IP addresses to public IP addresses and vice versa.
    + SNAT - Source Network Address Translation.
    + DNAT - Destination Network Address Translation.
 * PAT - Port Address Translation is a type of NAT that maps multiple private IP addresses to one public IP address using different ports.
 * MAC (Media Access Control) Address - A permanent address assigned to a device on a network, like a fingerprint. Consists of 12 characters in hexadecimal format.
    + Spoofing - MAC addresses can be "spoofed." This is kind of like identity theft. This occurs when a device pretends to be another device by using its MAC address. One might spoof their MAC address to access resources available to other devices.
 * NIC - Network Interface Card. MAC addresses are assigned to the NIC on each device.
 * ISP - Internet Service Providers assign public IP addresses to devices for a fee.
 * Ping - Ping is a basic network utility that uses ICMP Echo Request and Echo Reply messages to check whether a remote device is reachable and how long it takes to respond (latency).
   + ICMP - Internet Control Message Protocol.
   + Ping Syntax - "Ping (insert IP address or URL here)"
 * LAN - Local Area Network. A LAN is a physical/logical network that connects devices within a small geographic area, like a home, office, or campus. Isolated from the public network unless connected through a gateway.
 * VLAN - Virtual LAN. Just a LAN that has been divided. So if you have devices connected to the same switch, you group the devices such that thay can no longer commmunicate directly with eachother. These two group are then VLANS.
 * Topologies - LANS can be arranged in different topologies, each with their own set of advantages and disadvantages.
    + Star - Each device is connected directly to a central device such as a switch. Most reliable but also most expensive.
    + Bus - Bus topology connects all devices to a single central communication line (the "bus" or backbone cable). It’s cheap and simple, but performance degrades as more devices are added due to network congestion (traffic jams). There's no redundancy. The backbone cable is a single point of failure. If the backbone cable is damaged, the entire network goes down.
    + Ring - Devices are connected directly to eachother forming a loop. Less susceptible to congestion, but a single break in the circuit or a failure of a single device breaks the network.
 * Switch - Used within LANs to connect mutiple devices like printers, computers, and servers. They can even be daisy-chained, or connected to other switches. The often keep track of which device is connected to which port.
 * SNMPv3 - Simple Network Management Protocol is used to MONITOR and manage devices within a LAN, such as switches, routers, and printers. SNMPv1 and v2 are not secure because they send data in cleartext, but SNMPv3 uses authentication and encryption, making it secure.
 * Router - A router just routes data based on a routing table. You can think of routers like thousands of Tron style baseball players standing in an a massive field. Their job is to catch and throw the data balls from baseball player to baseball player in the optimal path (OSPF) until the ball reaches its intended destination. If a player drops the ball, that's called a packet loss. There's countless (literally) data balls contantly flying everywhere in every direction at the speed of light.
 * Port Forwarding - A router can be configure to forward ports. This is just how one opens up his local server to the internet, so hother people can access his server.
 * Firewalls - A device that determines the traffic that is allowed to enter/exit a device/network. An adminstrator can can configure a firewall to permit or deny traffic based on rules. The following are different characeristics a firewall can inspect packets for:
    - Source IP address
    - Destination IP address
    - Destination Port
    - Protocols (like UDP or TCP)
 * Stateless Firewalls - Only inspects individual packets without any context.
 * Stateful Firewalls - Inspects packets based on the context of the entire session.
 * Subnetting - Dividing a network into smaller networks within itself. Devices on the same subnet can communicate directly with eachother, but devices on different subnets have to communicate through a router.
   + Subnet Mask - Each subnet is assigned a subnet mask which is an IP address used to identify that subnet.
* ARP - Address Resolution Protocol. Turns a devices MAC address into an IP address within the network.
   + ARP Request
   + ARP Reply
   + ARP Cashe
* DHCP - Dynamic Host Configuration Protocol. Assigns devices IP addresses.
   + Discover
   + Offer
   + Request
   + Acknowledge
* VPN - Virtual Private Network. Connect networks separated by space through a secure tunnel. Thats just means a sniffer or eavesdropper won't be able to understand your data if intercepted.
   + PPP - Encrypts and authenticates but is NOT routable by itself.
   + PPTP - Point to Point Tunneling Protocol. Makes PPP routable. Easy to set up but weak encryption.
   + IPsec - Hard to set up but strong encryption.
## Open Systems Interconnection (OSI) Model
  1. Physical - Ethernet.
  2. Data Link
      + Frames - No IP Address! Travel within the LAN.
      + NIC - Network Interface Card.
      + ARP - Adress Resolution Protocol.
  3. Network/Routing
      + Packets - IP Addresses! Travel the internet.
      + OSPF - Open Shortest Path First.
      + RIP - Routing Information Protocol.
  4. Transport
      + UDP - User Datagram Protocol.
      + TCP - Transmission Control Protocol.
  5. Session
  6. Presentation
      + Encryption
      + Decryption
  8. Application - The payload is born at this layer, and dies at this layer.
     + HTTP and HTTPS
     + DNS - Domain Name System.
     + GUI - Graphical User Interface. (not actually part of layer 7 but good to know)
#### As data travels through each of the OSI model layers, pieces of information are added. This is encapsualtion. It's like the data is being encapsulated with more and more information. Stripping this information away is known as decapsulation. These terms are kind of misleading, because data travels in a single file line. When we encapsulate a payload, we are not actually wrapping data in layers of more information, but adding information to the front of the line (header) or back of the line (trailer). That being said, at layer 2, an ethernet header AND trailer are added at the same time, which actually literally does encapsulate the payload. However, most layers only add headers.
 ## TCP/ICP
  * Layers
    + Aplication
    + Transport
    + Internet
    + Network Iterface
  * Establishing a Connection (3-Way Handshake)
    + SYN
    + SYN/ACK
    + ACK - These acknowledgements are one of the defining charactistics of TCP. UDP does NOT use acknowledgments.
    + DATA
    + FIN
    + RST
  * Headers
    + Source Port
    + Desination Port
    + Source IP
    + Desintation IP
    + Sequence Number
    + Acknowledgment Number
    + Checksum
    + Flag
   #### It is worth comparing TCP/IP and UDP/IP. Both of them share a few of the same headers, such as the source/destination port/IP. One big difference is that TCP is stateful while UDP is stateless. This is just to say that TCP establishes a connection, while UDP does not. UDP just sends the data and hopes for the best. That is why TCP is much more reliable, but it is also much slow. So, both have their place.
# How the Web Works
## Domain Name System (DNS)
#### DNS resolves user friendly words to IP addresses. That way, you can remember a name and not an IP address. Imagine having to know the IP address for the each server that hosts every website you want to visit.
* Domain Hierarchy
  + Root
  + TLD - Top Level Domain.
    - gTLD - Generic TLD.
    - ccTLD - Country Code TLD.
  + Second-Level
  + Subdomain
* DNS Record Types
  + A - Resolves IPv4.
  + AAAA - Resolves IPv6.
  + CNAME - Resolves one domain name to anouther domain name.
  + MX Record - Directs where to send email based on priority.
  + TXT Record - Text based data.
* DNS Request Process
  1. When you request a domain name, your computer first checks its local DNS cache.
  2. If the IP address isn’t there, it queries a recursive DNS resolver (usually provided by your ISP).
  3. If the recursive resolver doesn't have the IP cached, it starts a DNS lookup by querying a root server, which responds with the address of the appropriate Top-Level Domain (TLD) server (e.g., .com, .org).
  4. The recursive resolver then asks the TLD server, which replies with the address of the authoritative nameserver for that domain.
  5. The recursive resolver then queries the authoritative nameserver, which provides the final IP address.
  6. That IP is returned to your computer, and the recursive resolver caches it for future use.
  7. Summary of all the servers involved in a DNS request:
     + Recrusive
     + Root
     + TLD
     + Authoritative Name Server
#### Its also worth noting that DNS records stored in cache have a TTL. That way, you're not using an old record that was updated a long time ago. After the TTL, the record goes "stale."
## Hypertext Transfer Protocol (HTTP)
#### HTTP Refers to the set of rules used when communicating with web servers to transmit webpage data.
* Tim-Berners Lee - Created HTTP around 1990.
* HTTPS - The secure version of HTTP. Provides encryption of data and verification that you are talking to the correct web server, rather than a malicious server.
* URL - Uniform Resource Locator. As that name sugest, a URL, which you type into a webpage, is basically an instruction of how and where to request resources on the internet. A URL is made up of a few parts:
  + Scheme
  + User
  + Host
  + Port
  + Path
  + Query String
  + Fragment
* HTTP Methods
  + GET - Get information from the web server.
  + POST - Submit new information to the web server.
  + PUT - Update existing information.
  + DELETE - Deletes information from a web server.
* Common HTTP Status Codes
  + 200 - OK
  + 201 - Created
  + 301 - Moved Permanently
  + 302 - Found
  + 400 - Bad Request
  + 401 - Not Authorized
  + 403 - Forbidden
  + 404 - Page Not Found
  + 405 - Method Not Allowed
  + 500 - Internal Service Error
  + 503 - Service Unavailable
* HTTP Request Headers
  + Host
  + User-Agent
  + Content-Length
  + Accept-Encoding
  + Cookies
* HTTP Response Headers
  + Set-Cookie
  + Cache-Control
  + Content-Type
  + Content-Encoding
