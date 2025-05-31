# Security Architecture

## Network Segmentation

- VLAN 10: Staff (Doctors, Admin, IT)
- VLAN 20: Nurses / Medical Devices
- VLAN 30: Guest Wi-Fi (Internet only, no LAN access)

## Firewall

- pfSense with:
  - Default deny inbound
  - Allow necessary outbound services (DNS, HTTPS)
  - Restrict inter-VLAN traffic
  - VPN server (OpenVPN)

## VPN

- OpenVPN server (hosted on pfSense)
- Secure remote access for approved users
- MFA required for VPN login
- Encrypted tunnel (AES-256)

## IDS/IPS

- Suricata running on dedicated Linux server
- Monitors VLAN 10 and VLAN 20 traffic
- Sends alerts to syslog server

## Endpoint Security

- HP Laptops:
  - BitLocker full disk encryption
  - Windows Defender or CrowdStrike
  - MFA on user accounts
- iPads:
  - Enforced encryption
  - MDM enrollment
  - MFA on EMR app

## Identity & Access Management

- Role-based access controls (RBAC) for EMR and internal systems
- Centralized authentication (Azure AD / local AD hybrid)
- Least privilege principle enforced
- MFA on all user accounts

## Monitoring & Logging

- Centralized syslog server collects logs from:
  - pfSense
  - Suricata
  - Windows event logs
  - VPN access logs
- Regular log review by IT staff