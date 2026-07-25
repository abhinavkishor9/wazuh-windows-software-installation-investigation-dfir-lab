# Investigation Notes

## Lab Summary

This investigation focused on analyzing Windows software installation activity using native Windows Installer logs and Wazuh.

The investigation reconstructed application installation by correlating Event Viewer, PowerShell, and Wazuh Discover evidence.

---

## Analyst Methodology

The investigation followed a structured DFIR workflow:

1. Verify Wazuh agent connectivity.
2. Install a Windows application.
3. Confirm installation.
4. Review MsiInstaller events.
5. Validate installer logs using PowerShell.
6. Search installation events in Wazuh Discover.
7. Correlate evidence.
8. Document findings.

---

## Investigation Scenario

A Windows workstation received a new software installation.

The investigation aimed to determine:

- Which application was installed.
- Whether installation completed successfully.
- Which Windows events were generated.
- Whether Wazuh collected the activity.

---

## Evidence Collected

### Evidence 1 – Installed Application

Collected:

- Installed application
- Version
- Installation status

Finding:

Confirmed successful application deployment.

---

### Evidence 2 – Windows Event Viewer

Collected:

- MsiInstaller events
- Event IDs
- Installation timestamp

Finding:

Confirmed successful installation activity.

---

### Evidence 3 – PowerShell Validation

Command Used

```powershell
Get-WinEvent -LogName Application |
Where-Object {$_.ProviderName -eq "MsiInstaller"} |
Select TimeCreated, Id, LevelDisplayName, Message -First 10
```

Finding:

Validated Windows Installer events independently.

---

### Evidence 4 – Wazuh Discover

Collected:

- Installer events
- Provider Name
- Event IDs

Finding:

Confirmed successful event collection within Wazuh.

---

## DFIR Analysis

Evidence from Event Viewer, PowerShell, and Wazuh consistently confirmed successful software installation.

Correlating these sources reconstructed the installation timeline and validated software deployment.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | User Execution | T1204 |
| Persistence | Software Installation | T1543 (Contextual) |

---

## Analyst Observations

- Windows Installer generates valuable forensic events.
- Event Viewer and PowerShell provide consistent validation.
- Wazuh Discover centralizes installer activity.
- Installation events can be reconstructed without Sysmon.
- Multiple evidence sources improve investigation reliability.

---

## Conclusion

The investigation successfully reconstructed Windows software installation activity using native Windows logging and Wazuh. Event correlation demonstrated how installation events can be validated and documented during endpoint investigations.
