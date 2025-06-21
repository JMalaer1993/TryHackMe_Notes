# Network Fundamentals
 * Network - A network is just devices that are connected.
 * Internet - The internet is just a giant network made up of many tiny networks.
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
 * Topologies - LANS can be arranged in different topologies, each with their own set of advantages and disadvantages.
    + Star - Each device is connected directly to a central device such as a switch. Most reliable but also most expensive.
    + Bus - Bus topology connects all devices to a single central communication line (the "bus" or backbone cable). It’s cheap and simple, but performance degrades as more devices are added due to network congestion (traffic jams). There's no redundancy. The backbone cable is a single point of failure. If the backbone cable is damaged, the entire network goes down.
    + Ring - Devices are connected directly to eachother forming a loop. Less susceptible to congestion, but a single break in the circuit or a failure of a single device breaks the network.
 * Switch - Used within LANs to connect mutiple devices like printers, computers, and servers. They can even be daisy-chained, or connected to other switches. The often keep track of which device is connected to which port.
 * SNMPv3 - Simple Network Management Protocol is used to MONITOR and manage devices within a LAN, such as switches, routers, and printers. SNMPv1 and v2 are not secure because they send data in cleartext, but SNMPv3 uses authentication and encryption, making it secure.
 * Router - A router just routes data based on a routing table. You can think of routers like thousands of Tron style baseball players standing in an a massive field. Their job is to catch and throw the ball from baseball player to baseball player in the optimal path until the ball reaches its intended destination. If a player drops the ball, that's called a packet loss. There's balls contantly flying everywhere in every direction.
 * Subnetting - Dividing a network into smaller networks within itself. Devices on the same subnet can communicate directly with eachother, but devices on different subnets have to communicate through a router.
   + Subnet Mask - Each subnet is assigned a subnet mask which is an IP address used to identify that subnet.
