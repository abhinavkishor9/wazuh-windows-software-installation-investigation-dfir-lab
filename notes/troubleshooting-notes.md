# Troubleshooting Notes

## Issue 1 — Installer Events Missing

### Cause

Application was installed using a method that bypassed Windows Installer.

### Resolution

Use an MSI-based installer or verify the application's logging behavior.

---

## Issue 2 — No MsiInstaller Events

### Cause

Incorrect log location or provider.

### Resolution

Verify the Application log and filter by the **MsiInstaller** provider.

---

## Issue 3 — Events Missing in Wazuh Discover

### Cause

Indexing delay or incorrect search query.

### Resolution

Wait briefly after installation and search using:

```
data.win.system.providerName:"MsiInstaller"
```

---

## Issue 4 — PowerShell Returns No Results

### Cause

Incorrect provider name or log selection.

### Resolution

Verify the Application log and ensure the provider is **MsiInstaller**.

---

## Issue 5 — Application Not Listed

### Cause

Installation failed or was incomplete.

### Resolution

Confirm installation through Installed Apps or Control Panel before beginning the investigation.

---

# Lessons Learned

- Windows Installer events provide reliable software installation evidence.
- Event Viewer and PowerShell should both be used for validation.
- Wazuh Discover simplifies centralized investigation.
- Multiple evidence sources strengthen forensic conclusions.
- Native Windows logging provides effective DFIR visibility.
