# Detection Notebook

This repository is a practical “detection engineering notebook” that demonstrates how I design, document, and validate detections using a threat-informed approach.

## What this repo shows
- Threat-model–driven detection design (start from attacker goals, not alerts)
- MITRE ATT&CK mapping and coverage tracking
- Detection logic in multiple formats (Sigma / SPL / KQL where applicable)
- Clear assumptions, limitations, and validation notes

## Structure
- `methodology/` — how I approach detection engineering end-to-end
- `attacker-objectives/` — detections organized by attacker goals (with threat models + coverage)
- `telemetry/` — notes on log sources and schemas (future)
- `metrics/` — coverage and effectiveness tracking (future)
