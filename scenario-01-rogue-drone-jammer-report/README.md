# Scenario: Detection and Mitigation of Rogue RF Drone Jammer

## Overview
A rogue drone was detected hovering near company facilities, disrupting Wi-Fi and GPS signals. The drone was emitting targeted RF interference in the 2.4 GHz and 1.5 GHz bands, consistent with consumer-grade jamming hardware.

## Impact Summary
- Temporary disruption to drone-based inventory scanning
- Loss of GPS signal for on-site delivery vehicles
- 7% drop in warehouse network throughput

## Forensics & Analysis
- RF spectrum analysis logs captured spikes between 2.42–2.48 GHz
- Drone visual identified via thermal camera, 70 ft altitude
- Suspected jamming origin: custom drone running SDR hardware (BladeRF variant)

## Response Actions
1. Isolated affected mesh network nodes
2. Activated RF alert threshold in intrusion detection platform
3. Reported incident to FCC regional office (violation of Title 47 CFR Part 15)

## Recommendations
- Deploy RF anomaly baseline for continuous spectrum monitoring
- Integrate directional RF localization tools (Yagi antenna or triangulation grid)
- Implement drone surveillance countermeasure (non-interference passive radar)

## Status: **Closed**
