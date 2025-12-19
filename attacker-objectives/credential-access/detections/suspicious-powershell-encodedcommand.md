# Detection: Suspicious PowerShell EncodedCommand

## ATT&CK Mapping
- T1059.001 – PowerShell

## Attacker Behavior
Attackers frequently use Base64-encoded PowerShell commands to:
- Obfuscate intent
- Evade simple string-based detections
- Deliver payloads filelessly
- Deliver or stage credential-theft tooling (e.g., Invoke-Mimikatz) using execution that enables credential access rather than being the objective itself.

This is commonly observed during credential access, initial access staging, and post-exploitation; here it is tracked as an execution signal that supports the Credential Access objective.

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

---

## Limitations / Blind Spots (linked to threat model assumptions)
- Depends on threat model assumptions about telemetry availability (process creation logging and, ideally, PowerShell logging); without these, detection quality degrades.
- Evasion via renamed binaries, Living-off-the-Land execution, or EDR bypass techniques aligns with threat-model blind spots; this rule will miss such cases.
- This is a generic execution signal and not credential-theft-specific by itself; additional context is required to confirm Credential Access intent.

