📌 Project Summary

This project demonstrates the implementation and troubleshooting of a complete Active Directory infrastructure lab using Windows Server.

The lab focuses on understanding how DNS and DHCP integrate with Active Directory, and how configuration errors can directly impact domain operations.

This was built and tested in a virtual lab environment (VMware Workstation).

Lab Environment
🔹 Domain Controller

Hostname: DC01

Domain Name: WS.local

IP Address: 192.168.10.10

Roles Installed:

Active Directory Domain Services (AD DS)

DNS Server

DHCP Server

🔹 Client Machine

Receives IP dynamically from DHCP

DNS configured to point to DC01

Successfully joined to the domain


Configuration Breakdown
✅ Active Directory

Promoted server to Domain Controller

Created new forest: WS.local

Verified domain controller discovery via SRV records

Tested domain join from client machine


Forward Lookup Zone: WS.local

Reverse Lookup Zone: 192.168.10.0/24

Verified records:

A Records

PTR Records

SRV Records:

_ldap._tcp.dc._msdcs.ws.local

_kerberos._tcp.dc._msdcs.ws.local

DNS Validation Commands Used:
nslookup dc01.ws.local
nslookup 192.168.10.10
nslookup -type=SRV _ldap._tcp.dc._msdcs.ws.local


DHCP Configuration

Scope Range: 192.168.10.50 – 192.168.10.100

Subnet Mask: 255.255.255.0

DNS Server Option: 192.168.10.10

DHCP Authorization completed successfully

Tested IP assignment using:

ipconfig /release
ipconfig /renew


Testing & Troubleshooting

During the lab, several real-world issues were intentionally tested and resolved:

Client receiving APIPA address (169.254.x.x)

Domain Join Failure (Error 1355 – No Such Domain)

DNS timeout due to incorrect DNS configuration

DHCP not distributing IP addresses

Missing PTR records in Reverse Lookup Zone

Each issue was diagnosed and resolved to simulate enterprise troubleshooting scenarios.

Key Technical Skills Demonstrated

Active Directory deployment

DNS infrastructure design (Forward & Reverse Zones)

SRV record validation

DHCP scope configuration & authorization

Domain Controller discovery process

Network troubleshooting in Windows environments

Outcome

This lab strengthened my understanding of how core Windows infrastructure services interact in an enterprise environment and how to diagnose common deployment failures.

