# Windows Security Event Logs

## Overview

Windows Security Event Logs provide visibility into authentication, account management, object access and other security-relevant activities occurring in the laboratory environment.

These events are used as a source of telemetry for security monitoring and analysis through Wazuh SIEM.

## Relevant Events

| Event ID | Activity | Security relevance |
|---|---|---|
| 4624 | Successful logon | Authentication visibility |
| 4625 | Failed logon | Detection of repeated authentication failures |
| 4740 | Account locked out | Detection of account lockout activity |
| 4720 | User account created | Monitoring of identity changes |
| 4728 | Member added to security-enabled global group | Monitoring of privilege/group membership changes |
| 4729 | Member removed from security-enabled global group | Monitoring of group membership changes |
| 4663 | Object access | Monitoring of access to securable objects |
| 4103 | PowerShell module logging | PowerShell activity visibility |
| 4104 | PowerShell script block logging | Visibility into executed PowerShell script blocks |

## Authentication Monitoring

Authentication events are used to identify successful and unsuccessful logon activity.

### Event ID 4624

Successful authentication events provide information that can be used to establish a timeline of user activity.

Relevant information may include:

- Account
- Host
- Logon type
- Timestamp
- Source information

### Event ID 4625

Failed authentication events are particularly useful when investigating repeated authentication attempts.

Potential analysis includes:

- Number of failed attempts
- Target account
- Source host or IP
- Time pattern
- Subsequent successful authentication

## Account Lockout Monitoring

### Event ID 4740

Account lockout events provide visibility into accounts that have been locked after repeated authentication failures.

This event can be correlated with authentication failures to investigate possible password-spraying or brute-force activity within the controlled laboratory environment.

## Account Management

### Event ID 4720

This event records the creation of a user account.

Monitoring account creation helps identify unexpected identity changes within the domain.

### Event IDs 4728 and 4729

These events provide visibility into changes to membership of security-enabled global groups.

They can be useful when investigating changes that may affect permissions or administrative access.

## Object Access

### Event ID 4663

This event provides visibility into access to objects that are configured for auditing.

Its interpretation depends on the object, access type and surrounding events.

## PowerShell Monitoring

### Event ID 4103

Provides visibility related to PowerShell module logging.

### Event ID 4104

Provides visibility into PowerShell script block activity.

PowerShell telemetry can be useful when investigating administrative activity or potentially suspicious script execution.

## SIEM Integration

The Windows events are collected and analyzed through Wazuh.

```text
Windows Event Logs
        ↓
Wazuh Agent
        ↓
Wazuh Manager
        ↓
Wazuh Indexer
        ↓
Wazuh Dashboard
        ↓
Security Analysis
