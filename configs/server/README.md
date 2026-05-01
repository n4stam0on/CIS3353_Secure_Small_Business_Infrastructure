# Server Configuration

This section documents the setup, configuration, and hardening of the Ubuntu web server hosted in the DMZ.

## Overview

The Ubuntu server was initially deployed in an insecure state to demonstrate vulnerabilities. It was later hardened through the implementation of encryption and secure access controls.

## Initial Configuration (Insecure State)

- Ubuntu Server 22.04 deployed in DMZ
- Web server configured to run over HTTP (port 80)
- No encryption enabled
- Password-based SSH authentication allowed

This setup was used to demonstrate:
- Unencrypted traffic exposure
- Vulnerability to interception and attacks

## Security Implementation

### TLS / HTTPS Configuration
- SSL certificate generated
- Web server configured to use HTTPS (port 443)
- HTTP traffic redirected to HTTPS
- Encrypted communication verified

### SSH Hardening
- SSH key pair generated
- Key-based authentication enabled
- Password authentication disabled
- Secure remote access verified

## Service Configuration

| Service | Port | Status |
|---|---|---|
| HTTP | 80 | Redirected to HTTPS |
| HTTPS | 443 | Enabled |
| SSH | 22 | Key-based authentication only |

## Verification

Security improvements were validated by:

- Confirming HTTPS is active in browser
- Verifying encrypted traffic using packet capture
- Testing SSH login using key authentication
- Confirming password login is disabled
- Ensuring HTTP traffic is redirected to HTTPS

## Evidence

Screenshots in this folder include:

Pulled from Issue #5

Screenshot 1 showing Apache webpage is accessed in Microsoft Edge within Windows (LAN Client)
<img width="980" height="726" alt="Image" src="https://github.com/user-attachments/assets/d3739fb0-95f4-4b8d-9339-5139725c8f47" />

Screenshot 2 showing the output of  `curl http://localhost` from Ubuntu 
<img width="1919" height="1117" alt="Image" src="https://github.com/user-attachments/assets/74310ec5-43cc-45ae-9ce2-633b79fe506f" />

Screenshot 3 showing Kali gaining access to the Web Server `curl http://192.168.2.101`
<img width="835" height="662" alt="Image" src="https://github.com/user-attachments/assets/664ea7d4-bd32-48bd-85dc-69619a5b4f77" />

Screenshot 4 showing MariaDB console displaying `SHOW DATABASES;` with `insecure_db`
<img width="776" height="290" alt="Image" src="https://github.com/user-attachments/assets/3d30807f-17c2-4229-a983-524a6f0b4920" />

Screenshot 5 showing MariaDB service status being ACTIVE and RUNNING
<img width="831" height="439" alt="Image" src="https://github.com/user-attachments/assets/0b239ede-a5a3-4168-a623-daff6bc11a42" />

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #6

Screenshot 1 showing use of command `ip a`
<img width="846" height="231" alt="Image" src="https://github.com/user-attachments/assets/6e14a47f-c6e5-438c-a77d-0e7d3d935b17" />

Screenshot 2 showing use of command `ping 192.168.2.1`
<img width="1206" height="677" alt="Image" src="https://github.com/user-attachments/assets/f2c3cec4-bda0-411a-8f60-a2c1b092fdce" />

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #7

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

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #24

Screenshot 1 showing **SSL** module enabled (`a2enmod ssl`) 
 <img width="870" height="251" alt="Image" src="https://github.com/user-attachments/assets/9f917bc4-a70a-4f99-974b-0fc121300935" />

Screenshot 2 showing **SSL** site enabled `(a2ensite default-ssl.conf`)
<img width="581" height="93" alt="Image" src="https://github.com/user-attachments/assets/b039d862-0461-4504-82ce-8cb9de113cb3" />

Screenshot 3-4 showing Updated **SSL** configuration file showing certificate paths
**__OLD__**
<img width="638" height="85" alt="Image" src="https://github.com/user-attachments/assets/77612841-8901-4b39-b150-6036cd483758" />

**__NEW__**
<img width="572" height="55" alt="Image" src="https://github.com/user-attachments/assets/de3eae91-d729-41c5-8491-35206c0fad38" />

Screenshot 5 showing usage of `ls` commands to prove the `.key` and `.crt` existed
<img width="662" height="133" alt="Image" src="https://github.com/user-attachments/assets/146dc413-f89a-46f7-99e4-1d02bd06fb91" />

Screenshot 6 showing Configuration Test showing `Syntax OK`
<img width="833" height="85" alt="Image" src="https://github.com/user-attachments/assets/8dff3169-252e-48d9-91b8-d63e8f3ac792" />

Screenshot 7 showing the Warning page within the Browser using **HTTPS** 
<img width="968" height="660" alt="Image" src="https://github.com/user-attachments/assets/21309281-2df8-4478-9738-c324f106f582" />

Screenshot 8 showing successfully loaded **HTTPS** page after proceeding through Advanced
<img width="951" height="673" alt="Image" src="https://github.com/user-attachments/assets/3d7fd470-42e2-439c-95d9-e700e8113d0f" />

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #25

Screenshot 1 showing the Updated **HTTP** configuration file with the redirect rule
<img width="756" height="541" alt="Image" src="https://github.com/user-attachments/assets/6eabc952-3472-4ff9-a908-0c9be40d3299" />

Screenshot 2 showing the Apache restart confirmation using command `sudo systemctl restart apache2` (Successfully having no errors)
<img width="568" height="78" alt="Image" src="https://github.com/user-attachments/assets/2cb63764-081a-408f-a8da-825239e0f808" />

Video showing how you are being redirected to **HTTPS** whenever you use **HTTP** 
https://github.com/user-attachments/assets/9346e53d-2edb-4654-8eb2-55b7c4db2a22

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #23

Screenshot 1 showing installation of **OpenSSL** / version check
<img width="881" height="600" alt="Image" src="https://github.com/user-attachments/assets/6962a28f-4a1c-41ff-b2bf-4047f85469b4" />

Screenshot 2 showing generation of the certificate process (Country Name, State, etc for setup)
<img width="856" height="476" alt="Image" src="https://github.com/user-attachments/assets/c4c7ed52-06a2-43db-9985-24070e2090f2" />

Screenshot 3 showing verification output of the Certificate `Enabling module ssl`
<img width="870" height="251" alt="Image" src="https://github.com/user-attachments/assets/8404cb18-fd0c-40c7-a3d4-e3a259c19b14" />

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #26

Screenshot 1 showing wireshark capturing on `eth0` 
<img width="866" height="592" alt="Image" src="https://github.com/user-attachments/assets/7991c84d-4260-4bbd-b99f-3d4a16f2a0f2" />

Screenshot 2 showing **HTTPS** page is loaded in browser and showing traffic within wireshark due to refreshing a couple times
<img width="974" height="716" alt="Image" src="https://github.com/user-attachments/assets/3434af63-37e9-440f-8490-1e04c0579eeb" />

Screenshot 3 showing an applied filter `tcp.port == 443` 
<img width="864" height="600" alt="Image" src="https://github.com/user-attachments/assets/765d757b-0a39-405f-8d23-db4b20747a7d" />

Screenshot 4 showing a packet inspection, revealing encrypted data
<img width="1188" height="721" alt="Image" src="https://github.com/user-attachments/assets/9285992c-b9cd-4a1b-8e47-080634fb1b40" />

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #33

Screenshot 1 showing **SSH** key generation output
<img width="631" height="493" alt="Image" src="https://github.com/user-attachments/assets/be31a7f3-db1e-4c07-b745-3248e6a29044" />

Screenshot 2 showing connection refusal error
<img width="714" height="188" alt="Image" src="https://github.com/user-attachments/assets/634b3706-9258-4afb-b294-ebaf3c32633e" />

Screenshot 3 showing the use of command `sudo apt install openssh-server -y` in order to get the service running 
<img width="725" height="116" alt="Image" src="https://github.com/user-attachments/assets/6120268e-3f57-4894-a352-db51e4f43fda" />

Screenshot 4 showing the **SSH** service running
<img width="830" height="459" alt="Image" src="https://github.com/user-attachments/assets/fefa591e-baa4-4779-bbaf-586d0054f85a" />

Screenshot 5 showing the copy of the key being successful
<img width="767" height="370" alt="Image" src="https://github.com/user-attachments/assets/aa1f5e3f-d542-473e-b6f3-37b7f89e72ff" />

Screenshot 6 showing a successful login 
<img width="692" height="591" alt="Image" src="https://github.com/user-attachments/assets/83aaa1f0-5812-46b4-b17c-afd30a360f79" />  

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #34

Screenshot 1-2 showing **SSH** config showing updated settings
**OLD**
<img width="587" height="71" alt="Image" src="https://github.com/user-attachments/assets/9d0f847d-584e-4d24-8031-f7646659bae0" />

**NEW** 
<img width="542" height="83" alt="Image" src="https://github.com/user-attachments/assets/52b7dfb3-62bc-4157-8ee7-e3635770b38c" />

Screenshot 3 showing **SSH** restart confirmation
<img width="489" height="65" alt="Image" src="https://github.com/user-attachments/assets/ad0a32ec-2c13-496d-9665-fdf0a5582e79" />

----------------------------------------------------------------------------------------------------------------------------------

Pulled from Issue #35

Screenshot 1 showing a successful **SSH** login  
<img width="746" height="613" alt="Image" src="https://github.com/user-attachments/assets/0284f7a6-8951-4b0f-adc7-696db8c1c52c" />

Screenshot 2 showing a Failed Login attempt using a different method
<img width="568" height="79" alt="Image" src="https://github.com/user-attachments/assets/b9443c40-b4c2-4bfd-bab0-c7797000e2ff" />
