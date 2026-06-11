## Wireshark Packet Analysis Lab

### Overview
- This lab demonstrates packet capture and traffic analysis using Wireshark in a Windows Server Active Directory lab environment.
- The goal of this lab was to capture and analyze common network protocols including ARP, DNS, DHCP, ICMP, and TCP.

------------------------------------------------------------
### Lab Environment
- Server Name: DC1
- Server OS: Windows Server 2022
- Client Name: PC1
- Client OS: Windows 11
- Domain: amir.local
- Network: VirtualBox Internal Network - AD-Lab

------------------------------------------------------------
### IP Addressing
- DC1 IP Address: 192.168.10.10
- PC1 IP Address: DHCP assigned
- DNS Server: 192.168.10.10
- DHCP Server: 192.168.10.10

------------------------------------------------------------
### Protocols Captured
- ARP
- DNS
- DHCP
- ICMP
- TCP

------------------------------------------------------------
### Wireshark Filters Used
- arp
- dns
- dhcp
- bootp
- icmp
- tcp
- tcp.port == 445
- ip.addr == 192.168.10.10

------------------------------------------------------------
### Screenshots

#### ARP Capture:
- [001-wireshark-interface-selected.png](https://github.com/asamandi/Wireshark-Packet-Analysis-Lab/blob/main/Screenshots/001-wireshark-interface-selected.png)
- 002-arp-capture.png

#### DNS Capture:
- 003-dns-query-response.png

#### DHCP Capture:
- 004-dhcp-dora-capture.png

#### ICMP Capture:
- 005-icmp-ping-capture.png

#### TCP Capture:
- 006-tcp-handshake-smb.png

#### Filter IP Address:
- 007-filter-ip-addr.png

#### Filter Examples:
- 008-filter-examples.png

#### Final Verification:
- 009-final-verification-01.png
- 009-final-verification-02.png
- 009-final-verification-03.png

------------------------------------------------------------
### Skills Demonstrated
- Wireshark packet capture
- Protocol analysis
- ARP request and reply analysis
- DNS query and response analysis
- DHCP DORA process analysis
- ICMP echo request and echo reply analysis
- TCP three-way handshake analysis
- SMB traffic identification
- Display filter usage
- Network troubleshooting verification

------------------------------------------------------------
### Verification Commands
- ipconfig /all
- arp -d *
- ping 192.168.10.10
- ping dc1
- ipconfig /flushdns
- nslookup amir.local
- nslookup dc1.amir.local
- nslookup fileserver.amir.local
- ipconfig /release
- ipconfig /renew
- dir \\DC1\IT

------------------------------------------------------------
### Troubleshooting Notes

### Issue:
- No packets appear in Wireshark.

Cause:
- The wrong network adapter may be selected.

Fix:
- Select the active Ethernet adapter and restart the capture.

### Issue:
- DNS traffic does not appear.

Cause:
- DNS results may be cached.

Fix:
- Run ipconfig /flushdns, then run nslookup again.

### Issue:
- DHCP traffic does not appear.

Cause:
- The client may already have a valid DHCP lease.

Fix:
- Run ipconfig /release and ipconfig /renew while Wireshark is capturing.

### Issue:
- TCP handshake does not appear.

Cause:
- The SMB session may already be open.

Fix:
- Close File Explorer, restart the capture, then open \\DC1\IT again.

------------------------------------------------------------
### Final Result
- Wireshark successfully captured and analyzed ARP, DNS, DHCP, ICMP, and TCP traffic. The lab verified client connectivity, DNS resolution, DHCP address assignment, and SMB TCP communication with the Windows Server.
- This lab demonstrates practical packet analysis and network troubleshooting skills using Wireshark.
