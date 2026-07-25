# wazuh-windows-software-installation-investigation-dfir-lab
## Overview

This Digital Forensics and Incident Response (DFIR) lab demonstrates how Windows software installation activity can be investigated using native Windows event logs and Wazuh.

Rather than relying on Sysmon, this investigation uses Windows Installer (MsiInstaller) events collected through Windows Event Logs and Wazuh Discover to reconstruct software installation activity.

The investigation demonstrates how software installation events are generated, validated, collected, and correlated to produce forensic evidence of application deployment.

---

# Executive Summary

This investigation demonstrates how software installation activity can be reconstructed using Windows native logging and Wazuh.

The investigation included:

- Installing a Windows application
- Verifying successful installation
- Analyzing MsiInstaller events
- Validating installation events using PowerShell
- Confirming Wazuh event ingestion
- Investigating installer activity through Wazuh Discover
- Correlating multiple evidence sources

---

# Learning Objectives

- Understand Windows Installer logging
- Investigate software installation events
- Analyze MsiInstaller logs
- Validate installation using PowerShell
- Investigate installation activity using Wazuh Discover
- Correlate installation evidence
- Reconstruct installation timeline

---

# Skills Demonstrated

- Windows DFIR Investigation
- Windows Event Log Analysis
- Software Installation Investigation
- Event Viewer Analysis
- PowerShell Event Validation
- Wazuh Discover Investigation
- Windows Installer Analysis
- Evidence Correlation
- Timeline Reconstruction
- DFIR Documentation
- MITRE ATT&CK Mapping

---

# Tools Used

- Wazuh Dashboard (Discover)
- Windows Event Viewer
- Windows PowerShell
- Windows Installer (MsiInstaller)
- Installed Apps
- Control Panel
- archives.json (if required)

---

# Lab Environment

| Component | Details |
|-----------|---------|
| SIEM | Wazuh 4.12 |
| Endpoint | Windows 11 Pro |
| Server | Oracle Linux 9 |
| Investigation Type | Windows DFIR |
| Event Source | Windows Application Log |
| Provider | MsiInstaller |
| Sysmon | Not Used |

---

# Investigation Scenario

A new application has been installed on a Windows workstation.

As the DFIR analyst, your objectives are to determine:

- Which application was installed
- When the installation occurred
- Whether installation completed successfully
- Which Windows Installer events were generated
- Whether Wazuh collected the installation events
- Reconstruct the installation timeline

---

# Investigation Workflow

1. Verify Wazuh agent connectivity.
2. Install a Windows application.
3. Verify successful installation.
4. Examine Windows Installer events.
5. Validate events using PowerShell.
6. Search for installation events in Wazuh Discover.
7. Correlate installation evidence.
8. Document investigative findings.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | User Execution | T1204 |
| Persistence | Software Installation | T1543 (Contextual) |

### Why Software Installation Matters

Software installation events provide valuable forensic evidence during endpoint investigations. Unauthorized software deployment may indicate insider activity, unauthorized administrator actions, or malware installation. Correlating Windows Installer events with SIEM data enables analysts to reconstruct installation activity accurately.

---

# Evidence Collected

- Installed Application
- Windows Installer Events
- Event Viewer Logs
- PowerShell Validation
- Wazuh Discover Events
- Installation Timeline

---

# Evidence Correlation

| Evidence Source | Information Obtained | Investigation Value |
|-----------------|---------------------|--------------------|
| Installed Apps | Installed software | Confirmed application presence |
| Event Viewer | Installer events | Verified installation |
| PowerShell | Installer logs | Independent validation |
| Wazuh Discover | Collected events | SIEM validation |

---

# Investigation Findings

- Software installation completed successfully.
- Windows generated MsiInstaller events.
- Event Viewer confirmed installation.
- PowerShell validated installer activity.
- Wazuh successfully collected installation events.
- Evidence sources consistently reconstructed the installation process.

---

# Key Takeaways

- Windows Installer logs provide valuable forensic evidence.
- Event Viewer and PowerShell should both be used for validation.
- Wazuh Discover enables centralized investigation of installation activity.
- Correlating multiple evidence sources improves DFIR accuracy.
- Native Windows logs provide excellent visibility without Sysmon.

---

