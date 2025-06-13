# Network Fundamentals
 * Network - A network is just devices that are connected.
 * Internet - The internet is just a giant network made up of many tiny networks.
    + Private Networks - These tiny networks are called private networks.
    + Public Networks - The private networks are connected through public networks.
 * WWW - World Wide Web. Invented by Tim Berners-Lee in 1989.
 * IP (Internet Protocol) Address - A temporary address assigned to a device on a network. Private IP addresses are assigned to devices within a private network while public IP adresses assigned to devices on the internet. There cannot be the same private IP address assigned to different devices simultaneiously on the same private network. However, two devices that share a private network could share the same public IP address.
   + IPv4 - Consists of 4 octets.
   + IPv6 - Allows for WAY more devices on the internet.
 * NAT - Network Address Translation converts private IP addresses to public IP addresses and vice versa.
    + SNAT - Source Network Address Translation.
    + DNAT - Destination Network Address Translation.
 * PAT - Port Address Translation is a type of NAT that maps multiple private IP addresses to one public IP address using different ports.
 * MAC (Media Access Control) Address - A permanent address assigned to a device on a network, like a fingerprint. Consists of 12 characters in hexadecimal format.
    + Spoofing - MAC addresses can be "spoofed." This is kind of like identity theft. This occurs when a device pretends to be another device by using its MAC address. One might spoof their MAC address to access resources available to other devices.
 * NIC - Network Interface Card. MAC addresses are assigned to the NIC on each device.
 * ISP - Internet Service Proividers assign public IP addresses to devices for a fee.
