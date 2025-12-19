# Initial Access Detection Coverage

This document tracks detection coverage for Initial Access scenarios, focusing on early trust boundary crossings and attempted access paths into the environment.

| Technique / Scenario                                   | Detection                                      | Status       | Notes                                                                 |
|--------------------------------------------------------|------------------------------------------------|--------------|-----------------------------------------------------------------------|
| First-time privileged access from new network          | First-Time WordPress Admin Login from New Network | Documented   | Surfaces new authenticated admin access paths requiring analyst triage |
| Exploit attempt against public-facing application      | Apache HTTP Server Path Traversal Attempt       | Documented   | Network-based exploit-pattern detection for attempted initial access   |
