# Detection: External Email with Malicious Link Delivered

## Detection Summary
This detection surfaces external emails delivered to user inboxes that contain hyperlinks to external domains, which may represent a potential pathway to initial access, for analyst review.

## ATT&CK Mapping
None  
(Pre-Intrusion behavioral indicator; email delivery alone does not establish attacker access.)

## Attacker Behavior
- Email links are commonly used by attackers to direct users to external infrastructure they control or have compromised.

- Such links may be used to facilitate credential harvesting, session abuse, or delivery of additional content.

- This activity is frequently observed as an early stage of intrusion campaigns.

## What This Detection Claims
If this detection fires, it indicates that:
- 
- 


## What This Detection Does NOT Claim
- 
- 
- 


## Required Telemetry
- 
- 
- 


## Analyst Decisions Required
- 
- 


## Confidence-Building Signals
- 
- 
- 


## Known Limitations
- 
- 
- 
