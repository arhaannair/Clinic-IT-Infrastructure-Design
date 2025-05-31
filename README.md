# Healthcare Clinic IT Infrastructure Design

## 📋 Project Overview

Designed a secure IT infrastructure for a small healthcare clinic (~20 users).  
Emphasis on secure networking, access controls, data protection, and operational resilience.

---

## 🏥 Clinic Environment

- Users (~20 total):
  - 5 Doctors
  - 10 Nurses
  - 3 Administrative staff
  - 2 IT staff
- Devices:
  - 25 HP laptops (one per user + surplus)
  - 15 iPads (10 for nurses + 5 surplus)
  - 3 HP LaserJet printers
  - 10 Cisco VoIP phones (doctors, admin, IT)
- Core applications:
  - EMR system: OpenEMR
  - Office suite
  - Secure email
  - VPN for remote access

---

## 🌐 Network Design

**Key components:**
- VLAN segmentation:
  - VLAN 10: Staff (Doctors, Admin, IT)
  - VLAN 20: Nurses / Medical Devices
  - VLAN 30: Guest Wi-Fi
- Firewall:
  - pfSense with strict ingress/egress rules
- VPN:
  - OpenVPN for secure remote access
- IDS/IPS:
  - Suricata (open-source IDS)
- Centralized logging:
  - Syslog server

*[See network diagram → NetworkDiagram.png](NetworkDiagram.png)*

---

## VLAN Summary

| VLAN | Purpose | Typical Devices |
|------|---------|-----------------|
| VLAN 10 | Staff (Doctors, Admin, IT) | HP Laptops, Cisco VoIP Phones, HP LaserJet Printers (3) |
| VLAN 20 | Nurses / Medical Devices | iPads (Nurses), iPads (Surplus), Medical Devices (optional) |
| VLAN 30 | Guest Wi-Fi | Guest Wi-Fi Access Point, Guest Devices (BYOD) |


---

## 🛡️ Security Architecture

See [`SecurityArchitecture.md`](SecurityArchitecture.md).

---

## 💾 Backup & Disaster Recovery

See [`Backup_DisasterRecovery.md`](Backup_DisasterRecovery.md).

---

## 👥 User Onboarding / Offboarding

**Onboarding:**
- Device provisioning (encryption, MFA, AV)
- Role-based access controls
- VPN setup (if remote)

**Offboarding:**
- Immediate account deactivation
- Device return & wipe
- Audit log review

---

## 🚀 Tools Used

| Purpose          | Tools                    |
| ---------------- | ------------------------ |
| Network diagram  | draw.io (diagrams.net)    |
| Documentation    | Markdown (VSCode)        |
| Firewall         | pfSense                  |
| VPN              | OpenVPN                  |
| IDS              | Suricata                 |
| Logging          | Syslog server            |
| Backup           | AWS + NAS                |
| Version control  | GitHub                   |

---

*Project by: Arhaan Nair* 🚀