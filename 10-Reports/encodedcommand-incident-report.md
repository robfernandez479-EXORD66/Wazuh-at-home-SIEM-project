# Incident Report: Suspicious PowerShell EncodedCommand Execution

**Incident ID:** IR-2026-PSH-001  
**Detection ID:** WZ-DET-001  
**Rule ID:** 100010  
**MITRE ATT&CK:** T1059.001 – PowerShell  
**Severity:** High  
**Status:** Closed  
**Date:** <Insert Date of Alert>  
**Analyst:** Robert Fernandez  

---

## 1. Executive Summary

Wazuh generated a high‑severity alert indicating that `powershell.exe` was executed with the `-EncodedCommand` flag.  
This behavior is commonly associated with obfuscated or malicious PowerShell activity, including payload execution, reconnaissance, and defense evasion.

The alert was validated, decoded, and investigated. No malicious payload was identified in this test scenario, as the activity was intentionally generated for detection validation.

---

## 2. Detection Details

**Alert Source:** Wazuh Manager  
**Rule Triggered:** `100010 – Suspicious PowerShell usage with EncodedCommand`  
**Agent:** <Windows Hostname>  
**User:** <User Account>  
**Command Line:**  

powershell.exe -EncodedCommand <Base64String>

**Evidence:**  
- Raw alert JSON: `04-Data-Samples/encodedcommand-alert.json`  
- Screenshots:  
  - `09-Screenshots/encodedcommand_alert_01.png`  
  - `09-Screenshots/encodedcommand_rawlog_01.png`  
  - `09-Screenshots/encodedcommand_dashboard_01.png`  

---

## 3. Timeline of Events

| Time (Local) | Event |
|--------------|--------|
| HH:MM:SS | PowerShell process executed with EncodedCommand |
| HH:MM:SS | Wazuh agent forwarded event to Manager |
| HH:MM:SS | Rule 100010 triggered |
| HH:MM:SS | Analyst began triage |
| HH:MM:SS | Encoded command decoded and reviewed |
| HH:MM:SS | Incident closed as expected test activity |

---

## 4. Investigation Summary

### 4.1 Initial Triage
- Verified alert in Wazuh Security Events  
- Confirmed command line contained `EncodedCommand`  
- Identified user and host involved  
- Checked for additional suspicious PowerShell executions  

### 4.2 Decoding the EncodedCommand
Decoded using:

```powershell
[System.Text.Encoding]::Unicode.GetString([System.Convert]::FromBase64String("<Base64Here>"))

Decoded Result:  
<Insert decoded content here — e.g., benign test string or script>

4.3 Host Activity Review
No additional suspicious processes observed

No network connections to unknown IPs

No persistence mechanisms created

No file modifications detected

5. Root Cause Analysis
Cause:  
Intentional execution of an EncodedCommand for detection validation.

Why It Triggered:  
The Wazuh rule correctly identified the presence of the EncodedCommand flag in the PowerShell command line.

Impact:  
None — controlled test activity.

6. Containment & Remediation
Since this was a controlled test:

No containment actions required

No remediation required

Detection validated successfully

7. Recommendations
Continue monitoring for EncodedCommand usage

Combine this detection with:

Parent process analysis (Sysmon Event ID 1)

Network activity correlation

User behavior analytics

Add exclusions for known administrative scripts if needed

8. Supporting Artifacts
Artifact	Location
Raw alert JSON	04-Data-Samples/encodedcommand-alert.json
Alert screenshot	09-Screenshots/encodedcommand_alert_01.png
Raw log screenshot	09-Screenshots/encodedcommand_rawlog_01.png
Dashboard screenshot	09-Screenshots/encodedcommand_dashboard_01.png
Detection rule	06-Detections/powershell-encodedcommand.md
Playbook	07-Playbooks/powershell-encodedcommand.md

9. Conclusion
The detection for suspicious PowerShell EncodedCommand execution is functioning as intended.
The alert was validated, decoded, and analyzed with no malicious activity identified.
This incident confirms that the Wazuh rule and Sysmon configuration provide effective visibility into obfuscated PowerShell usage.
