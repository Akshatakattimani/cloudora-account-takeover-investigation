# Tier-1 SOC Incident Escalation

## Incident Title

**HIGH — Suspected CEO Account Takeover**

## Incident Details

| Field | Details |
|---|---|
| Incident ID | CLD-0001 |
| Severity | High |
| Affected Account | daniel.reeve@cloudora.io |
| User Role | CEO |
| Location | Lagos |
| Suspicious IPs | 197.210.54.21, 105.112.34.77 |
| Suspicious Device | DEV-ATTACK01 |
| Status | Escalated to Tier 2 |

---

## Alert Summary

Suspicious authentication activity was identified on the CEO account.

Three failed authentication attempts were observed from IP address `197.210.54.21` between 03:07 and 03:10 UTC, followed by successful authentication at 03:12 UTC.

---

## Key Findings

- Unusual sign-in activity from Lagos
- Multiple failed authentication attempts followed by successful access
- Successful sign-ins marked as high risk
- Suspicious device identified as `DEV-ATTACK01`
- CEO mailbox accessed
- OAuth application consent recorded
- Security information/MFA registration recorded
- CEO account modification recorded
- Confidential Deal Folder accessed
- Activity continued from a second suspicious IP: `105.112.34.77`

---

## Tier-1 Assessment

The activity is assessed as a **high-confidence suspected account takeover**.

The combination of abnormal authentication activity, suspicious IP addresses, high-risk sign-ins, suspicious device activity, and sensitive post-authentication actions indicates potential unauthorized access to the CEO account.

---

## Recommended Escalation

Escalate to Tier 2 for:

- Investigation of the OAuth application and permissions
- Investigation of MFA/security-information changes
- Review of account modifications
- Investigation of mailbox and confidential file access
- Determination of possible data exfiltration
- Identification of the initial access method
- Containment and remediation

---

## Evidence

Investigation evidence and KQL queries are available in the repository.

**Environment:** Azure Data Explorer (ADX)  
**Query Language:** Kusto Query Language (KQL)  
**Dataset:** Synthetic Entra ID-style sign-in and audit logs
