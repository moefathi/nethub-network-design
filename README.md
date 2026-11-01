# NetHub Network Design
In my project, I designed and implemented a network infrastructure for a company called NetHub that has seven branches located in Vienna, Morocco, Tunis, London, Paris, Rome, and Milan, where the main headquarters and data center are located. The main purpose of this project was to design a network that connects all these branches together, allowing devices in different locations to communicate with each other and access the services provided by the main data center.

## Network Design and Subnetting
In my design, I used a star topology for the LAN connections inside each branch, where all devices are connected to a central switch, and an extended star topology for the Milan location because it contains both the headquarters and the data center. For the WAN connections, I used point-to-point connections between neighbouring routers to connect all seven branches.

For the LAN subnetting, I used the private IP address range 10.0.0.0/8 and divided it into eight subnets using a /23 prefix, providing 510 usable IP addresses for each subnet. I selected this subnet size based on the business requirement that each location is not expected to have more than 500 employees, while also considering future expansion.

For the WAN connections, I used the IP address range 200.0.0.0/24 and divided it into /30 subnets because each point-to-point connection requires two usable IP addresses, one for each router interface. This allowed me to assign separate network addresses to the connections between the branches.

## Network Configuration and Routing
I configured the router interfaces using static IP addressing and enabled OSPF (Open Shortest Path First) to exchange routing information between routers. I selected OSPF because it supports larger networks and allows routers to update their routing information when network changes happen.

I also configured the end devices, including PCs, laptops, printers, and access points. I assigned static IP addresses to devices such as printers and servers, while other devices receive their IP addresses dynamically through DHCP.

## Server Installation and Services
In my design, I installed five dedicated servers in the Milan data center, with each server responsible for one service. These services include DHCP, HTTPS, DNS, FTP, and Email. I separated these services across different servers because having all services running on one server could create a single point of failure, meaning that if the server failed, all the services would become unavailable.

The DHCP server contains seven address pools, allowing devices in the different LAN networks to receive IP addresses dynamically. I also configured DNS to map IP addresses to domain names, HTTPS to provide secure access to the company's internal system, FTP to allow employees to upload and download files, and Email to support sending and receiving messages using SMTP and POP3.

## Testing and Verification
After completing the network configuration, I performed different tests to verify that the network and its services were working correctly. For connectivity, I used the ping command to test communication between devices in the same branch and between devices in different branches.

I also checked the routing tables using the show ip route command to verify the routing information between routers. For service availability, I tested DHCP by requesting dynamic IP addresses, FTP by connecting to the FTP server, HTTPS and DNS by accessing the internal website using its IP address and domain name, and Email by sending and receiving messages between devices.

## Network Evaluation and Future Improvements
In my evaluation, I considered the advantages and limitations of the network design, including the topologies, routing protocol, and communication technologies. I used Ethernet (IEEE 802.3) for wired LAN connections and Wi-Fi (IEEE 802.11) for wireless connections, while OSPF was used for routing between the different branches.

Another thing I considered was how the network could be improved in the future. For example, I suggested implementing firewalls to improve network security, using fibre-optic cables instead of copper cables to support higher bandwidth and longer distances, and considering a mesh topology for WAN connections to provide additional connectivity options.

## Technologies and Protocols Used
- Cisco Packet Tracer
- IPv4 Subnetting
- OSPF
- DHCP
- DNS
- HTTPS
- FTP
- SMTP and POP3
- Ethernet (IEEE 802.3)
- Wi-Fi (IEEE 802.11)

## Project Information
- **Type:** Academic Project
- **Course:** Networking
- **Semester:** Fall 2024/2025

## License
© 2026 Mohammad Aldeghemat. All rights reserved.
