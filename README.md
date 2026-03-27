# Microsoft Sentinel KQL Queries

This repository contains a curated collection of **Kusto Query Language (KQL)** queries designed for use in **Microsoft Sentinel**.

The project is focused on supporting:

- SOC Analysts performing threat hunting and incident investigation  
- Security teams building custom analytics rules  
- System Administrators monitoring user activity and system behavior  
- Blue teams improving visibility across endpoints and cloud services  

The queries included in this repository can be used for:

- Threat hunting  
- Detection engineering  
- User activity monitoring  
- Insider threat analysis  
- Incident response investigations  
- Security auditing  

---

## Project Structure

```text
.
├── SharePointActivity
│   ├── SharePointDeletedFiles.kql
│   ├── SharePointFiles.kql
│   └── SharePointFolders.kql
│
├── SignIns
│   └── SignInAttemptsByUser.kql
│
├── USB
│   ├── CreatedFilesFromUSB.kql
│   ├── FileDownloadedFromUSB.kql
│   ├── InitiatedProcessByUSB.kql
│   └── USBConnectedDevices.kql
│
├── WebHistory
│   ├── NavigationHistoryByUser.kql
│   ├── WebVisitedByUser.kql
│   └── WebVisitedGroupedByVisitCount.kql
│
├── VBS
│   ├── ChangesFileOwnership.kql
│   ├── RunsFromSuspiciousFolder.kql
│   ├── RunsShell.kql
│   └── StartsRemoteConnection.kql
|
├── DownloadedSoftware.kql
├── EmailAttachmentInfoSuspicious.kql
├── EmailAttachmentInfoSuspicious.kql
├── PasswordChange.kql
├── PasswordChangeFollowedByBruteforce.kql
├── PIMEscalationMotive.kql
├── RegistersAndProcessesByHost.kql
└── RemoteToolsExecution.kql
```

---

## Folder Overview

### SharePointActivity

Detection queries focused on SharePoint file and folder activity:

- File deletion events  
- File access and interaction tracking  
- Folder creation, modification, and deletion operations  

These queries are particularly useful for:

- Auditing collaboration environments  
- Detecting suspicious document handling  
- Investigating potential data exfiltration or tampering

---

### SignIns

Detection queries related to authentication and account activity:

- User sign-in attempts and patterns  
- Account activity investigation and correlation  

These queries are particularly useful for:

- Identifying brute force or password spraying attacks  
- Detecting anomalous login behavior (impossible travel, unusual locations)  
- Investigating account compromise and misuse 

---

### USB

Detection queries focused on removable media activity at the endpoint level:

- USB device connection events  
- Files created or executed from USB devices  
- File transfers to and from removable media  
- Processes launched from USB-mounted paths  

These queries are particularly useful for:

- Detecting data exfiltration via removable media  
- Monitoring insider threat activity  
- Investigating unauthorized device usage  
- Tracing initial access vectors involving physical media 

---

### VBS

Detection queries focused on browser and navigation activity:

- Websites visited by users  
- Navigation history correlated per user  
- Visit frequency and domain patterns  

These queries are particularly useful for:

- Investigating access to malicious or risky domains  
- Monitoring user browsing behavior during incidents  
- Supporting threat hunting and timeline reconstruction  

---

### WebHistory

Browser and navigation activity queries:

- Websites visited by user  
- Navigation history per user  
- Visit counts grouped by frequency  

Useful for:

- Investigating malicious browsing  
- Monitoring risky domains  
- User activity review during incident response  

---

## Standalone Queries

The repository also includes individual KQL queries focused on specific security scenarios:

- **DownloadedSoftware.kql** – Identifies downloaded executables and software activity
- **EmailAttachedFiles_Suspicious** - Lists emails with attached files that contain extensions such as ".exe", ".js", ".iso", ".bat". It includes documents with macros such as ".docm" and "xlsm" that can be uncommented
- **PasswordChange.kql** – Tracks password modification events  
- **PasswordChangeFollowedByBruteforce.kql** – Detects suspicious sequences involving password changes and brute force attempts  
- **PIMEscalationMotive.kql** – Investigates privilege escalation patterns (e.g., PIM-related activity)  
- **RegistersAndProcessesByHost.kql** – Correlates registry modifications and process activity per host  
- **RemoteToolsExecution.kql** - Lists execution of Remote Desktop Applications like TeamViewer, Anydesk, RustDesk, ScreenConnect.ClientService, UltraViewer and DWAgent

---

## Requirements

To use these queries effectively, you should have:

- Microsoft Sentinel deployed  
- Microsoft Defender for Endpoint (recommended for USB and process visibility)  
- Relevant data connectors enabled (Azure AD, Office 365, Defender, etc.)  

Ensure that the required tables (e.g., `DeviceEvents`, `DeviceFileEvents`, `SignInLogs`, `OfficeActivity`) are available in your workspace.

---

## Usage

1. Open Microsoft Sentinel.  
2. Navigate to **Logs**.  
3. Copy and paste the desired `.kql` query.  
4. Adjust filters such as:
   - Time range  
   - User UPN  
   - Device name  
   - File hash  
   - Domain  
5. Optionally convert the query into:
   - An Analytics Rule  
   - A Hunting Query  
   - A Workbook visualization  

---

## Contribution

Contributions are welcome. You may:

- Improve query performance  
- Add new detection scenarios  
- Enhance documentation  
- Add MITRE ATT&CK mapping  
- Provide tuning guidance  

Please ensure queries are properly formatted and documented before submitting changes.

---

## Disclaimer

These queries are provided as-is. They should be tested and adapted to your environment before being deployed in production as detection rules.

Always validate query logic, performance impact, and false positive rates in your tenant.

---

## License

This project is intended for educational and operational security purposes under GPL-3.0 license
