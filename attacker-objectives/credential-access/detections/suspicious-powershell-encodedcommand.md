# Detection: Suspicious PowerShell EncodedCommand

## ATT&CK Mapping
- T1059.001 – PowerShell

## Attacker Behavior
Attackers frequently use Base64-encoded PowerShell commands to:
- Obfuscate intent
- Evade simple string-based detections
- Deliver payloads filelessly

This is commonly observed during credential access, initial access staging, and post-exploitation.

---

## Required Telemetry
### Windows Endpoint
- Process creation events
  - Sysmon Event ID 1 **or**
  - Windows Security Event ID 4688
- Command-line logging enabled

---

## Detection Hypothesis
If an attacker is executing obfuscated PowerShell commands, we will observe:
- `powershell.exe` or `pwsh.exe`
- The `-EncodedCommand` or `-enc` argument
- Often launched from non-interactive or unusual parent processes

---

## Detection Logic (Generic)
Trigger when:
- Process name is `powershell.exe` or `pwsh.exe`
- Command line contains:
  - `-EncodedCommand` OR
  - `-enc`

---

## Example Sigma Logic (Simplified)

```yaml
title: Suspicious PowerShell EncodedCommand
status: experimental
logsource:
  category: process_creation
  product: windows
detection:
  selection:
    Image|endswith:
      - '\powershell.exe'
      - '\pwsh.exe'
    CommandLine|contains:
      - '-EncodedCommand'
      - '-enc'
  condition: selection
level: medium

