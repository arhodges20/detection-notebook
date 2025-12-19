# Initial Access Threat Model

## Objective
Identify the first successful trust boundary crossings from external actors into internal systems.

## What Initial Access Means Here
Initial Access occurs when an external actor successfully authenticates to or interacts with an internal resource in a way that was not previously expected.

## Assumptions
- External access paths to internal systems exist
- Authentication events are logged with sufficient context
- Legitimate users may occasionally access from new locations or networks

## Common Initial Access Patterns
- First-time authentication from a new network
- Access to internal administrative interfaces from the internet
- Valid credential use that appears legitimate but is contextually abnormal

## Out of Scope
- Post-authentication activity (Persistence, Lateral Movement)
- Credential theft mechanics
- Malware execution after access is obtained
