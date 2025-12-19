# Coverage: Credential Access

| ATT&CK Technique | Detection(s) | Data Source | Confidence | Notes / Gaps |
|---|---|---|---|---|
| T1003 OS Credential Dumping | (planned) | Sysmon / EDR | Low (initial) | Need specific LSASS access visibility + test cases |
| T1110 Brute Force | (planned) | Entra sign-in logs | Medium | Need thresholds + exceptions for legit patterns |
| T1555 Credentials from Password Stores | (planned) | Sysmon / EDR | Low | Requires identifying common tooling + access patterns |
| T1059.001 PowerShell | (planned) | Sysmon + PS logs | Medium | Start with encoded / download cradle patterns |

