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
├── DownloadedSoftware.kql
├── KQL Queries_github.kql
├── PasswordChange.kql
├── PasswordChangeFollowedByBruteforce.kql
├── PIMEscalationMotive.kql
└── RegistersAndProcessesByHost.kql
```

---

## Folder Overview

### SharePointActivity

Queries related to SharePoint file and folder activity:

- Detection of deleted files  
- File access tracking  
- Folder operations monitoring  

Useful for auditing collaboration environments and detecting suspicious document handling.

---

### SignIns

Authentication-related queries:

- Sign-in attempts by user  
- Account activity investigation  

Useful for identifying brute force attempts, anomalous login behavior, and account misuse.

---

### USB

Endpoint monitoring queries focused on removable media:

- USB device connections  
- Files created from USB drives  
- Files downloaded to/from USB  
- Processes initiated from USB devices  

These queries are particularly useful for:

- Data exfiltration detection  
- Insider threat monitoring  
- Investigating suspicious removable media activity  

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
- **PasswordChange.kql** – Tracks password modification events  
- **PasswordChangeFollowedByBruteforce.kql** – Detects suspicious sequences involving password changes and brute force attempts  
- **PIMEscalationMotive.kql** – Investigates privilege escalation patterns (e.g., PIM-related activity)  
- **RegistersAndProcessesByHost.kql** – Correlates registry modifications and process activity per host  
- **KQL Queries_github.kql** – Aggregated or reference queries  

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
