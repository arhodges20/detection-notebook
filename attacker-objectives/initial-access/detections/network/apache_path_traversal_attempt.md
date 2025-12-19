# Detection: Apache HTTP Server Path Traversal Attempt

## Detection Summary
This detection surfaces network traffic exhibiting URL path structures consistent with path traversal behavior, for analyst review.

## ATT&CK Mapping
T1190 – Exploit Public-Facing Application

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
- Network traffic inspection with visibility into inbound HTTP requests
- HTTP request parsing, including URL paths and request methods
- Sensor placement positioned to observe traffic targeting public-facing services

## Analyst Decisions Required
- Is this traffic expected?
- Was the request accepted or otherwise handled by the application, as evidenced by observable responses?

## Confidence-Building Signals
- the source IP address is associated with known scanning, exploitation, or adversary infrastructure based on threat intelligence
- the targeted service is known to be running a version affected by the referenced path traversal vulnerability, based on asset inventory or service fingerprinting
- repeated or patterned path traversal requests are observed against the same resource or across multiple paths over a short time window

## Known Limitations
- This detection does not confirm whether the request resulted in access to specific files or resources, as it is based on network request patterns rather than application-level outcomes.
- This detection may surface benign activity, such as vulnerability scanning, security testing, or misconfigured clients, that exhibits similar URL path manipulation patterns.
- This detection is dependent on network sensor placement and visibility; path traversal attempts that bypass inspected network paths (e.g., direct cloud service access, encrypted traffic without inspection, or alternate ingress points) may not be observed.
