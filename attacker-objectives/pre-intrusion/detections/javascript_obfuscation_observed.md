# Detection: JavaScript Obfuscation Observed in Web Traffic

## Detection Summary
This detection surfaces web traffic in which JavaScript content exhibits characteristics consistent with obfuscation, for analyst review.

## ATT&CK Mapping
None  
(Behavioral indicator only; requires additional correlation to support ATT&CK objective placement.)

## Attacker Behavior
- Attackers may obfuscate JavaScript to hinder human analysis and reverse engineering of code logic.

- JavaScript obfuscation is commonly used to evade simplistic or signature-based security controls that rely on readable content.

- Obfuscated JavaScript is often observed as part of content delivery mechanisms in malicious campaigns, but is not inherently malicious on its own.

## What This Detection Claims
If this detection fires, it indicates that:
- Obfuscated JavaScript content was observed in web traffic

- The obfuscated JavaScript was delivered to a client as part of a web session

## What This Detection Does NOT Claim
- The observed JavaScript was malicious in intent

- The JavaScript content was executed on the client

- The client system was compromised as a result of this activity

## Required Telemetry
- Network or proxy-level visibility into web traffic

- Inspection or analysis capability for JavaScript content within web responses

- Association of observed web traffic with a client session or user context 

## Analyst Decisions Required
- Is the observed obfuscated JavaScript expected for the destination or application?

- Does this activity correlate with additional signals indicating exploit delivery or execution?
  
## Confidence-Building Signals
- The destination IP or domain is associated with known malicious or suspicious infrastructure based on threat intelligence

- Additional web activity such as redirects, exploit attempts, or staged content delivery is observed following the initial JavaScript response

- Correlated endpoint or identity telemetry indicates anomalous behavior following the web session

## Known Limitations
- This detection does not examine or deobfuscate the JavaScript payload; it only identifies characteristics consistent with obfuscation
- Obfuscated JavaScript is frequently observed in legitimate web traffic, which may result in benign activity being surfaced
- This detection is dependent on network or proxy visibility and may miss obfuscated content delivered through encrypted or uninspected channels

