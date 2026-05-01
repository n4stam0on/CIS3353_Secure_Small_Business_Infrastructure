# Sprint Notes

This folder will contain sprint retrospectives, progress updates, and milestone summaries

Each sprint SHOULD have:
- Goals
- Completed Tasks
- Challenges
- Next Sprint Adjustments

# Progress Within Project
Completed User Story #1
This includes completing sub issues:
- #2
- #3
- #4

Completed User Story #5 (2)
This includes completing sub issues:
- #6
- #7
- #8

Completed User Story #9 (3)
This includes completing sub issues:
- #10
- #11
- #12

Completed User Story #13 (4)
This includes completing sub issues:
- #14
- #15
- #17

Inputted Analysis of Captured Traffic within User Issue #21
Documented Captured Traffic findings and Analysis into Wiki Under Threat Demonstration

Completed User Sub Issue #19 Under User Story #18 (5)
Completed User Sub Issue #20 Under User Story #18 (5)
Completed User Sub Issue #21 Under User Story #18 (5)
Completed User Story #18 (5)

Completed User Sub Issue #23 Under User Story #22 (6)
Completed User Sub Issue #24 Under User Story #22 (6)
Completed User Sub Issue #25 Under User Story #22 (6)
Completed User Sub Issue #26 Under User Story #22 (6)
Completed User Story #22 (6)

Completed User Sub Issue #33 Under User Story #32 (7)
Completed User Sub Issue #34 Under User Story #32 (7)
Completed User Sub Issue #35 Under User Story #32 (7)
Completed User Story #32 (7)

Completed User Sub Issue #37 Under User Story #36 (8)
Completed User Sub Issue #38 Under User Story #36 (8)
Completed User Sub Issue #39 Under User Story #36 (8)
Completed User Story #36 (8)

Completed User Sub Issue #41 Under User Story #40 (9)
Completed User Sub Issue #42 Under User Story #40 (9)
Completed User Sub Issue #43 Under User Story #40 (9)
Completed User Story #40 (9)

Wiki completely formatted and finalized


# Sprint Notes

This section documents sprint progress, completed work, and associated user stories.

---

## Sprint 1 – Project Setup & Infrastructure

### Goals
- Set up repository and project structure
- Configure virtual machines
- Deploy pfSense and segment network

### Completed Tasks
- pfSense installed and configured (WAN/LAN/DMZ)
- Ubuntu server deployed in DMZ
- Basic connectivity verified
- GitHub Wiki structured for documentation and planning

### Completed User Stories
- User Story #1 (1): Deploy pfSense and segment the network  
  - Sub-issues: #2, #3, #4  
- User Story #5 (2): Deploy Ubuntu server in insecure state  
  - Sub-issues: #6, #7, #8  
- User Story #9 (3): Structure GitHub Wiki for documentation and crypto planning  
  - Sub-issues: #10, #11, #12  

### Challenges
- Network adapter confusion in VirtualBox
- Connectivity issues between LAN and DMZ
- Organizing documentation structure early in the project

---

## Sprint 2 – Threat Demonstration (Insecure State)

### Goals
- Demonstrate vulnerabilities
- Perform scanning and packet capture

### Completed Tasks
- HTTP web server deployed (no encryption)
- Nmap scans performed
- Unencrypted traffic captured using Wireshark

### Completed User Stories
- User Story #13 (4): Perform reconnaissance scanning  
  - Sub-issues: #14, #15, #17  
- User Story #18 (5): Capture unencrypted HTTP traffic  
  - Sub-issues: #19, #20, #21  

### Challenges
- Capturing clear packet data
- Ensuring proper VM communication

---

## Sprint 3 – Security Implementation

### Goals
- Secure the environment using encryption and access control

### Completed Tasks
- TLS/HTTPS implemented
- HTTP redirected to HTTPS
- SSH key-based authentication enforced
- Firewall rules configured

### Completed User Stories
- User Story #22 (6): Implement TLS encryption  
  - Sub-issues: #23, #24, #25, #26  
- User Story #32 (7): Enforce SSH key authentication  
  - Sub-issues: #33, #34, #35  
- User Story #36 (8): Harden pfSense firewall rules  
  - Sub-issues: #37, #38, #39  

### Challenges
- Troubleshooting HTTPS configuration
- SSH configuration errors

---

## Sprint 4 – Verification & Documentation

### Goals
- Validate security improvements
- Finalize documentation

### Completed Tasks
- Vulnerability scan re-run
- Verified encrypted traffic
- Documentation and slides completed

### Completed User Stories
- User Story #40 (9): Re-run vulnerability scan  
  - Sub-issues: #41, #42, #43  
- User Story 10: Finalize documentation  
  - Sub-issues: #45, #46, #47

### Challenges
- Organizing documentation across repo
- Matching screenshots to configurations

---

## Overall Progress

- All user stories completed and validated
- Secure network successfully implemented
- Documentation finalized for presentation
