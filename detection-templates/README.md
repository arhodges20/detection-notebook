# Detection Templates

This directory contains reusable detection design templates used to standardize
how detections are documented in this repository.

These templates focus on:
- Attacker behavior and hypotheses
- Required telemetry and assumptions
- High-level detection logic
- Explicit limitations and blind spots

They intentionally exclude:
- Vendor-specific query logic
- SPL, KQL, or production-ready Sigma rules

Templates are used as scaffolding to create individual detection write-ups
located in the `/detections/` directory.
