# Network Configuration

This directory documents the network design and configuration used for the secure small business infrastructure project.

## Overview

The lab environment was designed using a segmented network model with separate WAN, LAN, and DMZ zones. pfSense was used as the firewall and routing device to control traffic between each network segment.

## Network Zones

| Zone | Purpose | Example Use |
|---|---|---|
| WAN | Provides external/internet access | NAT / Internet connection |
| LAN | Internal trusted network | Windows client system |
| DMZ | Isolated server network | Ubuntu web server |

## IP Addressing Plan

| Network | Subnet / Addressing | Description |
|---|---|---|
| WAN | DHCP / NAT | External access through VirtualBox NAT |
| LAN | 192.168.1.0/24 | Internal client network |
| DMZ | 192.168.2.0/24 | Server network for Ubuntu web server |

## VirtualBox Network Setup

| VM | Adapter 1 | Adapter 2 | Adapter 3 |
|---|---|---|---|
| pfSense | NAT / WAN | LAN_NET | DMZ_NET |
| Windows Client | LAN_NET | N/A | N/A |
| Ubuntu Server | DMZ_NET | N/A | N/A |
| Kali Linux | DMZ_NET | N/A | N/A |

## Segmentation Strategy

The network was segmented to separate internal users from public-facing services.

- LAN systems are separated from DMZ systems
- Ubuntu web server is placed inside the DMZ
- pfSense controls traffic between WAN, LAN, and DMZ
- DMZ to LAN communication is restricted to prevent lateral movement

## Traffic Flow

| Traffic Path | Status | Purpose |
|---|---|---|
| LAN → WAN | Allowed | Internal internet access |
| LAN → DMZ | Controlled | Client access to web server |
| WAN → DMZ | Controlled | External access to hosted services |
| DMZ → LAN | Blocked | Prevent unauthorized access to internal systems |

## Verification

Network configuration was verified by:

- Confirming pfSense interface assignments
- Testing LAN connectivity
- Testing DMZ server reachability
- Verifying Ubuntu server was reachable from client systems
- Confirming network segmentation with firewall testing

## Evidence

Screenshots in this folder should include:

Pulled from Issue #2

Screenshot 1 Shows pfSense is installed
<img width="794" height="84" alt="Image" src="https://github.com/user-attachments/assets/2307b108-ba00-4906-b145-e091cf60913c" />

Screenshot 2 in Network showing the NAT adapter
<img width="698" height="378" alt="Image" src="https://github.com/user-attachments/assets/d6ffee88-815f-48bb-90e4-046458c3cc4d" />

Screenshot 3 in Network showing the LAN-Net adapter
<img width="696" height="370" alt="Image" src="https://github.com/user-attachments/assets/e013c3bc-fa25-4447-aa33-8da992bf3336" />

Screenshot 4 shows the menu when pfSense is launched
<img width="823" height="487" alt="Image" src="https://github.com/user-attachments/assets/11024f2d-ca14-46e9-b72b-e14ec50b1825" />

Screenshot 5 of pfSense web interface on Windows 10 Virtual Machine
<img width="1129" height="816" alt="Image" src="https://github.com/user-attachments/assets/602d41dc-8e5d-4b08-abe8-9657fb4ad9a5" />

Screenshot 6 shows dashboard in pfSense website
<img width="1093" height="824" alt="Image" src="https://github.com/user-attachments/assets/599fe9f2-1c80-4a80-952e-98628ae97846" />

-----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #3

Screenshot 1 shows pfSense WAN interface successfully obtains internet connectivity via NAT (ping to 8.8.8.8 successful)
<img width="873" height="502" alt="Image" src="https://github.com/user-attachments/assets/23bf66e0-e3b2-4a8b-a540-d948d95ae21b" />

Screenshot 2 shows LAN client receives proper IP addressing from pfSense DHCP (192.168.1.100 with gateway 192.168.1.1)
<img width="1110" height="826" alt="Image" src="https://github.com/user-attachments/assets/4a46d6fb-82bc-4bd6-b652-6b7034d6c5ec" />

Screenshot 3 shows LAN client successfully reaches the internet through pfSense (ping to 8.8.8.8 successful)
<img width="563" height="198" alt="Image" src="https://github.com/user-attachments/assets/6c354bc3-a1c6-4806-a7e8-4af15392212d" />

-----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #4
Screenshot 1 shows pfSense interface assignments showing WAN (em0), LAN (em1), and DMZ (OPT1/em2) configured on separate interfaces.
<img width="1152" height="826" alt="Image" src="https://github.com/user-attachments/assets/4b50898b-57b0-4fd3-9929-befd45a18077" />

Screenshot 2 shows Ubuntu web server assigned to the DMZ network with IP address 192.168.2.101/24, confirming placement in the isolated DMZ subnet.
<img width="840" height="269" alt="Image" src="https://github.com/user-attachments/assets/2ee34d2f-18fc-4acf-be8f-3c19b277349f" />

Screenshot 3 showsDMZ host attempted to ping LAN client (192.168.1.100). 100% packet loss confirms pfSense firewall blocks DMZ-to-LAN traffic, validating network segmentation.
<img width="725" height="136" alt="Image" src="https://github.com/user-attachments/assets/77e0f02c-e026-42b7-b021-8faccae84f29" />

-----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #8
Screenshot 1 showing Windows browser accessing `http://192.168.2.101` (Apache page + showing its "Not Secure")
<img width="1206" height="1015" alt="Image" src="https://github.com/user-attachments/assets/2df945bf-0a5e-4406-a731-59f901607699" />

Screenshot 2-4 showing Kali Terminal (The attacker machine) being able to access the webpage using `curl http://192.168.2.101` and showing the output (The output should be showing the HTML line for the web page)
<img width="876" height="768" alt="Image" src="https://github.com/user-attachments/assets/16ffd7f6-cb69-4cb3-92d8-53f9f3e6072b" />
<img width="870" height="780" alt="Image" src="https://github.com/user-attachments/assets/7286fb8a-781a-4b78-8278-3fa3f024028b" />
<img width="878" height="770" alt="Image" src="https://github.com/user-attachments/assets/c0735d6d-f46a-49c8-b758-4771e2ed105c" />

Screenshot 5 showing Ubuntu Terminal being able to successfully ping to `192.168.2.1`
<img width="711" height="305" alt="Image" src="https://github.com/user-attachments/assets/1faab5f7-55a0-4112-b280-d04aa1de4332" />

Screenshot 6 showing pfSense being able to ping to `192.168.2.1`
<img width="797" height="464" alt="Image" src="https://github.com/user-attachments/assets/54abb9be-05fc-4185-9699-35b8ab6d0637" />
