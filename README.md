# Cloudora Account Takeover Investigation

## Overview

This project demonstrates a Tier-1 SOC investigation of a simulated CEO account takeover using **Azure Data Explorer (ADX)** and **Kusto Query Language (KQL)**.

The investigation uses synthetic Entra ID-style sign-in and audit logs created for a controlled cybersecurity lab environment.

> **Disclaimer:** Cloudora is a fictional organization. All users, IP addresses, devices, and security events in this project are simulated and created for educational and portfolio purposes.

---

## Scenario

A suspicious sign-in alert was generated for the CEO account:

**User:** Daniel Reeve  
**Account:** `daniel.reeve@cloudora.io`  
**Role:** CEO

The objective was to determine whether the activity represented a legitimate login or a potential account takeover.

---

## Tools & Technologies

- Azure Data Explorer (ADX)
- Kusto Query Language (KQL)
- Entra ID-style Sign-in Logs
- Audit Logs
- SOC Investigation Methodology

---

## Tier-1 Investigation Process

The investigation followed a standard Tier-1 SOC workflow:

1. Alert validation
2. User activity baseline
3. Suspicious location identification
4. Authentication analysis
5. IP address investigation
6. Device investigation
7. Audit log correlation
8. Incident timeline creation
9. Evidence collection
10. Tier-2 escalation

---

## Key Findings

The investigation identified:

- Multiple failed authentication attempts from Lagos
- Successful authentication following the failed attempts
- High-risk sign-in activity
- Suspicious device: `DEV-ATTACK01`
- Suspicious IP addresses:
  - `197.210.54.21`
  - `105.112.34.77`
- CEO mailbox access
- OAuth application consent
- Registration of security information
- CEO account modification
- Access to a confidential deal folder

### Assessment

**High-confidence suspected account takeover**

The incident was escalated for further Tier-2 investigation.

---

## Investigation Timeline

| Time (UTC) | Activity | Source |
|------------|----------|--------|
| 03:07 | Failed authentication | 197.210.54.21 |
| 03:09 | Failed authentication | 197.210.54.21 |
| 03:10 | Failed authentication | 197.210.54.21 |
| 03:12 | Successful authentication | 197.210.54.21 |
| 03:17 | CEO mailbox accessed | 197.210.54.21 |
| 03:20 | OAuth application consent | 197.210.54.21 |
| 03:22 | Security information registered | 197.210.54.21 |
| 03:26 | CEO account updated | 197.210.54.21 |
| 03:31 | Confidential Deal Folder accessed | 105.112.34.77 |
| 03:34 | Successful authentication | 105.112.34.77 |
| 03:36 | CEO mailbox accessed | 105.112.34.77 |

---

## Indicators of Compromise

| Indicator | Value |
|-----------|-------|
| Account | `daniel.reeve@cloudora.io` |
| Location | Lagos |
| IP Address | `197.210.54.21` |
| IP Address | `105.112.34.77` |
| Device | `DEV-ATTACK01` |
| Operating System | Windows 11 |
| Browser | Chrome 151 |

---

## Tier-1 Assessment

The activity was assessed as a **high-confidence suspected account takeover** based on the combination of abnormal authentication activity, suspicious device and IP addresses, high-risk sign-ins, and sensitive post-authentication actions.

The incident was escalated to **Tier 2** for deeper investigation.

---

## Further Investigation Required

Tier 2 should investigate:

- OAuth application and permissions
- MFA/security information changes
- Account modifications
- Mailbox items accessed
- Confidential files accessed
- Possible data exfiltration
- Initial access method
- Containment and remediation

---

## Skills Demonstrated

- KQL query development
- Azure Data Explorer investigation
- Authentication analysis
- Log correlation
- Incident timeline creation
- IOC identification
- Account takeover investigation
- Tier-1 SOC escalation
- Security incident documentation
