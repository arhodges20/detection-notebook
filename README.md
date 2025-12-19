# Detection Notebook

This repository is a **public detection engineering notebook** that documents how I think through, design, and reason about detections using a threat-informed approach.

It focuses on **detection logic, assumptions, tradeoffs, and analyst decision-making**, rather than deployable production rules.

---

## What this repo shows

- Threat-model-driven detection design (starting from attacker goals, not alerts)
- MITRE ATT&CK mapping and **conceptual** coverage tracking
- **Example** detection logic representations (Sigma / SPL / KQL) for illustration
- Explicit assumptions, limitations, and analyst validation considerations

---

## Structure

- `methodology/` — how I approach detection engineering end-to-end (thinking, not tooling)

- `attacker-objectives/` — detection write-ups organized by attacker goals, including:
  - attacker behavior
  - detection claims and non-claims
  - analyst decision points
  - coverage considerations

- `telemetry/` — notes on relevant log sources, schemas, and visibility constraints (planned)

- `metrics/` — conceptual approaches to coverage and effectiveness tracking (planned)

---

## Scope and Disclosure

This repository **does not contain production-ready detections** and is **not intended for direct deployment** in any environment.

Any example logic included is:
- intentionally incomplete or underspecified
- platform-agnostic where possible
- provided to illustrate *detection reasoning*, not operational tuning

This notebook is designed to demonstrate **how detections are thought about**, not to expose or replicate live security controls.
