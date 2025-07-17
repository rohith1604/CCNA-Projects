Basic LAN Setup with IP Addressing and Subnetting
Project Overview
This project demonstrates the configuration of a Local Area Network (LAN) for 20 users using Cisco Packet Tracer. The network is designed for a single department, with IP addressing and subnetting configured to ensure seamless communication. A Cisco router serves as the default gateway, and connectivity is verified using ping commands.
Objectives

Design a LAN to support 20 users.
Configure IP addressing with proper subnetting.
Set up a Cisco router as the default gateway.
Verify network connectivity using ping commands.
Document the configuration process.

Topology

Devices:
1 Cisco Router (2911)
1 Switch (2950)
20 PCs


Connections:
PCs connected to the switch using Copper Straight-Through cables.
Switch connected to the router's GigabitEthernet0/0 interface.


IP Addressing:
Network: 192.168.1.0/26 (255.255.255.192)
Router (Gateway): 192.168.1.1
PCs: 192.168.1.2 to 192.168.1.21
Switch (VLAN 1, for management): 192.168.1.22
Usable IP Range: 192.168.1.1–192.168.1.62
Broadcast Address: 192.168.1.63



Prerequisites

Cisco Packet Tracer: Version 7.3 or later recommended.
Basic Knowledge: Understanding of IP addressing, subnetting, and Cisco IOS commands.

Setup Instructions
Step 1: Download the Project

Clone this repository or download the .pkt file:git clone <repository-url>


Open the Basic_LAN_Setup.pkt file in Cisco Packet Tracer.

Step 2: Network Topology

Add Devices:
Place 20 PCs (PC0 to PC19), 1 Switch (2950), and 1 Router (2911) in the Packet Tracer workspace.


Connect Devices:
Connect each PC's FastEthernet0 to the switch's FastEthernet0/1 to FastEthernet0/20 using Copper Straight-Through cables.
Connect Switch0 FastEthernet0/24 to Router0 GigabitEthernet0/0 using a Copper Straight-Through cable.



Step 3: Configure IP Addressing

PCs:
For each PC (PC0 to PC19):
Go to Desktop > IP Configuration.
Assign:
IPv4 Address: 192.168.1.2 (increment for each PC, up to 192.168.1.21)
Subnet Mask: 255.255.255.192
Default Gateway: 192.168.1.1






Router:
Access Router0's CLI:enable
configure terminal
interface GigabitEthernet0/0
ip address 192.168.1.1 255.255.255.192
no shutdown
exit
write memory




Switch (Optional, for Management):
Access Switch0's CLI:enable
configure terminal
interface vlan 1
ip address 192.168.1.22 255.255.255.192
no shutdown
exit
ip default-gateway 192.168.1.1
write memory





Step 4: Verify Connectivity

Ping Tests:
From PC0's Command Prompt, ping another PC (e.g., PC1):ping 192.168.1.3


Ping the default gateway:ping 192.168.1.1


Repeat from other PCs to confirm connectivity.


Simulation Mode:
Switch to Simulation mode in Packet Tracer.
Send a Simple PDU from PC0 to PC19 to visualize packet flow.
Verify successful packet delivery.



Step 5: Documentation

IP Assignment Table:



Device
IP Address
Subnet Mask
Default Gateway



Router0
192.168.1.1
255.255.255.192
-


PC0
192.168.1.2
255.255.255.192
192.168.1.1


PC1
192.168.1.3
255.255.255.192
192.168.1.1


...
...
...
...


PC19
192.168.1.21
255.255.255.192
192.168.1.1


Switch0
192.168.1.22
255.255.255.192
192.168.1.1



Save the .pkt file and include it in the repository.


Running the Project

Open Basic_LAN_Setup.pkt in Cisco Packet Tracer.
Verify configurations as per the setup instructions.
Run ping tests to confirm connectivity.
Use Simulation mode to observe packet flow if needed.

Troubleshooting

Ping Fails:
Check IP addresses, subnet masks, and default gateways on PCs.
Ensure Router0's GigabitEthernet0/0 is active (no shutdown).
Verify cable types (use Copper Straight-Through).


Simulation Issues:
Ensure all devices are powered on and interfaces are up.
Check for correct IP assignments.



Repository Contents

Basic_LAN_Setup.pkt: Cisco Packet Tracer project file.
README.md: This documentation file.
