# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 09:00 | Verified Wazuh agent connectivity | agent_control |
| 09:05 | Installed Windows application | Installer |
| 09:08 | Verified installation | Installed Apps |
| 09:10 | Reviewed Event Viewer | MsiInstaller |
| 09:13 | Validated events using PowerShell | Get-WinEvent |
| 09:16 | Investigated Wazuh Discover | Discover |
| 09:20 | Correlated evidence | Documentation |
| 09:25 | Completed investigation | Report |

---

# Investigation Flow

Investigation Started

↓

Verified Agent Health

↓

Installed Application

↓

Confirmed Installation

↓

Reviewed Event Viewer

↓

Validated with PowerShell

↓

Investigated Wazuh Discover

↓

Correlated Evidence

↓

Investigation Completed

---

# Summary

The investigation successfully reconstructed Windows software installation activity using native Windows Installer logs and Wazuh Discover. Evidence from Event Viewer, PowerShell, and Wazuh consistently confirmed successful software deployment while demonstrating how installation events can be investigated without Sysmon.
