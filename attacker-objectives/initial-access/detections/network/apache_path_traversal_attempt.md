# Detection: Apache HTTP Server Path Traversal Attempt

## Detection Summary
This detection surfaces network traffic exhibiting URL path structures consistent with path traversal behavior, for analyst review.

## ATT&CK Mapping


## Attacker Behavior
- Attackers manipulate the URL structure of HTTP requests to influence how a server processes the request.

- This technique is commonly used to attempt to interact with unintended paths or resources.

- This behavior is typically observed during initial access stages of an intrusion.


## What This Detection Claims
If this detection fires, it indicates that:
- network traffic originating from an external source was observed targeting an internal, public-facing resource
- the observed traffic contained URL path structures consistent with path traversal behavior

## What This Detection Does NOT Claim
- the observed traffic was malicious in intent
- the path traversal behavior was successful
- the targeted system or application was compromised

## Required Telemetry


## Analyst Decisions Required


## Confidence-Building Signals


## Known Limitations
