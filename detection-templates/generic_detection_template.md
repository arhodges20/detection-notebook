# Detection: <Detection Name>

## ATT&CK Mapping
- <Technique ID> – <Technique Name>
- <Optional additional techniques>

---

## Attacker Behavior
Attackers may perform <behavior> to:
- 
- 
- 

This activity is commonly observed during:
- <Kill chain phase(s)>

In this detection, the behavior is tracked as:
- <Execution / Access / Discovery / Lateral Movement / Supporting signal>
- <What this detection supports, not claims>

---

## Required Telemetry
### <Platform / Data Source>
- <Event type>
  - <Event IDs or log types>
- <Required logging or visibility assumptions>

---

## Detection Hypothesis
If an attacker is performing <behavior>, we expect to observe:
- 
- 
- 

Often characterized by:
- <Contextual clues such as parent process, source IP, execution context>

---

## Detection Logic (Generic)
Trigger when:
- <High-level condition>
- <High-level condition>

Avoids asserting:
- <Intent>
- <Outcome>

---

## Example Sigma Logic (Simplified)

```yaml
title: <Detection Name>
status: experimental
logsource:
  category: <category>
  product: <platform>
detection:
  selection:
    <Field>:
      - <Value>
  condition: selection
level: <low|medium|high>
