# Methodology

## Detection engineering lifecycle (simple version)
1. Define attacker objective (what the adversary is trying to achieve)
2. Map to ATT&CK techniques (how they do it)
3. Identify required telemetry (what you must be able to observe)
4. Write a detection hypothesis (what behavior should exist if the technique occurs)
5. Implement detection logic (Sigma/SPL/KQL)
6. Document assumptions + blind spots (where this will fail)
7. Validate with real technique simulation (Atomic Red Team / scripts / lab activity)
8. Track coverage + tune (measure quality over time)

## Output expectations
Every detection should include:
- ATT&CK technique mapping
- Data sources required
- Why the logic works (in plain English)
- Known limitations and false positive risks
- How it was validated

