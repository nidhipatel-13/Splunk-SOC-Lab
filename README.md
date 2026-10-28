
# 🔎 Splunk SOC Lab | Detection & Investigation

> A hands-on Security Operations Center (SOC) home lab built using Splunk Enterprise, Windows 10, Sysmon, and the Splunk Universal Forwarder. This project demonstrates Windows log collection, security event investigation, and threat-hunting using Splunk Search Processing Language (SPL).

![Platform](https://img.shields.io/badge/Platform-Windows%2010-blue)
![SIEM](https://img.shields.io/badge/SIEM-Splunk%20Enterprise-black)
![Telemetry](https://img.shields.io/badge/Telemetry-Sysmon-orange)
![Focus](https://img.shields.io/badge/Focus-Blue%20Team-brightgreen)
![MITRE ATT%26CK](https://img.shields.io/badge/MITRE-ATT%26CK-red)

## 🎯 Project Objectives

- 🛡️ Set up Splunk Enterprise for centralized security monitoring and log analysis.
- ⚙️ Configure Splunk Universal Forwarder.
- 🧠 Develop and validate Splunk SPL detections.
- 🗺️ Map relevant detection use cases to MITRE ATT&CK.
- 🚨 Identify potential persistence and defense evasion activity.
- 📊 Build a foundation for SOC dashboards and alerting.

## 🏗️ Lab Architecture

  
```text
Windows 10 VM (VirtualBox)
        |
        | Windows Security Logs
        | Sysmon Operational Logs
        v
Splunk Universal Forwarder
        |
        v
Splunk Enterprise 10.6.1.1
        |
        v
SPL Searches and Security Investigation
```

## ⚙️ Lab Environment

| Component | Configuration |
|---|---|
|  SIEM | Splunk Enterprise 10.6.1.1 |
|  Endpoint | Windows 10 VM |
|  Virtualization | Oracle VirtualBox |
|  Log Collection | Splunk Universal Forwarder |
|  Telemetry |  Sysmon |

## 🔎 Detection & Investigation

### 1. DNS Query Monitoring
- Source: Sysmon Event ID 22
- Review process-associated DNS queries.
- Investigate unusual domain lookups and DNS activity.

### 2. Failed Logon Investigation
- Source: Windows Security Event ID 4625
- Extract logon type information.
- Review authentication failures and identify suspicious patterns.

### 3. PowerShell Process Monitoring
- Source: Sysmon Event ID 1
- Search for PowerShell process execution.
- Inspect parent processes, executable paths, and command lines.

### 4. Registry Persistence Monitoring
- Source: Sysmon Event ID 13
- Monitor registry changes involving Windows `CurrentVersion\Run` keys.
- Investigate suspicious autorun entries.

### 5. Security Audit Log Clearing
- Source: Windows Security Event ID 1102
- Identify Security audit log clearing events.
- Review surrounding activity and investigate potential evidence tampering.


## 🧰 Skills Demonstrated

- SIEM fundamentals and event log investigation
- Writing and understanding Splunk Processing Language (SPL) searches
- Windows process monitoring using Sysmon
- Failed logon investigation using Windows Security logs
- DNS query monitoring and analysis
- Registry activity monitoring
- Windows Security log investigation
- Filtering events and presenting results in tables
- Understanding endpoint telemetry and its role in SOC operations

