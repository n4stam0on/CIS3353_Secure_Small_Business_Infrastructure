# Final Report Draft

## Executive Summary

This project demonstrates the process of building a vulnerable network environment and progressively securing it using industry-standard security practices. The environment begins in an intentionally insecure state, exposing services such as HTTP, and is later hardened through the implementation of HTTPS encryption, SSH key-based authentication, and firewall segmentation. The goal is to showcase both offensive and defensive security techniques in a controlled lab setting.

---

## Architecture Overview

The network was designed using a segmented model consisting of WAN, LAN, and DMZ zones. pfSense was used as the firewall and routing device to manage traffic between these segments. The Ubuntu web server was placed in the DMZ to simulate a public-facing service, while a Windows client system resided in the LAN. This structure reflects a real-world small business network design.

---

## Threat Demonstration

The environment was initially configured in an insecure state to demonstrate potential vulnerabilities. The web server was deployed over HTTP, allowing traffic to be transmitted in plaintext. Using Kali Linux, reconnaissance scans were performed to identify open ports and exposed services. Wireshark was then used to capture unencrypted traffic, demonstrating how sensitive data could be intercepted.

---

## Defense Implementation

Security measures were implemented to mitigate the identified risks. TLS encryption was configured on the web server, enabling HTTPS and ensuring secure communication. HTTP traffic was redirected to HTTPS to prevent insecure access. SSH access was hardened by enforcing key-based authentication and disabling password logins. Additionally, pfSense firewall rules were configured to enforce strict segmentation between WAN, LAN, and DMZ networks.

---

## Verification Results

After implementing security controls, validation steps were performed to confirm improvements. A second vulnerability scan was conducted to verify that previously exposed services were secured. Packet capture analysis confirmed that traffic was encrypted and no longer readable. Firewall rules were tested to ensure unauthorized access between network segments was blocked.

---

## Conclusion

The project successfully demonstrated the full lifecycle of building, attacking, and defending a network environment. By transitioning from an insecure configuration to a secured system, it highlights the importance of encryption, access control, and network segmentation in protecting sensitive data and preventing unauthorized access.
