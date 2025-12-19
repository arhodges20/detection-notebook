# Detection: First-Time WordPress Admin Login from New Network

## Objective
Initial Access

## Detection Goal
Reduce uncertainty around new trust boundary crossings into privileged WordPress administration.

## Hypothesis
If this detection fires, a previously untrusted network has successfully authenticated to a privileged WordPress admin interface.

## What This Detection Does NOT Claim
- This detection does not claim malicious intent.
- This detection does not determine disposition.
- This detection does not assert credential compromise.

## Decision This Detection Forces
Is this authenticated admin access from a new network expected and authorized, or does it represent unauthorized initial access that requires containment?

## Why This Matters
Initial Access often occurs through valid credentials and appears legitimate.
Surfacing first-time authenticated access from new networks forces early decisions before further attacker actions occur.

## Signals That Increase Confidence
- Source IP, ASN, or network associated with known malicious infrastructure
- Authentication from a geographic location never previously associated with WordPress administration
- Immediate follow-on privileged actions (e.g., plugin installation, user creation)

## Signals That Reduce Confidence
- Confirmed administrator travel or remote work
- First-time use of a corporate or personal VPN by an existing administrator
- Change management or onboarding context

## Assumptions and Blind Spots
- Assumes successful authentication events are reliably logged
- Does not detect attacks that originate from previously trusted networks
- Does not differentiate between stolen credentials and legitimate credential use
