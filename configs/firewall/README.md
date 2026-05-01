# Firewall Configuration

This directory contains documentation and configuration details for the pfSense firewall used in this project.

## Overview
The firewall is used to enforce network segmentation between WAN, LAN, and DMZ environments. Rules were configured to control traffic flow and prevent unauthorized access between network segments.

## Key Configurations
- Allowed outbound traffic from LAN to WAN
- Blocked traffic from DMZ to LAN
- Restricted unnecessary inbound connections from WAN
- Controlled access to the Ubuntu web server in the DMZ

## Security Purpose
These firewall rules were implemented to:
- Enforce network segmentation
- Reduce attack surface
- Prevent lateral movement between network zones
- Protect internal systems from external and DMZ-based threats

## Verification
Firewall effectiveness was tested by:
- Attempting connectivity between restricted zones
- Running scans from Kali Linux
- Confirming blocked and allowed traffic behavior

## Evidence
Screenshots and rule exports demonstrating firewall configurations and test results are included in this folder.

> Pulled from Sub Issue #3
Screenshot shows pfSense WAN interface successfully obtains internet connectivity via NAT (ping to 8.8.8.8 successful)
<img width="873" height="502" alt="Image" src="https://github.com/user-attachments/assets/23bf66e0-e3b2-4a8b-a540-d948d95ae21b" />

Screenshot shows LAN client receives proper IP addressing from pfSense DHCP (192.168.1.100 with gateway 192.168.1.1)
<img width="1110" height="826" alt="Image" src="https://github.com/user-attachments/assets/4a46d6fb-82bc-4bd6-b652-6b7034d6c5ec" />

Screenshot shows LAN client successfully reaches the internet through pfSense (ping to 8.8.8.8 successful)
<img width="563" height="198" alt="Image" src="https://github.com/user-attachments/assets/6c354bc3-a1c6-4806-a7e8-4af15392212d" />

----------------------------------------------------------------------------------------------------------------------------------

> Pulled from Sub Issue #37
Screenshot 1 showing the **LAN** rules page
<img width="1011" height="582" alt="Image" src="https://github.com/user-attachments/assets/e2b1f167-346b-445c-907f-8dd4f1eb8b77" />

Screenshot 2 showing  New restricted rule configuration
<img width="830" height="591" alt="Image" src="https://github.com/user-attachments/assets/77b9cf30-5b7b-4627-996a-12deccc8e3cf" />

Screenshot 3 showing the confirmation of the applied firewall rules
<img width="988" height="354" alt="Image" src="https://github.com/user-attachments/assets/a70e9ec5-22fc-47da-befe-d2f26a2cceb4" />

----------------------------------------------------------------------------------------------------------------------------------

> Pulled from Sub Issue #38
Screenshot 1 showing changes of **OPT1** to **DMZ** were applied
<img width="689" height="302" alt="Image" src="https://github.com/user-attachments/assets/478c9a51-9796-48a7-ab26-ca5957473b04" />

Screenshot 2 showing the **DMZ** rule page
 <img width="969" height="319" alt="Image" src="https://github.com/user-attachments/assets/ae762437-2c56-4bda-97d6-4848d93ac7a2" />

Screenshot 3 showing Block rule configuration
<img width="978" height="341" alt="Image" src="https://github.com/user-attachments/assets/c1359faf-649f-407b-abc6-f4f2c48ded8c" />

Screenshot 4 showing the rules configuration being applied
<img width="933" height="120" alt="Image" src="https://github.com/user-attachments/assets/15985a8b-2fde-4af1-9aa5-5edfde3086da" />

----------------------------------------------------------------------------------------------------------------------------------

> Pulled from #39
Screenshot 1 showing successfuly internet access from **LAN** within Windows Client VM
<img width="1000" height="623" alt="Image" src="https://github.com/user-attachments/assets/70194c16-494c-4f19-9b25-59111110eb2f" />

Screenshot 2 showing a Failed ping from **DMZ** to **LAN**
<img width="622" height="206" alt="Image" src="https://github.com/user-attachments/assets/91f463de-fbc8-4b2c-b0b9-7cc74e0dd2ee" />

Screenshot 3 showing Windows PowerShell output showing failed port test
<img width="636" height="251" alt="Image" src="https://github.com/user-attachments/assets/e1ba3e85-713d-4c14-8927-55f035c21524" />
