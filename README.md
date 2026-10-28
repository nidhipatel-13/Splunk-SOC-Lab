
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

  
## 🗺️ MITRE ATT&CK Coverage

| Detection use case | Event ID | ATT&CK technique | Investigation goal |
|---|---:|---|---|
| DNS activity | Sysmon 22 | [T1071.004](https://attack.mitre.org/techniques/T1071/004/) | Investigate possible DNS-based C2 |
| Failed logons | Security 4625 | [T1110](https://attack.mitre.org/techniques/T1110/) | Investigate possible brute force |
| PowerShell | Sysmon 1 | [T1059.001](https://attack.mitre.org/techniques/T1059/001/) | Investigate command execution |
| Registry Run keys | Sysmon 13 | [T1547.001](https://attack.mitre.org/techniques/T1547/001/) | Investigate possible persistence |
| Security log clearing | Security 1102 | [T1070.001](https://attack.mitre.org/techniques/T1070/001/) | Investigate possible defense evasion |

> 📌 These are analytic mappings, not proof that an ATT&CK technique occurred. The mapped techniques describe behavior that the detection may help investigate.

## 🧰 Skills Demonstrated

- 🔎 Splunk Search Processing Language (SPL)
- 📥 Windows event collection and analysis
- 🔬 Sysmon telemetry investigation
- 🧠 Threat hunting and event correlation
- 🗺️ MITRE ATT&CK technique mapping
- 🔐 Authentication monitoring
- ⚡ Process execution analysis
- 🧩 Registry persistence investigation
- 🚨 Security log tampering investigation

## 📁 Repository Structure

```text
splunk-soc-lab/
├── README.md
├── .gitignore
├── spl/
│   ├── dns-queries.spl
│   ├── failed-logons.spl
│   ├── powershell-monitoring.spl
│   ├── registry-persistence.spl
│   └── security-log-cleared.spl
└── docs/
    └── investigation-notes.md
```

## 🚀 Project Roadmap

- [x] Install Splunk Enterprise
- [x] Configure Windows 10 VM
- [x] Install Splunk Universal Forwarder
- [x] Search Windows and Sysmon events
- [x] Execute initial SPL investigations
- [x] Document initial ATT&CK mappings
- [ ] Build a SOC monitoring dashboard
- [ ] Create and validate alert rules
- [ ] Document investigation case studies
- [ ] Add sanitized screenshots and findings

## ⚠️ Disclaimer

This project is for educational and defensive cybersecurity purposes in a controlled home lab. Detection results require validation and context. No event ID or SPL result should be treated as a definitive indicator of compromise without supporting evidence.
