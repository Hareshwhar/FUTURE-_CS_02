# FUTURE-_CS_02

# UFW Configuration for Kali Linux

This document provides an overview of the UFW (Uncomplicated Firewall) rules configured on this Kali Linux system.

## Firewall Rules Overview

The following UFW rules have been set up to control network traffic on this system:

| Port/Service             | Action | From                        | To                            | Protocol        |
|--------------------------|--------|-----------------------------|-------------------------------|-----------------|
| 22 (SSH)                 | ALLOW  | Anywhere                    | Anywhere                      | TCP             |
| 443 (HTTPS)              | ALLOW  | Anywhere                    | Anywhere                      | TCP             |
| 80 (HTTP)                | ALLOW  | Anywhere                    | Anywhere                      | TCP             |
| Anywhere                 | ALLOW  | 192.168.0.1                 | Anywhere                      | All             |
| 3306/tcp (MySQL)         | ALLOW  | Anywhere                    | Anywhere                      | TCP             |
| 22 (v6) (SSH)            | ALLOW  | Anywhere (v6)               | Anywhere (v6)                 | TCP (IPv6)      |
| 443 (v6) (HTTPS)         | ALLOW  | Anywhere (v6)               | Anywhere (v6)                 | TCP (IPv6)      |
| 80 (v6) (HTTP)           | ALLOW  | Anywhere (v6)               | Anywhere (v6)                 | TCP (IPv6)      |
| 3306/tcp (v6) (MySQL)    | ALLOW  | Anywhere (v6)               | Anywhere (v6)                 | TCP (IPv6)      |

## Detailed Explanation of Rules

### 1. SSH Access (Port 22)
- **Port/Protocol**: 22/TCP
- **Action**: ALLOW
- **From**: Anywhere (IPv4 and IPv6)
- **Description**: Allows SSH connections from any IP address. This is necessary for remote management of the system.

### 2. HTTPS Access (Port 443)
- **Port/Protocol**: 443/TCP
- **Action**: ALLOW
- **From**: Anywhere (IPv4 and IPv6)
- **Description**: Allows secure web traffic over HTTPS from any IP address.

### 3. HTTP Access (Port 80)
- **Port/Protocol**: 80/TCP
- **Action**: ALLOW
- **From**: Anywhere (IPv4 and IPv6)
- **Description**: Allows unsecured web traffic over HTTP from any IP address.

### 4. MySQL Access (Port 3306)
- **Port/Protocol**: 3306/TCP
- **Action**: ALLOW
- **From**: Anywhere (IPv4 and IPv6)
- **Description**: Allows MySQL database connections from any IP address.

### 5. Specific Network Access (192.168.0.1)
- **From**: 192.168.0.1
- **To**: Anywhere
- **Action**: ALLOW
- **Description**: Allows all incoming traffic from the IP address 192.168.0.1, which could be a trusted internal network.

## Notes

- **v6**: The rules that specify `(v6)` apply to IPv6 traffic.
- **Security Consideration**: Make sure to review the allowed rules regularly to ensure that only necessary services are exposed.

## How to Modify UFW Rules

To view the current UFW status and rules, run:
```bash
sudo ufw status verbose


**Kali Linux Official Documentation: Kali's official docs include information on managing security tools, including UFW.**
