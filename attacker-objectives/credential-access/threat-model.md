# Threat Model: Credential Access

## Attacker objective
Obtain user credentials (passwords, hashes, tokens, session material) to enable account takeover and access to systems/services.

## Common techniques (MITRE ATT&CK)
- T1003: OS Credential Dumping
- T1110: Brute Force (password spraying / guessing)
- T1555: Credentials from Password Stores
- T1059.001: PowerShell (often used to stage/execute credential theft)
- T1552: Unsecured Credentials (configs, scripts, files)

## Telemetry required (minimum viable)
### Windows endpoint
- Process creation (command line + parent/child): Sysmon Event ID 1 or Windows Security 4688
- (Optional but strong) PowerShell logging: Script Block Logging (4104), Module logging
- (Optional) LSASS access telemetry (Sysmon Event ID 10 if configured, or EDR telemetry)

### Cloud identity (Azure/Entra)
- Sign-in logs (interactive/non-interactive)
- Audit logs (MFA changes, credential registration, risky sign-in signals)

## Detection hypotheses (examples)
- If an attacker is dumping creds, we will see suspicious processes interacting with LSASS or known dumping tooling patterns.
- If an attacker uses PowerShell to stage credential theft, we will see encoded commands, unusual parents, or suspicious download/execute patterns.
- If an attacker is password spraying, we will see many failures across many accounts from a small set of IPs, often with consistent user-agent patterns.

## Assumptions / blind spots
- Without process creation logs, host-based detections degrade significantly.
- Without PowerShell logging, many fileless techniques become harder to detect.
- Attackers can evade naive detections via renamed binaries, living-off-the-land, or EDR bypasses.

## Validation plan (lab)
- Use Atomic Red Team tests for representative techniques
- Generate endpoint telemetry in a Windows VM with Sysmon
- Confirm detections fire and document false positives

