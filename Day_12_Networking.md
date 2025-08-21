Computer Networks Notes
Types of Computers in a Network

Server Computer

Definition: A computer designed to provide services or resources to other computers over a network.
Characteristics:
Equipped with higher RAM, storage, and processing power to handle multiple requests.
Runs specialized software (e.g., web servers, file servers, or database servers).
Often operates 24/7 to ensure availability.


Examples: Web servers (e.g., Apache, Nginx), email servers, file servers.


Client Computer

Definition: A computer that requests access to services or resources provided by a server.
Characteristics:
Typically has lower hardware specifications compared to servers.
Runs client software (e.g., web browsers, email clients) to interact with servers.
Initiates communication by sending requests to servers.


Examples: Personal computers, smartphones, or tablets accessing online services.



Types of Networks
Based on Geographical Scope

LAN (Local Area Network)

Definition: A network confined to a small geographic area, such as a single building, office, or home.
Characteristics:
High-speed connectivity (e.g., 100 Mbps to 10 Gbps).
Low latency and high reliability.
Typically managed by a single organization or individual.
Commonly uses Ethernet or Wi-Fi technologies.


Examples: Home Wi-Fi network, office network.


MAN (Metropolitan Area Network)

Definition: A network that spans a city or a large campus, connecting multiple LANs.
Characteristics:
Covers a larger area than a LAN but smaller than a WAN (e.g., a city or university campus).
Often used by organizations like universities, governments, or large businesses.
Uses fiber-optic cables or high-speed wireless connections.


Examples: City-wide Wi-Fi, university campus network.


WAN (Wide Area Network)

Definition: A network that spans large geographical areas, such as countries or continents.
Characteristics:
Connects multiple LANs and MANs over long distances.
Lower speeds and higher latency compared to LANs due to distance.
Often relies on public infrastructure (e.g., internet, leased lines).


Examples: The Internet, corporate networks across multiple cities.



Peer-to-Peer (P2P) Network

Definition: A network where all computers are equal, with no dedicated server or client roles.
Characteristics:
Each device (peer) can act as both a client and a server, sharing resources directly.
Cost-effective and easy to set up, as no specialized server hardware is required.
Suitable for small-scale environments or file-sharing applications.
Less secure and harder to manage in large networks compared to client-server models.


Examples: BitTorrent, file-sharing networks, small home networks.

IP (Internet Protocol)

Definition: A set of rules for addressing and routing data packets across networks to ensure they reach the correct destination.
Purpose: Provides a unique address (IP address) to identify devices on a network.
Components of an IP Address:
Network Part: Identifies the network to which a device belongs.
Host Part: Identifies a specific device (host) within that network.



IPv4 vs. IPv6



Feature
IPv4
IPv6



Address Length
32 bits (4 bytes)
128 bits (16 bytes)


Format
Decimal (e.g., 192.168.1.1)
Hexadecimal (e.g., 2001:0db8::1)


Address Space
~4.3 billion unique addresses
~340 undecillion addresses


Header Complexity
More complex, with optional fields
Simplified, more efficient


Security
Optional (IPsec support)
Mandatory (built-in IPsec)


Configuration
Manual or DHCP
Stateless auto-configuration (SLAAC)


Usage
Still widely used
Gradually replacing IPv4



Why IPv6? IPv4 addresses are nearly exhausted due to the rapid growth of internet-connected devices. IPv6 provides a vastly larger address space and improved features.

Types of IP Addresses
IP addresses are categorized based on their usage and scope.
Network Classes (IPv4)
IPv4 addresses are divided into classes based on the network size. These are less commonly used today due to Classless Inter-Domain Routing (CIDR), but they are still relevant:

Class A:
Range: 1.0.0.0 to 126.255.255.255
Network bits: 8, Host bits: 24
Used for large networks (e.g., ISPs, large organizations).
Example: 10.0.0.1


Class B:
Range: 128.0.0.0 to 191.255.255.255
Network bits: 16, Host bits: 16
Used for medium-sized networks (e.g., universities).
Example: 172.16.0.1


Class C:
Range: 192.0.0.0 to 223.255.255.255
Network bits: 24, Host bits: 8
Used for small networks (e.g., small businesses).
Example: 192.168.1.1


Class D:
Range: 224.0.0.0 to 239.255.255.255
Used for multicast (group communication).
Example: 224.0.0.1


Class E:
Range: 240.0.0.0 to 255.255.255.255
Reserved for experimental purposes, not used in production.



Reserved IP Addresses

Loopback: Addresses beginning with 127 (e.g., 127.0.0.1) are reserved for loopback and internal testing. They refer to the local device itself.
Network Address: An address with all host bits set to 0 (e.g., 192.168.1.0) identifies the network itself and cannot be assigned to a host.
Broadcast Address: An address with all host bits set to 1 (e.g., 192.168.1.255) is used to send data to all devices in a network.
Private IP Ranges (used in LANs, not routable on the public internet):
Class A: 10.0.0.0 to 10.255.255.255
Class B: 172.16.0.0 to 172.31.255.255
Class C: 192.168.0.0 to 192.168.255.255



Internet vs. Intranet



Feature
Internet
Intranet



Definition
A global network connecting millions of servers and devices worldwide.
A private network within an organization, connecting internal servers and devices.


Scope
Public, accessible to anyone with an internet connection.
Private, restricted to authorized users within an organization.


Access
Uses public IP addresses.
Uses private IP addresses, often behind firewalls.


Examples
Websites like google.com, social media platforms.
Company internal portals, employee databases.


Security
Less secure, exposed to external threats.
More secure, protected by organizational policies and firewalls.


Public vs. Private IP Addresses

Public IP:
Assigned to devices on a WAN (e.g., the internet).
Globally unique and routable across the internet.
Managed by organizations like IANA (Internet Assigned Numbers Authority).
Example: 8.8.8.8 (Google’s DNS server).


Private IP:
Assigned to devices on a LAN (e.g., home or office network).
Not routable on the public internet; used within private networks.
Example: 192.168.1.10 (common in home routers).



Network Address Translation (NAT)

Definition: A technique used to map private IP addresses to a public IP address to allow devices on a private network to access the internet.
Purpose:
Conserves public IP addresses by allowing multiple devices to share a single public IP.
Enhances security by hiding private IP addresses from the external network.


How it Works:
A router or gateway translates private IP addresses to a public IP when sending data to the internet.
It maintains a translation table to route responses back to the correct private IP.


Example:
A device with private IP 192.168.1.10 sends a request to a website.
The router uses NAT to map this to its public IP (e.g., 203.0.113.1) before forwarding the request.
The response is routed back to the router, which uses the NAT table to deliver it to 192.168.1.10.


Types of NAT:
Static NAT: One-to-one mapping of private to public IP (used for hosting servers).
Dynamic NAT: Temporary mapping of private to public IPs from a pool.
PAT (Port Address Translation): Maps multiple private IPs to a single public IP using different port numbers (most common in home routers).


