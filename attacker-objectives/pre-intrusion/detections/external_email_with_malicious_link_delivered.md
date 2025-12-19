# Detection: External Email with External Link Delivered

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
- An external email was successfully delivered to a user’s inbox

- The delivered email contained a hyperlink directing to an external domain


## What This Detection Does NOT Claim
- The presence of the email indicates a user account compromise

- The user interacted with the hyperlink contained in the email

- Any credentials, sessions, or systems were accessed as a result of this email


## Required Telemetry
- Email delivery telemetry indicating successful delivery to a user inbox

- Visibility into email message metadata and content, including embedded hyperlinks

- Association of the delivered email with a recipient user account


## Analyst Decisions Required
- Is this email and its embedded external hyperlink expected for the recipient user or their role?
  
- Are the external hyperlinks benign or malicious?


## Confidence-Building Signals
- The domain referenced by the embedded hyperlink is associated with known malicious or suspicious activity based on domain reputation or threat intelligence
  
- User interaction with the embedded hyperlink is observed following email delivery
  
- The hyperlink was not rewritten or otherwise mitigated by email security controls prior to user interaction


## Known Limitations
- This detection does not analyze the content of the embedded hyperlink or the destination domain beyond its presence in the email
  
- External emails containing hyperlinks are common in legitimate business communications and may result in benign activity being surfaced
  
- This detection is limited to email delivery telemetry and does not confirm user interaction or downstream impact without additional correlated signals
