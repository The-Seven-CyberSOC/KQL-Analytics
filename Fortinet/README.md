# 🔥 Fortinet KQL Analytics for Microsoft Sentinel

This repository contains KQL detection and threat hunting queries designed for monitoring Fortinet security devices within Microsoft Sentinel.

The queries help detect suspicious, malicious, and anomalous activity across Fortinet telemetry sources such as FortiGate, FortiAnalyzer, and other Fortinet-integrated logs.

---

## 📡 Supported Fortinet Data Sources

- FortiGate Firewall logs
- FortiAnalyzer logs
- Traffic logs
- Event logs
- VPN logs (SSL-VPN, IPSec)
- Authentication logs
- Threat and intrusion logs

---

## 🎯 Use Cases

- Suspicious VPN activity
- Brute force authentication attempts
- Malicious or suspicious IP connections
- Blocked threat detection events
- Privileged account activity
- Firewall deny/allow anomaly detection
- Communication with known malicious indicators

---

## 🧠 Query Types

This repository includes:

- Detection analytics
- Threat hunting queries
- Investigation queries
- Behavioral analytics

All queries are designed for:

- Microsoft Sentinel
- Log Analytics Workspace
- Fortinet logs ingested via Syslog, AMA, or Fortinet connectors

---

## 🧩 Requirements

- Microsoft Sentinel enabled
- Fortinet logs ingested into Log Analytics
- Common tables may include:

