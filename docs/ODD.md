# Operational Design Domain (ODD) — Lane Keep Assist

This document defines the assumed operating conditions for the sample LKA module. It exists to give the requirements-to-userstories pipeline consistent context to reference during feature decomposition (e.g., detecting when a requirement implicitly depends on an ODD boundary).

## Vehicle & Automation Level
- Passenger vehicle, SAE Level 2 automation
- LKA is a driver-assistance function; driver remains responsible for the driving task at all times

## Roadway
- Structured roads with visible, machine-readable lane markings (painted lines, reflective markers)
- Highway / motorway environments primarily; not validated for unmarked rural roads or complex urban intersections

## Speed Range
- Operational: 60–130 km/h
- Below 60 km/h: system unavailable (assumption — typical for highway-oriented LKA)
- Above 130 km/h: system unavailable (assumption — validation boundary)

## Environmental Conditions
- **In scope:** Daylight, dusk/dawn, light-to-moderate rain, clear night with adequate road lighting/headlights
- **Out of scope (this sample):** Heavy snow cover on lane markings, dense fog, standing water obscuring markings, construction zones with temporary/conflicting markings

## Sensors Assumed
- Single forward-facing mono camera (lane marking detection)
- Steering torque sensor (driver override / hands-off detection)
- Vehicle speed sensor (CAN bus)

## Known Limitations (by design, for this sample)
- No lane-marking-absent ("virtual lane") capability
- No construction-zone handling
- No sensor fusion with radar/lidar — camera-only, single-point-of-failure by design (this is a deliberate simplification for a test fixture, not a real-world recommendation)

## Assumptions Log
| # | Assumption | Rationale |
|---|---|---|
| A1 | ASIL C applies to core steering intervention functions | Reasonable default for a Level 2 lateral control function; not derived from a real HARA |
| A2 | 15-second hands-off detection threshold | Common industry ballpark figure, used for realism |
| A3 | 200ms fault-to-safe-state transition | Typical order-of-magnitude for safety-relevant automotive fault handling |

These are **assumptions for pipeline-testing purposes only** and have not been derived from a formal Hazard Analysis and Risk Assessment (HARA).
